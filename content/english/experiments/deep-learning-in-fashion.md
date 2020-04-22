Deep Learning in Fashion | EXPERIENCESUTRA                         Deep Learning in Fashion | EXPERIENCESUTRA     window.\_wpemojiSettings = {"baseUrl":"http:\\/\\/s.w.org\\/images\\/core\\/emoji\\/72x72\\/","ext":".png","source":{"concatemoji":"http:\\/\\/experiencesutra.com\\/wp-includes\\/js\\/wp-emoji-release.min.js?ver=4.2.2"}}; !function(a,b,c){function d(a){var c=b.createElement("canvas"),d=c.getContext&&c.getContext("2d");return d&&d.fillText?(d.textBaseline="top",d.font="600 32px Arial","flag"===a?(d.fillText(String.fromCharCode(55356,56812,55356,56807),0,0),c.toDataURL().length>3e3):(d.fillText(String.fromCharCode(55357,56835),0,0),0!==d.getImageData(16,16,1,1).data\[0\])):!1}function e(a){var c=b.createElement("script");c.src=a,c.type="text/javascript",b.getElementsByTagName("head")\[0\].appendChild(c)}var f,g;c.supports={simple:d("simple"),flag:d("flag")},c.DOMReady=!1,c.readyCallback=function(){c.DOMReady=!0},c.supports.simple&&c.supports.flag||(g=function(){c.readyCallback()},b.addEventListener?(b.addEventListener("DOMContentLoaded",g,!1),a.addEventListener("load",g,!1)):(a.attachEvent("onload",g),b.attachEvent("onreadystatechange",function(){"complete"===b.readyState&&c.readyCallback()})),f=c.source||{},f.concatemoji?e(f.concatemoji):f.wpemoji&&f.twemoji&&(e(f.twemoji),e(f.wpemoji)))}(window,document,window.\_wpemojiSettings);   img.wp-smiley, img.emoji { display: inline !important; border: none !important; box-shadow: none !important; height: 1em !important; width: 1em !important; margin: 0 .07em !important; vertical-align: -0.1em !important; background: none !important; padding: 0 !important; }                 /\* <!\[CDATA\[ \*/ var ot = {"THEME\_NAME":"tresor","THEME\_FULL\_NAME":"Tresor","adminUrl":"http:\\/\\/experiencesutra.com\\/wp-admin\\/admin-ajax.php","gallery\_id":"","galleryCat":"","imageUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/images\\/","cssUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme\\/css\\/","themeUrl":"http:\\/\\/experiencesutra.com\\/wp-content\\/themes\\/tresor-theme"}; /\* \]\]> \*/             var \_gaq = \_gaq || \[\]; \_gaq.push(\['\_setAccount', 'UA-63333235-1'\]); \_gaq.push(\['\_trackPageview'\]); (function() { var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true; ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js'; var s = document.getElementsByTagName('script')\[0\]; s.parentNode.insertBefore(ga, s); })();     

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
*   Deep Learning in Fashion

Articles
--------

Deep Learning in Fashion
------------------------

[EXPERIMENTS](http://experiencesutra.com/category/experiments/)

Recommendation engines are crucial for the fashion e-commerce business. Showing relevant items from the inventory has proven to be a sales booster. For fashion, building a recommendation engine involves multiple tasks. One such task is to appropriately tag clothing items. When you shop on a website the recommendation engine would try to find items similar to whatever you have selected based on tags. These tags can specify multiple things, i.e., type, color, texture. The intent of this experiment was to automate the tagging process using machine learning. To be specific, we are identifying the type (i.e., shirt, top), pattern (i.e., checked, stripped), and color palette from clothing images.

Convolutional Neural Nets or ConvNets, in short, has gained tremendous popularity in recent years. Deep Neural Networks built using ConvNets has been proven to be extremely efficient in tasks such as image recognition. Neural networks trained with a large amount of data (e.g. ImageNet, which contains 1.2 million images with 1000 categories) has even surpassed human level accuracy in image recognition. We are using Deep Convolutional Neural Nets to recognize clothing type and the patterns on the cloths.

There are two major difficulties:

1.  Training these deep convolutional neural nets requires a tremendous amount data.
2.  Our models still lack the ability to generalize to conditions that are different from the ones encountered during training.

To address these limitations, researchers have come up with a newer technique for training deep neural networks called transfer learning.

### What is Transfer Learning?

In traditional machine learning, we train a model A with data and labels for a particular task or domain A. On another occasion, for a task or domain B we again require labeled data to train model B. For example, a model trained on images of cats and dogs will fail to detect pedestrians.

Transfer Learning allows us to store and use the knowledge gained in one task or domain A in some other related task or domain B. We achieve it by storing the weights of model A and initializing model B with the stored weights before training. The major advantage is that transfer learning allows us to train a deep learning model with relatively fewer data.

[![traditional-vs-transfer-learning](http://experiencesutra.com/wp-content/uploads/2017/11/traditional-vs-transfer-learning.png)](http://experiencesutra.com/wp-content/uploads/2017/11/traditional-vs-transfer-learning.png)

### Training Deep Learning Models on Clothing Images

We went with the Deep Residual Learning model for image recognition (ResNet-50) that won the ILSVRC-2015 challenge in ImageNet classification, ImageNet detection, ImageNet localization, COCO detection, and COCO segmentation.

We have collected more than 30,000 images for 12 different categories of clothing, augmented the dataset by applying rotation, scaling and gamma adjustment and used weights pre-trained on ImageNet to initialize our model. We trained the final dense layers from scratch. We applied the same strategy for clothing pattern recognition. This time for 9 categories with a similar number of images. We have achieved around 90% and 95% accuracy for the aforementioned tasks, respectively.

### Finding Dominant Colors on Clothing

We used the CIE LAB color space and grouped every pixel within a particular region-of-interest in clusters using the k-means clustering algorithm. Then used each cluster center to represent one color.

Our final output can be seen in the following image.

[![final-output](http://experiencesutra.com/wp-content/uploads/2017/11/vastram.png)](http://experiencesutra.com/wp-content/uploads/2017/11/vastram.png)

#### References

1.  [http://cs231n.github.io/transfer-learning/](http://cs231n.github.io/transfer-learning/)
2.  [http://www.image-net.org/challenges/LSVRC/](http://www.image-net.org/challenges/LSVRC/)
3.  [https://arxiv.org/abs/1512.03385](https://arxiv.org/abs/1512.03385)

[Featured ![ZooYou](http://experiencesutra.com/wp-content/uploads/2015/12/Zooyou-397x310_c.png)   EXPERIMENTS **ZooYou**](http://experiencesutra.com/experiments/zooyou/) 

[Featured ![Project Chameleon](http://experiencesutra.com/wp-content/uploads/2017/06/default-397x310_c.png)   EXPERIMENTS **Project Chameleon**](http://experiencesutra.com/experiments/project-chameleon/) 

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