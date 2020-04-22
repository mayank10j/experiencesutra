The Mirror Reimagined\_ – A Smart Shopping Assistant for the Retail | EXPERIENCESUTRA                         The Mirror Reimagined\_ – A Smart Shopping Assistant for the Retail | EXPERIENCESUTRA                                   

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
*   [PROJECTS](http://experiencesutra.com/category/projects/)
*   The Mirror Reimagined\_ – A Smart Shopping Assistant for the Retail

Articles
--------

The Mirror Reimagined\_ – A Smart Shopping Assistant for the Retail
-------------------------------------------------------------------

[PROJECTS](http://experiencesutra.com/category/projects/)

We started experimenting with the idea of a smart shopping assistant for the physical apparel stores around this time [last year](http://experiencesutra.com/projects/the-interactive-mirror/). We had envisioned the Mirror to be a personalized shopping assistant with the capabilities of a recommendation system. Recommendation systems aren’t anything that is new. In fact, smart recommendations have long transformed the world of e-business. Netflix’s recommendation engine generates [$1 billion yearly revenue](https://www.businessinsider.in/Why-Netflix-thinks-its-personalized-recommendation-engine-is-worth-1-billion-per-year/articleshow/52754724.cms). In 2012, Amazon reported 29% sales increase during their second fiscal quarter. [The success story of Amazon](http://fortune.com/2012/07/30/amazons-recommendation-secret/) was accredited to the recommendation system they had in place. Fashion e-commerce websites offer smart recommendations based on customer preference. Shopping history, wishlist items etc. indicate the customer’s likings. You’d add something to your shopping cart or to your wish list, and the mobile e-commerce app or the website would give you a list of recommendations. Your wishlist shows your intent.

Inventory visibility directly connects to the number of sales. And this is the reason recommendation systems are so successful. The more you show, the more you sell – is the mantra. But how can you have such a recommendation system for a physical setup? It has to serve the same purpose as in an e-commerce website and has to be seamless, as well. So, we envisioned a user journey. When a customer picks up some clothing item and tries to see how they would look on it in front of a mirror – by casually holding the cloth in front of them, the mirror would surprise them by showing more similar options they could purchase.

[![Mirror StoryBoard](http://experiencesutra.com/wp-content/uploads/2018/05/Mirror_StoryBoard_02MAY181.jpg)](http://experiencesutra.com/wp-content/uploads/2018/05/Mirror_StoryBoard_02MAY181.jpg)

When designing the Mirror, we had the following pointers in mind.

1.  The experience has to be absolutely frictionless for shoppers.
2.  The Mirror must improve the sales figures by bringing forward the inventory.

The working prototype of the Mirror that we have demonstrated very recently at the Great Indian Developer Summit (Asia’s largest developer summit, at Indian Institute of Science, Bengaluru), 2018, serves our intention. It has the following functionalities.

1.  Classifies Men’s and Women’s categories, automatically.
2.  Recognizes apparel type and shows a list of recommendations of similar looking clothes.
3.  Suggests other items (complimentary/matching clothes) that the shopper might like to buy.
4.  Presents deals/available sizes and an option to shortlist items the shopper would like to try-on inside a trial room.

[http://experiencesutra.com/wp-content/uploads/2018/05/GIDS-Mirror.mp4](http://experiencesutra.com/wp-content/uploads/2018/05/GIDS-Mirror.mp4)

So, how does the Mirror work?

The Mirror is powered by state-of-the-art Deep Learning. We have trained four different deep learning models for the following tasks.

1.  Person Detection.
2.  Face Detection.
3.  Gender Detection.
4.  Apparel Category Classification.

We have prepared a dataset of 30k+ images to train our DCNN model for apparel category classification. Detailed explanations of our deep learning architectures can be found in our [previous blog](http://experiencesutra.com/experiments/deep-learning-in-fashion/). Accuracies of our apparel classification model are shown in the following graph.

[![accuracies](http://experiencesutra.com/wp-content/uploads/2018/05/Screen-Shot-2018-05-02-at-1.21.15-PM.png)](http://experiencesutra.com/wp-content/uploads/2018/05/Screen-Shot-2018-05-02-at-1.21.15-PM.png)

After apparel category classification, in the final stage of generating a list of similar items, we rank the store inventory based on features extracted from the query image. Query features are extracted from intermediate DCNN layers. Deep Convolutional Neural Nets can be utilized to extract features from an image. Features are represented in a hierarchical manner in a CNN. First few layers of a CNN extract low-level features like color and gradient. More abstract features like edges, textures are extracted from deeper layers. We have prepared a database of features that map to items in the store inventory, beforehand. This database is well optimized (using state-of-the-art clustering algorithms) for storage and search. The inference architecture for recommendation generation using similarity search is depicted in the diagram below.

[![mirror-arch](http://experiencesutra.com/wp-content/uploads/2018/05/mirror-arch.png)](http://experiencesutra.com/wp-content/uploads/2018/05/mirror-arch.png)

The newest feature in our Mirror is cross-recommendations. Showing relevant items that shoppers can buy is a sales booster. We want our Mirror to display relevant items, such as trousers, handbags, backpacks etc. for a complete look recommendation. Currently, we are suggesting trousers with shirts, tops, t-shirts etc.

We have more feature extensions and improvements planned for the Mirror. Stay tuned on experiencesutra for updates.

[Featured ![Interactive wall of stories](http://experiencesutra.com/wp-content/uploads/2016/05/KDy2015-397x310_c.png)   PROJECTS **Interactive wall of stories**](http://experiencesutra.com/projects/wallofstories/) 

[Featured ![Mirror Reimagined @ The Fifth Elephant](http://experiencesutra.com/wp-content/uploads/2018/08/10-397x310_c.jpg)   PROJECTS **Mirror Reimagined @ The Fifth Elephant**](http://experiencesutra.com/projects/mirror-reimagined-the-fifth-elephant/) 

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