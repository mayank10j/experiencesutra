IMI on ODROID XU4 | EXPERIENCESUTRA                         IMI on ODROID XU4 | EXPERIENCESUTRA     window.\_wpemojiSettings = {"baseUrl":"http:\\/\\/s.w.org\\/images\\/core\\/emoji\\/72x72\\/","ext":".png","source":{"concatemoji":"http:\\/\\/experiencesutra.com\\/wp-includes\\/js\\/wp-emoji-release.min.js?ver=4.2.2"}}; !function(a,b,c){function d(a){var c=b.createElement("canvas"),d=c.getContext&&c.getContext("2d");return d&&d.fillText?(d.textBaseline="top",d.font="600 32px Arial","flag"===a?(d.fillText(String.fromCharCode(55356,56812,55356,56807),0,0),c.toDataURL().length>3e3):(d.fillText(String.fromCharCode(55357,56835),0,0),0!==d.getImageData(16,16,1,1).data\[0\])):!1}function e(a){var c=b.createElement("script");c.src=a,c.type="text/javascript",b.getElementsByTagName("head")\[0\].appendChild(c)}var f,g;c.supports={simple:d("simple"),flag:d("flag")},c.DOMReady=!1,c.readyCallback=function(){c.DOMReady=!0},c.supports.simple&&c.supports.flag||(g=function(){c.readyCallback()},b.addEventListener?(b.addEventListener("DOMContentLoaded",g,!1),a.addEventListener("load",g,!1)):(a.attachEvent("onload",g),b.attachEvent("onreadystatechange",function(){"complete"===b.readyState&&c.readyCallback()})),f=c.source||{},f.concatemoji?e(f.concatemoji):f.wpemoji&&f.twemoji&&(e(f.twemoji),e(f.wpemoji)))}(window,document,window.\_wpemojiSettings);   img.wp-smiley, img.emoji { display: inline !important; border: none !important; box-shadow: none !important; height: 1em !important; width: 1em !important; margin: 0 .07em !important; vertical-align: -0.1em !important; background: none !important; padding: 0 !important; }                 /\* <!\[CDATA\[ \*/ var ot = {"THEME\_NAME":"tresor","THEME\_FULL\_NAME":"Tresor","adminUrl":"http:\\/\\/experiencesutra.com\\/wp-admin\\/admin-ajax.php","gallery\_id":"","galleryCat":"","imageUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/images\\/","cssUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/css\\/","themeUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme"}; /\* \]\]> \*/             var \_gaq = \_gaq || \[\]; \_gaq.push(\['\_setAccount', 'UA-63333235-1'\]); \_gaq.push(\['\_trackPageview'\]); (function() { var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true; ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js'; var s = document.getElementsByTagName('script')\[0\]; s.parentNode.insertBefore(ga, s); })();     

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
*   IMI on ODROID XU4

Articles
--------

IMI on ODROID XU4
-----------------

[EXPERIMENTS](http://experiencesutra.com/category/experiments/)

> _IMI can now run on single board computer peripherals …_

This is a follow up post to our previous blog post [Mirror Reimagined](http://experiencesutra.com/projects/the-mirror-reimagined_-a-smart-shopping-assistant-for-the-retail/), which was about Sapient smart mirror application IMI developed here in Kepler. A quick recap – IMI generates the apparel recommendation in the physical store based on what you wear/ show in front of it.

This post is about two things: adding personalized _Experience Zone_ capabilities in IMI and porting the entire IMI application on a single board computer like ODROID or RPI.

The _Experience Zone_ comprise of two features: _Companion_ and _Lighting_. The former allows users to record themselves in an outfit and compare the recordings side by side while the latter enables them to see the outfit in various lighting conditions. This is a personalized experience and is mapped to a token ID valid for 3 hours. This means all your recordings will be available to you under a temporary token.

* * *

We wanted to run entire IMI application on a single board computer. What this means is that all the capability of AI powered recommendation engine, and your personalized experience zone will be available to you in a low powered, low cost device. We chose ODROID XU4 over RPi because it has more RAM, and also supports hardware based GPU acceleration for Chromium browser, which is required to support good quality video recordings. We expected that porting our code on ODROID would be a simple task of plug and play, but while working on it, we encountered the following problems:

1.  By default ODROID use _armsoc_ as its graphic driver, which doesn’t support screen rotation feature. Screen rotation was a major concern because, our mirror template runs on a display rotated by 90 degrees. Check out [ODROID screen rotation issues](https://forum.odroid.com/viewtopic.php?f=8&t=2440) for more detail.
2.  We tried another graphic driver  _fbdev,_ but it doesn’t has capabilities to use hardware based graphic acceleration, which resulted in poor user experience.
3.   The videos recorded with _fbdev_ had a frame rate of about 5-10 fps, resulting in laggy videos.
4.  ODROID also had issues utilizing  _ffmpeg_. With XU4 we were unable to decode _.webm_ files using vp8 codec. we used _ffmpeg_ to convert ._webm_ files to _.mp4_ (a de facto for videos).

To resolve these issues, we had to do the following:

1.  Move video conversion out of the ODROID device.
2.  Use a different operating system, and shift from Ubuntu.

Doing the above helped us resolve all the issues. Our Video conversion ran on a different machine, and posed no problems at all. The Android images had in built ODROID utility, which supported screen rotation, and the driver also make utilization of hardware based acceleration. In case you are wondering how will installed our application on Android, we used an application _Termux ([Termux Emulator App](https://termux.com)), which enabled us use apt-get on our system._

[Featured ![CreateAR – when, AR and AI meet](http://experiencesutra.com/wp-content/uploads/2019/05/Screen-Shot-2019-05-02-at-10.36.09-AM-397x310_c.png)   EXPERIMENTS **CreateAR – when, AR and AI meet**](http://experiencesutra.com/experiments/createar-when-ar-and-ai-meet/) 

[Featured ![Mobile deployment of deep learning models](http://experiencesutra.com/wp-content/uploads/2018/09/AR-397x310_c.jpeg)   EXPERIMENTS **Mobile deployment of deep learning models**](http://experiencesutra.com/experiments/mobile-deployment-of-deep-learning-models/) 

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