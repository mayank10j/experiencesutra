Contraption | EXPERIENCESUTRA                         Contraption | EXPERIENCESUTRA     window.\_wpemojiSettings = {"baseUrl":"http:\\/\\/s.w.org\\/images\\/core\\/emoji\\/72x72\\/","ext":".png","source":{"concatemoji":"http:\\/\\/experiencesutra.com\\/wp-includes\\/js\\/wp-emoji-release.min.js?ver=4.2.2"}}; !function(a,b,c){function d(a){var c=b.createElement("canvas"),d=c.getContext&&c.getContext("2d");return d&&d.fillText?(d.textBaseline="top",d.font="600 32px Arial","flag"===a?(d.fillText(String.fromCharCode(55356,56812,55356,56807),0,0),c.toDataURL().length>3e3):(d.fillText(String.fromCharCode(55357,56835),0,0),0!==d.getImageData(16,16,1,1).data\[0\])):!1}function e(a){var c=b.createElement("script");c.src=a,c.type="text/javascript",b.getElementsByTagName("head")\[0\].appendChild(c)}var f,g;c.supports={simple:d("simple"),flag:d("flag")},c.DOMReady=!1,c.readyCallback=function(){c.DOMReady=!0},c.supports.simple&&c.supports.flag||(g=function(){c.readyCallback()},b.addEventListener?(b.addEventListener("DOMContentLoaded",g,!1),a.addEventListener("load",g,!1)):(a.attachEvent("onload",g),b.attachEvent("onreadystatechange",function(){"complete"===b.readyState&&c.readyCallback()})),f=c.source||{},f.concatemoji?e(f.concatemoji):f.wpemoji&&f.twemoji&&(e(f.twemoji),e(f.wpemoji)))}(window,document,window.\_wpemojiSettings);   img.wp-smiley, img.emoji { display: inline !important; border: none !important; box-shadow: none !important; height: 1em !important; width: 1em !important; margin: 0 .07em !important; vertical-align: -0.1em !important; background: none !important; padding: 0 !important; }                 /\* <!\[CDATA\[ \*/ var ot = {"THEME\_NAME":"tresor","THEME\_FULL\_NAME":"Tresor","adminUrl":"http:\\/\\/experiencesutra.com\\/wp-admin\\/admin-ajax.php","gallery\_id":"","galleryCat":"","imageUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/images\\/","cssUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/css\\/","themeUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme"}; /\* \]\]> \*/             var \_gaq = \_gaq || \[\]; \_gaq.push(\['\_setAccount', 'UA-63333235-1'\]); \_gaq.push(\['\_trackPageview'\]); (function() { var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true; ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js'; var s = document.getElementsByTagName('script')\[0\]; s.parentNode.insertBefore(ga, s); })();     

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
*   Contraption

Articles
--------

Contraption
-----------

[vasu Agrawal](http://experiencesutra.com/author/vagrawal9/ "Posts by vasu Agrawal") [EXPERIMENTS](http://experiencesutra.com/category/experiments/)

We all strive for great output, don’t we? Our entire work lives revolve around achieving targets, meeting expectations and on most instances, performing beyond them. Walking through these self imposed peaks of professional competency, how many of us do actually end up enjoying the journey – to get there, but watch some trees and lakes as we drive past?

The Contraption is one such experiment conducted by Kepler to highlight the importance of the process. Through this we look to communicate that the simplest of tasks, even the ones that are taken for granted, have a beautiful process running in the background which is completely lost on us. Once we get a peek into this very process, things start to make more sense and the value of the output takes a new height of excitement.

This contraption is a Rube Goldberg machine which combines various elements like Chain Reactions, Marble Machines and a combination of sensors and maker electronics to create a complex chain of actions to fulfil a simple task – take a selfie.

_The Journey_

One of the core ideas was to create a chain reaction using off-topic elements. The user performs a completely unrelated action of pressing a bicycle pump to start the experience. This activates a flap switch which activates levitating ping-pong ball. Next up is a swing-arm mechanism which releases a steel ball through a funnel on to a marble track. A spot light also turns on at this stage, throwing light onto the next segment of the track.

The steel ball travels some distance, changing levels on a double storied path with lifting mechanisms. The ball then falls through a pipe onto a plate which triggers off another spot light onto the third segment of the journey.

Here, some more distance is covered on a marble track before the steel ball is raised by one level and directed onto a domino set. These dominos fall to trigger off the digital segment of the experience where a short animation leads onto a clapboard, setting off spot light number 3.

This final spot light activates a Robotic arm to click a picture of the person standing at the bicycle pump and a style transfer algorithm running at the backend applies a filter to the picture taken and projects it onto the wall in front of the user – thus taking the perfect Selfie.

[http://experiencesutra.com/wp-content/uploads/2018/01/Contraption\_for-Blogpost.m4v](http://experiencesutra.com/wp-content/uploads/2018/01/Contraption_for-Blogpost.m4v)

_The Hardware_

The entire circuit is controlled using an Arduino.

The levitating ping pong ball is made using a blower fan and covering it with a channel. This mechanism also houses an LDR which picks up the trigger for opening the swing arm and switching on light #1 and lift mechanisms #1 and #2.

As the ball drops through the pipe, it lands on to a piezo sensor which triggers light #2 and the third lift mechanism.

The dominos are made off cut Aluminum plates and assembled in such a way that their reset time is less than 20seconds.

Another LDR on light #3 triggers off the Robotic arm made using a Lego Mindstorm kit and converted into a keyboard action using a Makey-Makey kit. And finally, the last piece of technology, which manages the style transfer using Neural Networks to apply the look & feel of one image to another.

This experiment done recently at Kepler was a great combination of enormous amounts of fun as well as a lot of hands-on-learning of bringing together puzzle pieces from different domains and stitching them together to create a fresh perspective on things. The beauty of the whole experience being the scalability it offers to be implemented across countless applications and across all user segments – definitely making it a potentially great tool for brand stories.

![vasu Agrawal](http://2.gravatar.com/avatar/55d6e9d5d2d5e5699239c3afa99af9ee?s=100&d=mm&r=g)

### vasu Agrawal

[View more by vasu Agrawal](http://experiencesutra.com/author/vagrawal9/)

[Featured ![ZooYou](http://experiencesutra.com/wp-content/uploads/2015/12/Zooyou-397x310_c.png)   EXPERIMENTS **ZooYou**](http://experiencesutra.com/experiments/zooyou/) 

[Featured ![De-Stress Time with Muse and Oculus Rift DK2](http://experiencesutra.com/wp-content/uploads/2017/08/brainwavefrequencies_v2crop1-397x310_c.png)   EXPERIMENTS **De-Stress Time with Muse and Oculus Rift DK2**](http://experiencesutra.com/experiments/de-stress-time-with-choosemuse-headband-and-oculus-rift-dk2/) 

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

                      /\* <!\[CDATA\[ \*/ var mejsL10n = {"language":"en","strings":{"Close":"Close","Fullscreen":"Fullscreen","Download File":"Download File","Download Video":"Download Video","Play\\/Pause":"Play\\/Pause","Mute Toggle":"Mute Toggle","None":"None","Turn off Fullscreen":"Turn off Fullscreen","Go Fullscreen":"Go Fullscreen","Unmute":"Unmute","Mute":"Mute","Captions\\/Subtitles":"Captions\\/Subtitles"}}; var \_wpmejsSettings = {"pluginPath":"\\/wp-includes\\/js\\/mediaelement\\/"}; /\* \]\]> \*/