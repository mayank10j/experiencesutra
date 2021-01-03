+++
author = ""
date = 2020-12-24T18:30:00Z
description = ""
image = "/uploads/2021/01/03/logo-1.png"
image_webp = "/uploads/2021/01/03/logo.png"
title = "alternat — The Open Sourced Alternate Text Generator"

+++

Probably this is how an inaccessible website feels like to a visually impaired person.

![](/uploads/2021/01/03/empty_image.jpg)

The problem is not just about an exclusion of a group but has severe financial implications. As per r[esults from the 2019 Click-Away Pound Survey](https://clickawaypound.com/downloads/cap19final0502.pdf)**,** UK retailers lose £17 billion years by ignoring accessibility needs.

But haven’t we solve the problem of inaccessibility? Technically yes, but in reality a sad NO. Everyone knows that alt-text attribute of an image tag in html makes images accessible but the cost to do it is too high.

> Accessibility solutions exists but most of them are unaffordable. The barrier to make accessible solutions is high.

[_alternat_](https://github.com/keplerlab/alternat) is a collection of tool sets with the ambition of lowering the barrier of adapting accessibility solution. In the current MVP, the focus is making images accessible.

The purpose of this post is to take you under the hood and highlight different design choices we made. Knowing behind the scenes thought process helps in using the tool correctly and efficiently.

Driven by our needs and validated with few folks in the industry, _alternat_ can be used in three modes.

* As a CLI
* As library
* As service

## **CLI Mode**

CLI mode (command line mode) — It helps to imagine this as an standalone application — A black box, to which you pass the images and you get back the alternative text. An example would be helpful here

![](/uploads/2021/01/03/alternat_1.png)

The following commands extracts the alt-text from the image

    python app.py generate — output-dir-path=./results/ — input-image
    -file-path=./images_with_text/sample_images/multi.png

The generated output (JSON format) is persisted in the designated output folder path which here is specified via _— output-dir-path_ parameter. I have removed other details for brevity. Please refer to the [documentation](https://alternat.readthedocs.io/en/main/) for details.

    {‘alt’: ‘Appears to contain text: 35% OFF Any cooking class 
    package limited availability 6/17 COOKING SCHOOL .’}

CLI mode is useful for batch mode scenarios. In our case it was required as a airflow task. Btw, as no surprise, you can provide single image or a folder path as a parameter.

## **Library Mode**

Think of it as a python package that you import in your application and integrate in your current workflow or application. This is what you get when you install alternat from PyPi. Library mode was a common demand across the board. In our case it was required for an integration with an existing AI powered image cropping tool. After cropping, alt-text are generated. Code snippet below demonstrates the usage in library mode.

    from alternat.generation
    
    import Generatorgenerator = Generator()
    generator.generate_alt_text_from_file(input_image_file_path, output_dir_path)

## **Service Mode**

Service mode is web API for alternat. If you look at github code repository, you find the api code base in the api folder. It run using the [fastAPI](https://fastapi.tiangolo.com/) python framework. Service Mode is helpful for real-time alt-text generation and non pythonic stacks integration requirements. We choose fastAPI over flask due to fastAPI native support of asyncio and its scalability options. In the content authoring process( web content authoring on CMS), The real-time API can be used for auto alt-text generation process or in the automated content authoring process. As no surprise it is a wrapper over the library exposing the endpoint.

# Image input modes

alternat support different methods to provide the image(s). The table shows the supported method across different modes. We didn’t made it same across all the mode because some input mechanism were mode specific for e.g. base64 based image is not required for application mode — what use case warrants converting image to base64 encoded data on command line!! Since we are talking about input modes, it would be worthwhile to highlight that at the moment, we are only supporting **jpeg, jpg and png**.

![](/uploads/2021/01/03/alernat_image2.png)

_Image input modes matrix_

# alternat components

[alternat](https://github.com/keplerlab/alternat) features are centered around tasks. Following table shows the features break up across each task

![](/uploads/2021/01/03/alternat_image_3.png)

_Task matrix with underlying frameworks_

Why did we split across tasks? The reasons for splitting the tasks was the connections between the two tasks. In majority of batch mode use cases that we found, collection (download images beforehand), was a common requirement. Even for a small websites that we asked around, average images count was more than 40. Searching and downloading all those images manually was not a good idea.

In order to download images, the website needs to be crawled and we have used apify wrapper for puppeteer scraper. In case you don’t know puppeteer — [Puppeteer](https://developers.google.com/web/tools/puppeteer) is a Node library which provides a high-level API to control Chrome or Chromium over the DevTools Protocol. Puppeteer runs headless by default. We are also exploring [scrapy](https://scrapy.org/) (the popular python web crawler) and may added as an option in later releases. Puppeteer, scrapy or later something else are like drivers which the community can add depending upon their requirements. In a nutshell, there could be different ways to download images and alternat needs to be flexible enough for extension easily.

As no surprise, “generate” is responsible for generating the alt-text. To generate the alt-text, the images goes through multiple extractors, filters and text aggregators. Following is the sudo equation to deduce an image alt-text

    alt-text = image caption + ocr + filters + text aggregators 

* image caption extracts what is going on in a image.
* OCR extracts any text in the image
* filters removes very small texts which most probably people will miss.
* text aggregator would combine the texts.

Few examples would be helpful here:

![](/uploads/2021/01/03/caption_test_1.jpg)

_The image caption returned by the generator would be — “Appears to be: a sign on a building.” “Appears to be ” is prefix that we add in order to indicate that generated caption is system interpreted and may be wrong. The captured OCR will be — HOTEL” and “HOTEI”. Note that in the vertical “Hotel”, “L” is almost “I” (well for AI)._

![](/uploads/2021/01/03/caption_test_2.jpg)

_In the above cartoon image, there are texts on the joker screen. Probably you can’t read it but the OCR would. Filters job is to filter out such texts. It does by calculating text to image ratio and if it is below the threshold (configurable), it is ignored._

![](/uploads/2021/01/03/captino_test_3.jpg)

_In the above image, the text blobs won’t be read the way you expect them(most of ML API would treat single line as one text blob). You might get strings like “We can’t Great hotel” because of text blob boundaries. Text aggregators clusters smaller blobs in larger logical groups. By default, it will be row wise but you can change to column-wise._

You may be wondering why we provided different drivers (azure, google and open source) for alt-text generation. Well, there are few reasons for it

* azure and google gives ready to use API, essentially lowering the barrier to get started.
* Most of the organizations don’t have the data to train their own model for OCR and image captioning.
* Open source is a free alternative but can be little less accurate in few situations.

I guess, you get the trade off here between cost and accuracy. As an insider trick — since it is treated as a driver, you can add your own driver. Please refer to the documentation for details.

# alternat components

alternat is configuration driven so that it can be adjusted to different types of images (visual heavy, text heavy etc.). We expect the different thresholds(configuration values) to be adjusted depending on the requirements. In order to adjust it, switch on the debug option and check the confidence/threshold values for your images and then adjust it accordingly. One trick is to set it to zero and then change it slowly and iteratively. To enable the debug mode all you need is to set the “DEBUG” flag to True. Check the JSON sample below.

    {
    "DRIVER": "azure",
    "GENERATOR": 
      {
     	 "DEBUG": false,"ENABLE_OCR_CLUSTERING": true
      },
    }

Inside a python script you need to set the configuration via set_config method

    # set debug to true
    generator_config = {“DEBUG”: True}
    generator.set_config(generator_config)

On command line you need to specify the JSON file. The configuration JSON files as samples are available under the sample/sample_conf_generator_driver folder.

    python example.py generate --output-dir-path=./results/ 
    --input-image-file-path=./images_with_text/sample_images/Hotel-thumbnail.jpg 
    --driver-config-file-path=”sample_conf_generator_driver/azure.json”

Just to make it explicit — to switch from one driver to another, all you need is to change the configuration JSON and that can be provided as a json string or json file. Please recall, that alternat can work us an application or a library.

Shown below are configurable values for azure driver. They are present under “sample_conf_generator_driver” folder. Please refer to the documentation for details. As guessed each of the drivers may have different values and hence are managed separately.

    {
      "DRIVER": "azure",
      "GENERATOR": 
        {
            "DEBUG": false,"ENABLE_OCR_CLUSTERING": true
         },
       "SUBSCRIPTION_KEY": "",
       "ENDPOINT": "",
       "AZURE_RATE_LIMIT_ON": true,
       "AZURE_RATE_LIMIT_TIME_IN_SEC": 30,
       "CAPTION_CONFIDENCE_THRESHOLD": 0.2,
       "OCR_CONFIDENCE_THRESHOLD": 0.75,
       "LABEL_CONFIDENCE_THRESHOLD": 0.75,
       "OCR_HEIGHT_RATIO_TO_IMAGE_THRESHOLD": 0.015,
     }

Since, the alt-text are ML generated/interpreted, we recommend it to be reviewed manually. The easiest and robust way is to upload it in a CMS (content management system) and let it go through the content review process. But, would it not take away the benefits of automation. In our experience, even with manual review the the workflow reduced the total effort by almost 40%. Correction is always easier than creation.

We look forward to the community for feedback and suggestions. If you like the project do share it like on github.