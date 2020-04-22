Comparison of advanced NLP tools for chatbots | EXPERIENCESUTRA                         Comparison of advanced NLP tools for chatbots | EXPERIENCESUTRA     window.\_wpemojiSettings = {"baseUrl":"http:\\/\\/s.w.org\\/images\\/core\\/emoji\\/72x72\\/","ext":".png","source":{"concatemoji":"http:\\/\\/experiencesutra.com\\/wp-includes\\/js\\/wp-emoji-release.min.js?ver=4.2.2"}}; !function(a,b,c){function d(a){var c=b.createElement("canvas"),d=c.getContext&&c.getContext("2d");return d&&d.fillText?(d.textBaseline="top",d.font="600 32px Arial","flag"===a?(d.fillText(String.fromCharCode(55356,56812,55356,56807),0,0),c.toDataURL().length>3e3):(d.fillText(String.fromCharCode(55357,56835),0,0),0!==d.getImageData(16,16,1,1).data\[0\])):!1}function e(a){var c=b.createElement("script");c.src=a,c.type="text/javascript",b.getElementsByTagName("head")\[0\].appendChild(c)}var f,g;c.supports={simple:d("simple"),flag:d("flag")},c.DOMReady=!1,c.readyCallback=function(){c.DOMReady=!0},c.supports.simple&&c.supports.flag||(g=function(){c.readyCallback()},b.addEventListener?(b.addEventListener("DOMContentLoaded",g,!1),a.addEventListener("load",g,!1)):(a.attachEvent("onload",g),b.attachEvent("onreadystatechange",function(){"complete"===b.readyState&&c.readyCallback()})),f=c.source||{},f.concatemoji?e(f.concatemoji):f.wpemoji&&f.twemoji&&(e(f.twemoji),e(f.wpemoji)))}(window,document,window.\_wpemojiSettings);   img.wp-smiley, img.emoji { display: inline !important; border: none !important; box-shadow: none !important; height: 1em !important; width: 1em !important; margin: 0 .07em !important; vertical-align: -0.1em !important; background: none !important; padding: 0 !important; }                 /\* <!\[CDATA\[ \*/ var ot = {"THEME\_NAME":"tresor","THEME\_FULL\_NAME":"Tresor","adminUrl":"http:\\/\\/experiencesutra.com\\/wp-admin\\/admin-ajax.php","gallery\_id":"","galleryCat":"","imageUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/images\\/","cssUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/css\\/","themeUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme"}; /\* \]\]> \*/             var \_gaq = \_gaq || \[\]; \_gaq.push(\['\_setAccount', 'UA-63333235-1'\]); \_gaq.push(\['\_trackPageview'\]); (function() { var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true; ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js'; var s = document.getElementsByTagName('script')\[0\]; s.parentNode.insertBefore(ga, s); })();     

.wpb\_animate\_when\_almost\_visible { opacity: 1; }

*   [![EXPERIENCESUTRA](/wp-content/themes/tresor-theme/images/logo.png)](http://experiencesutra.com/)

*   [PURPOSE](http://experiencesutra.com/purpose/)
*   [PEOPLE](http://experiencesutra.com/people/)
*   [SPACE](http://experiencesutra.com/gallery/space/)
*   [ABOUT US](http://experiencesutra.com/about-us/)

 [Show menu](#dat-menu)

*   [HOME](http://experiencesutra.com/)
*   [PROJECTS](http://experiencesutra.com/category/projects/)
*   [INSIGHTS](http://experiencesutra.com/category/insights/)
*   [EXPERIMENTS](http://experiencesutra.com/category/experiments/)
*   [SCRIBBLES](http://experiencesutra.com/category/scribbles/)
*   [CONTACT US](http://experiencesutra.com/contact-us/)

*   [Home](http://experiencesutra.com)
*   [EXPERIMENTS](http://experiencesutra.com/category/experiments/)
*   Comparison of advanced NLP tools for chatbots

Articles
--------

Comparison of advanced NLP tools for chatbots
---------------------------------------------

[EXPERIMENTS](http://experiencesutra.com/category/experiments/)

>  “Chatbots represent a new trend in how people access information, make decisions, and communicate. We think that chatbots are the beginning of a new form of digital access, which centers on messaging. Messaging has become a huge component of how we interact with our devices, and how we stay connected with the people, businesses and the day-to-day activities of life. Chatbots bring commerce into this part of our lives, and will open up new opportunities.”  – [Christie Pitts](https://www.linkedin.com/in/christiepitts), Manager, Verizon Ventures

We explored various NLP engine for chatbots and here is the comparison of prominent NLP tools based on our experience/understanding.

**Feature**

[Facebook wit.ai](https://wit.ai/home)

[Microsoft luis.ai](https://www.luis.ai/)

[IBM Watson language classifier](https://www.ibm.com/watson/developercloud/nl-classifier.html)

[api.ai](https://api.ai/)

**Price**

Free/no limitations

Free (in beta) up to 10k transactions per month, 5 requestsper second, per account

First classifier is FREE. Each additional classifier is $20.00 per month.First one thousand API calls per month are FREE. Additional calls are $0.0035 per call.First four training events per month are FREE. Additional training events are $3.00 per training event.

Free up to 6,000 requests,Enterprise starts at $89 USD per month

**Ease of training**

Web based interface. Could not find option to import already trained model

Easy to use web based interface. Ability to import utterances.

Need to provide the data to train the Natural Language Classifier in comma-separated value (CSV) format specified on the website.

Easy to use web based interface. Ability to import intents and entities.

**Pre-built features/entity**

It has pre-built entities like datetime, duration, location, number, amount\_of\_money, phone number, url, email,

It has pre-built entities like number(in number or text), temperature, dimensions, money, age, geography, encyclopedia, percentage and datetime

There is no single API that does intent and entity recognition in a single call, this is inconvenient since you have to build your own pipeline with multiple API calls to extract all the information you need and it’s harder to link entities to intent

built-in domains of knowledge (Intents with Entities and even suggested Replies ) on topics like small talk, weather, apps or even wisdom.

**Integration effort**

No integration module, webservice API

Integration into MS Azure andother services, deployable in anysupported servers

There are a lot of building blocks that you can use in your application, but you probably will spend a decent amount of time integrating them into one solution.

Integration module to connect to messenger APIs. Support fordeploying into Heroku server,enterprise paid environment

**API**

Wit.ai API for iOS, Android,Nod.js, Raspberry Pi, Ruby,Python, C, Rust and Windowsphone

No coding needed

For simple scripted conversation, IBM provides the Dialog API. Dialog API is not integrated with text understanding APIs and you may need to write thousands of line of XML to build a simple app

SDKs for Android, iOS, AppleWatch, Node.js, Cordova, Unity,C#, Xamarin, Windows phone,Python and JS

**Content addition and updating**

Web based interface to updated/add new entity/chat flow

Web based interface to update/delete/add intent/entity

There is no single API that does intent and entity recognition in a single call.

Web based interface to update/delete/add intent/entity

**Notes**

Wit.ai supports 50 different languages including English, Chinese, Japanese, Polish, Ukrainian and RussianProvides a nice combination of both voice recognition and machine learning for developers.

The classifier supports English (en), Arabic (ar), French (fr), German (de), Japanese (ja), Italian (it), Portuguese (pt), and Spanish (es).

Speech to Text and Text to Speech capabilities, along with machine  learning.

**Resources and further reading:**

[http://stackoverflow.com/questions/37215188/comparison-between-luis-ai-vs-api-ai-vs-wit-ai](http://stackoverflow.com/questions/37215188/comparison-between-luis-ai-vs-api-ai-vs-wit-ai)

[http://blogs.aspect.com/bot-framework-s-comparison/](http://blogs.aspect.com/bot-framework-s-comparison/)

[https://stanfy.com/blog/advanced-natural-language-processing-tools-for-bot-makers/](https://stanfy.com/blog/advanced-natural-language-processing-tools-for-bot-makers/)

[https://medium.com/@Conversate/natural-language-apis-for-bots-e791f090e32f#.p8jw54m5h](https://medium.com/@Conversate/natural-language-apis-for-bots-e791f090e32f#.p8jw54m5h)

[Featured ![Improving Colour based filtering results for Interactive Mirror Installation](http://experiencesutra.com/wp-content/uploads/2018/05/Mirror_StoryBoard_02MAY18-397x310_c.jpg)   EXPERIMENTS **Improving Colour based filtering results for Interactive Mirror Installation**  by Mayank Jain  •](http://experiencesutra.com/experiments/improving-colour-based-filtering-results-for-interactive-mirror-installation/) 

[Featured ![Chorus – A Music Jamming Experience](http://experiencesutra.com/wp-content/uploads/2018/09/IMG_20180903_153109_HDR-397x310_c.jpg)   EXPERIMENTS **Chorus – A Music Jamming Experience**](http://experiencesutra.com/experiments/chorus-a-music-jamming-experience/) 

[Tweets by @keplervaani](https://twitter.com/twitterdev)

Socialize
---------

[**0**_Shares_](http://www.facebook.com/sharer/sharer.php?u=http://experiencesutra.com) [**0**_Tweets_](#) [**0**_+1's_](https://plus.google.com/share?url=http://experiencesutra.com) [**0**_Shares_](http://www.linkedin.com/shareArticle?mini=true&url=http://experiencesutra.com&title=EXPERIENCESUTRA+-+Humanizing+Technology)

EXPERIENCESUTRA
---------------

Humanizing technology  
© 2016 - Kepler186f

[Close Window](#)

### Loading, Please Wait!

This may take a second or two. ![Loading, Please Wait!](http://experiencesutra.com/wp-content/themes/tresor-theme/images/loading.gif "Loading, Please Wait!")