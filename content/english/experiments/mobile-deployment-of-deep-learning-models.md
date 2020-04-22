Mobile deployment of deep learning models | EXPERIENCESUTRA                         Mobile deployment of deep learning models | EXPERIENCESUTRA     window.\_wpemojiSettings = {"baseUrl":"http:\\/\\/s.w.org\\/images\\/core\\/emoji\\/72x72\\/","ext":".png","source":{"concatemoji":"http:\\/\\/experiencesutra.com\\/wp-includes\\/js\\/wp-emoji-release.min.js?ver=4.2.2"}}; !function(a,b,c){function d(a){var c=b.createElement("canvas"),d=c.getContext&&c.getContext("2d");return d&&d.fillText?(d.textBaseline="top",d.font="600 32px Arial","flag"===a?(d.fillText(String.fromCharCode(55356,56812,55356,56807),0,0),c.toDataURL().length>3e3):(d.fillText(String.fromCharCode(55357,56835),0,0),0!==d.getImageData(16,16,1,1).data\[0\])):!1}function e(a){var c=b.createElement("script");c.src=a,c.type="text/javascript",b.getElementsByTagName("head")\[0\].appendChild(c)}var f,g;c.supports={simple:d("simple"),flag:d("flag")},c.DOMReady=!1,c.readyCallback=function(){c.DOMReady=!0},c.supports.simple&&c.supports.flag||(g=function(){c.readyCallback()},b.addEventListener?(b.addEventListener("DOMContentLoaded",g,!1),a.addEventListener("load",g,!1)):(a.attachEvent("onload",g),b.attachEvent("onreadystatechange",function(){"complete"===b.readyState&&c.readyCallback()})),f=c.source||{},f.concatemoji?e(f.concatemoji):f.wpemoji&&f.twemoji&&(e(f.twemoji),e(f.wpemoji)))}(window,document,window.\_wpemojiSettings);   img.wp-smiley, img.emoji { display: inline !important; border: none !important; box-shadow: none !important; height: 1em !important; width: 1em !important; margin: 0 .07em !important; vertical-align: -0.1em !important; background: none !important; padding: 0 !important; }                 /\* <!\[CDATA\[ \*/ var ot = {"THEME\_NAME":"tresor","THEME\_FULL\_NAME":"Tresor","adminUrl":"http:\\/\\/experiencesutra.com\\/wp-admin\\/admin-ajax.php","gallery\_id":"","galleryCat":"","imageUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/images\\/","cssUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/css\\/","themeUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme"}; /\* \]\]> \*/             var \_gaq = \_gaq || \[\]; \_gaq.push(\['\_setAccount', 'UA-63333235-1'\]); \_gaq.push(\['\_trackPageview'\]); (function() { var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true; ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js'; var s = document.getElementsByTagName('script')\[0\]; s.parentNode.insertBefore(ga, s); })();     

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
*   Mobile deployment of deep learning models

Articles
--------

Mobile deployment of deep learning models
-----------------------------------------

[EXPERIMENTS](http://experiencesutra.com/category/experiments/)

With the proliferation of deep learning libraries, we are facing the paradox of choices, there are so many different libraries where we can train our deep learning models. To choose one of these is giving us lots of anxiety.

We can use some of the comparatively old but still very powerful [caffe](http://caffe.berkeleyvision.org/) , [Theanao](https://github.com/Theano/Theano) or [torch](http://torch.ch/), or you can join cutting edge deep learning research by becoming part of [Tensorflow](https://www.tensorflow.org/), [Pytorch](https://github.com/pytorch/pytorch) or [MxNet](https://mxnet.apache.org/) community, as always devil lies in details. Hence we set out on a journey for finding out which library would be best suited for our newest secret Augmented reality experience.

The problem statement was simple: How to classify between some unique items on top of the table, to be specific a floppy drive, Pizo, Stepper motor, and Relay. But constraint was that the trained model should be able to run on alongside ios arkit with good accuracy. Preferable able to use hardware acceleration using ios coreml neural network format. Why do we have such unique requirements and why do we need to classify between these weird items is a suspense which would be revealed in our upcoming blog posts ;-).

We started out with FastAI / PyTorch combo so for people who do not know fastai is library written on top of pytorch which enables writing industry grade deep learning models in the minimal line of codes. Writing deep learning model this way enables us to get optimal accuracy in a short span of time. [http://www.fast.ai/](http://www.fast.ai/) also host a very popular MOOC course which incidentally we are also using for our AI Saturdays initiatives. We were able to get quite a good accuracy for our collected data on fastai with accuracy after transfer learning with resnet64 in range of 98 percent.  One of the recommended ways for converting FastAI/Pytorch trained models in mobile devices is using Onyxx which is being a universal way for neural network compatibility, so ideally they way convert pytorch model is pytorch -> Onnyx and then onnyx to coreML for iOS or Caffe2 for android. while trying to convert pytorch model to onnyx we stumbled on a bottleneck that some of the functions namely dynamic avg pooling is not supported on onnyx for now. After a lot of debugging and web search, we concluded that pytorch is not suitable for now for mobile porting as these features are still being worked upon. So we had to move on to other approaches.

So next we used one interesting project called [turicreate](https://github.com/apple/turicreate) which is an ML library written in-house at apple and support direct export of coreML models. ( coreML is official neural network format for running on iOS if you want to use hardware acceleration)

So we were able to use our training data for mobilenet transfer learning in turicreate and able to integrate with our new secret app/project. But on testing, it’s accuracy we found it less than satisfactory. This we confirmed with the online community. There is a general consensus that neural networks trained on turicrete sometimes gives suboptimal accuracy. So our recommendation, for now, for anybody exploring turicrete is to re-confirm results obtained from turicreate with more mature libraries like tensorflow etc.

So, at last, we used Tensorflow for training and able to convert tensorflow modlel to coreML using this project [tf-coreml](https://github.com/tf-coreml/tf-coreml) . After initial hiccups, we were able to run the whole network with quite a good accuracy on mobile. You can see the results:

![Mayank Jain](http://2.gravatar.com/avatar/e4f97426870388bd7c4b8ca3ffd06fb7?s=100&d=mm&r=g)

### Mayank Jain

[View more by Mayank Jain](http://experiencesutra.com/author/mjain/)

[Featured ![Contraption](http://experiencesutra.com/wp-content/uploads/2018/01/Pic_for-Blogpost-397x310_c.jpg)   EXPERIMENTS **Contraption**  by vasu Agrawal  •](http://experiencesutra.com/experiments/contraption/) 

[Featured ![Comparison of advanced NLP tools for chatbots](http://experiencesutra.com/wp-content/uploads/2015/05/Sound-397x310_c.jpg)   EXPERIMENTS **Comparison of advanced NLP tools for chatbots**](http://experiencesutra.com/experiments/comparison-of-advanced-nlp-tools-for-chatbots/) 

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