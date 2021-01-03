+++
author = ""
date = 2019-10-08T18:30:00Z
description = ""
image = "/uploads/2021/01/03/katna-1.png"
image_webp = "/uploads/2021/01/03/katna.png"
title = "Smart Image Cropping with katna"

+++
Some of the simple tasks for humans can be very tedious for machines. Image cropping is one of them. It's quite easy for human to identify the important area in a photo and decide the parts to retain or crop. But for machines, it is quite difficult.

[Katna](https://github.com/keplerlab/katna) is a python based open source smart image cropping tool that can intelligently identify important elements of an image and retain it during cropping. Katna content — aware algorithm can also retain important texts in the image.

![](/uploads/2021/01/03/katna_crop1.jpg)

![](/uploads/2021/01/03/katna_crop_2.png)

The best way to learn about Katna smart cropping module is to actually use it.

The best way to learn about Katna smart cropping module is to actually use it.

**Installation**

Katna can be installed either via PyPI or directly from source.

**_PyPI_ —** Installation via PyPI is pretty straight forward

* Install python 3
* Install with pip
```
pip install katna
```
**_Install from source_ —** Follow the steps below

* Install git.
* Install python 3.
* Clone the git repo.
```
git clone https://github.com/keplerlab/Katna.git
```
Change the current working directory to the folder where you have cloned Katna repo.
```
cd <<path_to_the_folder_repo_cloned>>
```
If you use the anaconda python distribution then create a new conda environment. Keeping environment separate is a good practice.
```
conda create --name katna python=3
source activate katna
```
Run the setup
```
python setup.py install
```
# How to use katna image module

Import the video module from the katna library
```
from Katna.image import Image
```
Instantiate the image class.
```
img_module = Image()
```
Image class offers different cropping methods for different inputs. here is a quick list of different cropping methods

1. **crop_image:** — To crop an image file. This function is useful when you have bunch of images to be cropped.
2. **crop_image_from_cvimage: —** To crop an in-memory image file. The in-memory image needs to be numpy array. This is useful for workflows integrations.
3. **crop_image_with_aspect: —** To crop an image based on aspect ratio. Please note the difference from crop_image method. crop_image crops using width and height whereas crop_aspect_ratio uses aspect ratio for cropping.

Let us look at the function definitions now.

**crop_image** — . This method accepts 6 parameters and returns a list of images as numpy 2D array. Below are the six parameters of the function.

1. **file_path**: image file path from which crop has to be extracted.
2. **crop_width**: width of crop to extract.
3. **crop_height**: height of crop to extract.
4. **no_of_crops_to_returned**: number of crops rectangles to be extracted
5. **filters**: You can use this **optional** parameter to specify image parts/objects that should be retained in the cropped image. At the moment only “text” retention filter is present. A text filter attempts to retain the texts in the image. Newer retention filters will be added in future. By default, filters are not applied.
6. **down_sample_factor**: You can use this **optional** feature to specify the downsampling factor. For large images consider increasing this parameter for fast image cropping. By default input images are downsampled by factor of **8** before processing.

```
# number of images to be returned
 no_of_crops = 3

 # crop dimensions
 crop_width = 1000
 crop_height = 600

 # Filters
 filters = ["text"]sampling_factor = 12image_file_path = <Path where the image is stored>

crop_list = img_module.crop_image(
   file_path=image_file_path,
   crop_width=crop_width,
   crop_height=crop_height,
   num_of_crops= no_of_crops,
   filters=filters,
   down_sample_factor = sampling_factor
)
```

**crop_image_from_cvimage —** It accepts opencv image as image source, rest of the parameters are same as _crop_image_ function.

1. **input_image:** in-memory image as numpy array.
2. crop_width
3. crop_height
4. no_of_crops_to_returned
5. filters
6. down_sample_factor

**crop_image_with_aspect —** It accepts the aspect ratio for cropping dimension. Rest of the parameters are same as _crop_image_

1. file_path
2. **crop_aspect_ratio**: aspect ratio in string format (for e.g. ‘4:3’ or ‘16:9’)by which crops need to be extracted.
3. no_of_crops_to_returned
4. filters
5. down_sample_factor

# How katna image module works

All possible crops from the input image for the crop size is selected and passed through set of filters — [The rule of third](https://www.photographymad.com/pages/view/rule-of-thirds), [Saliency](https://blog.algorithmia.com/introduction-image-saliency-detection), face detection and edge detection. Images shown below are filter output of an image. Each of the filter gives a score to the crops. If the text retention filter is switched on then it filters out crops that cuts the text. The final emerging crops are sorted and then numbers of crops requested by the caller are returned.

# What’s next

We plan to add more filters in future like violence, nudity etc. to make it more robust.

We are thankful to open source community and project [smartcrop](https://github.com/jwagner/smartcrop.js/) especially that enabled us to reuse and the take good ideas forward. If you find the tool useful please do share the project.

That’s it!! You can find a complete application [here](https://github.com/keplerlab/katna/blob/master/example_image.py).

