
---
title: "Comparison of advanced NLP tools for chatbots"
date: 2018-09-12T12:52:36+06:00
image_webp: uploads/2015/05/Sound-269x180_c.jpg
image: uploads/2015/05/Sound-269x180_c.jpg
author: 
description : ""
---

*“Chatbots represent a new trend in how people access information, make decisions, and communicate. We think that chatbots are the beginning of a new form of digital access, which centers on messaging. Messaging has become a huge component of how we interact with our devices, and how we stay connected with the people, businesses and the day-to-day activities of life. Chatbots bring commerce into this part of our lives, and will open up new opportunities.”  – [Christie Pitts](https://www.linkedin.com/in/christiepitts), Manager, Verizon Ventures*

We explored various NLP engine for chatbots and here is the comparison of prominent NLP tools based on our experience/understanding.

  
||||||
|--- |--- |--- |--- |--- |
|  **Feature**  |**Facebook wit.ai**|**Microsoft luis.ai**|**IBM Watson language classifier**|**api.ai**|
|  **Price**  |   Free/no limitations   |   Free (in beta) up to 10k transactions per month, 5 requestsper second, per account   |     First classifier is FREE. Each additional classifier is $20.00 per month.First one thousand API calls per month are FREE. Additional calls are $0.0035 per call.First four training events per month are FREE. Additional training events are $3.00 per training event.   |  Free up to 6,000 requests,Enterprise starts at $89 USD per month  |
|  **Ease of training**  |   Web based interface. Could not find option to import already trained model   |   Easy to use web based interface. Ability to import utterances.   |  Need to provide the data to train the Natural Language Classifier in comma-separated value (CSV) format specified on the website.|  Easy to use web based interface. Ability to import intents and entities.  |
|  **Pre-built features/entity**  |   It has pre-built entities like datetime, duration, location, number, amount_of_money, phone number, url, email,|   It has pre-built entities like number(in number or text), temperature, dimensions, money, age, geography, encyclopedia, percentage and datetime|There is no single API that does intent and entity recognition in a single call, this is inconvenient since you have to build your own pipeline with multiple API calls to extract all the information you need and it’s harder to link entities to intent|  built-in domains of knowledge (Intents with Entities and even suggested Replies ) on topics like small talk, weather, apps or even wisdom.  |
|   **Integration effort**  |  No integration module, webservice API   |   Integration into MS Azure andother services, deployable in anysupported servers|There are a lot of building blocks that you can use in your application, but you probably will spend a decent amount of time integrating them into one solution.   |   Integration module to connect to messenger APIs. Support fordeploying into Heroku server,enterprise paid environment   |
|  **API**  |   Wit.ai API for iOS, Android,Nod.js, Raspberry Pi, Ruby,Python, C, Rust and Windowsphone   |   No coding needed  |  For simple scripted conversation, IBM provides the Dialog API. Dialog API is not integrated with text understanding APIs and you may need to write thousands of line of XML to build a simple app    |   SDKs for Android, iOS, AppleWatch, Node.js, Cordova, Unity,C#, Xamarin, Windows phone,Python and JS    |
|  **Content addition and updating**  |  Web based interface to updated/add new entity/chat flow   |  Web based interface to update/delete/add intent/entity  |     There is no single API that does intent and entity recognition in a single call.    |  Web based interface to update/delete/add intent/entity     |
|  **Notes**  |  Wit.ai supports 50 different languages including English, Chinese, Japanese, Polish, Ukrainian and RussianProvides a nice combination of both voice recognition and machine learning for developers.    ||  The classifier supports English (en), Arabic (ar), French (fr), German (de), Japanese (ja), Italian (it), Portuguese (pt), and Spanish (es).      |S  peech to Text and Text to Speech capabilities, along with machine  learning.     |  

<pre>
hello, this is
   just an     example



....
</pre>
&nbsp;
&nbsp;

#### Resources and further reading:  

[http://stackoverflow.com/questions/37215188/comparison-between-luis-ai-vs-api-ai-vs-wit-ai](http://stackoverflow.com/questions/37215188/comparison-between-luis-ai-vs-api-ai-vs-wit-ai)  


[http://blogs.aspect.com/bot-framework-s-comparison/](http://blogs.aspect.com/bot-framework-s-comparison/)  

[https://stanfy.com/blog/advanced-natural-language-processing-tools-for-bot-makers/](https://stanfy.com/blog/advanced-natural-language-processing-tools-for-bot-makers/)  

[https://medium.com/@Conversate/natural-language-apis-for-bots-e791f090e32f#.p8jw54m5h](https://medium.com/@Conversate/natural-language-apis-for-bots-e791f090e32f#.p8jw54m5h)  

