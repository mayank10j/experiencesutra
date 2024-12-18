---
title: "Improving Colour based filtering results for Interactive Mirror Installation"
date: 2018-05-02T12:52:36+06:00
image_webp: uploads/2018/05/Mirror_StoryBoard_02MAY181.jpg
image: uploads/2018/05/Mirror_StoryBoard_02MAY181.jpg
author: Mayank Jain
description : ""
---

This is the follow up of our previous blog post [http://experiencesutra.com/projects/the-mirror-reimagined\_-a-smart-shopping-assistant-for-the-retail](http://experiencesutra.com/projects/the-mirror-reimagined_-a-smart-shopping-assistant-for-the-retail) which was about Sapient smart mirror application IMI being developed here in Kepler, to recap its functionality primary use case for IMI is the generation of Clothing recommendation in the physical retail store based on what you wear/show in front of it. Think of it as a distant cousin for _you may also like this_ feature that you while shopping but in an actual physical apparel store.

Our system has two primary filters for apparel search color based and style based. While style based filtering was giving us lots of accolades color based filtering still had a lot of issues. So, this is the story about what were the issues with color-based recommendations and how we were able to improve it.

&nbsp;
&nbsp;
![mirror-arch]({{< baseurl >}}uploads/2018/05/mirror-arch-1024x475.png)
&nbsp;
&nbsp;

So, to recap as illustrated in above system diagram. In our current system, we extract features from convolution layers and use these as the feature vector for matching with inventory items using Image similarity search subsystem. For color-based image search, this was being done by extracting first few layers of a CNN features. This works for some of the cases like this result.

&nbsp;
&nbsp;
![Picture1]({{< baseurl >}}uploads/2018/06/Picture1.png)
&nbsp;
&nbsp;

But fails miserably in many  other cases when a person is wearing multi-color shirts like this which was giving us lots of heartburn.

&nbsp;
&nbsp;
![Picture2]({{< baseurl >}}uploads/2018/06/Picture2.png) ![Picture3]({{< baseurl >}}uploads/2018/06/Picture3.png)  
&nbsp;
&nbsp;

It quickly became obvious to us that we need a better solution for color-based recommendations. It was time we tighten our belts and start from the beginning.  
On lots of introspection, one of the main issue we found that if a person was wearing a multi-color dress, sometimes results are coming an average of two colors in his worn apparel which is not what we wanted.

To mitigate this we asked ourselves a question. Is there exist a way to extract dominant primary colors in a given apparel with good accuracy? This may seem like a trivial problem but trust me it is not. Obvious solutions like counting pixels and placing them in color bins did not work out so well us. Another solution was using Clustering algorithms like K Means for clustering colors, but one of the major problems of using K Means like clustering methods are that many times results are biased based on how good K Means is initialization is e.g. choice of the number of clusters and initial cluster centers.

On further exploration, we found one blog post which was trying to answer the similar question of how to extract dominant colors from an image? In very short solution comes out to doing hierarchical color quantization with help of tree-based search while using Eigenvectors to split tree with each pixel in image belonging to one tree node. Node root gives the median of the subtree. You can read more about approach form aishack blog linked here.

[http://www.aishack.in/tutorials/dominant-color-implementation/](http://www.aishack.in/tutorials/dominant-color-implementation/)  which must be read if you want in-depth knowledge of approach.

Following these footsteps, We were able to get dominant colors in given apparel with very good accuracy. Now question rose for us that how do we do the image comparison and search from inventory using this? For doing the color comparison of two images we picked histogram comparison approach. Here we assign each pixel of the image into discrete bins. After this, we can directly compare two histogram using histogram comparison metrics, e.g. Bhattacharya distance.

Next problem was What is an optimum number of bins to choose ? and how to choose which bin each pixel will fall into ? Time to do lots of experiments. Choosing how many color spaces to choose is very important as it greatly affects the accuracy of the final result. If too many colors are chosen then histogram comparisons start suffering from the same problem of color averaging as discussed at the start of this blog post. So, for starting out we picked all 16 colors from 4-bit color space. These are all the colors in 4-bit color space. Image Credit: [http://r0k.us/graphics/colSpace.htm](http://r0k.us/graphics/colSpace.html)

&nbsp;
&nbsp;
![4bitColorspace]({{< baseurl >}}uploads/2018/06/4bitColorspace.png)
&nbsp;
&nbsp;

Next: For generating a color histogram of given apparel image we first extract dominant colors using AIShack method, after this each nearest neighbor of dominant color is picked from 16 colors mentioned above. For purpose of calculating nearest neighbor, we need a distance function that can accurately compare two colors. Naïve RGB color space is not suitable for this as RGB color space is not perceptually uniform. For this purpose, LAB color space is more suitable as it is designed to approximate human vision, hence the direct L2 distance between two colors in LAB color space gives the perceptually accurate result.  After projecting Dominant colors in 4bit color space we assign each pixel into bins of these 16 primary colors. So, for each image, you get the histogram of size 16 with an intensity of each bin varying between 0 to 100 percent. Sum of all histogram intensities is hence 100.

To use in our Color comparison based apparel recommendation system we iterate over all inventory data using a batch process and extract and save dominant color histograms mentioned above. On live system whenever a person stands in front of the camera we again extract dominant color histogram from his worn apparel and compare with all inventory histograms. Further, we pick top 10 nearest matches by first performing quicksort on all inventory histogram distances and then picking top 10 results.

Here are the results using 4-bit color space as histogram bins:

&nbsp;
&nbsp;

![img00003_4bit]({{< baseurl >}}uploads/2018/06/img00003_4bit-1024x341.jpeg)

![img00008_4bit]({{< baseurl >}}uploads/2018/06/img00008_4bit-1024x341.jpeg)

&nbsp;
&nbsp;

Quite an improvements, right?  but still on analyzing results from our test images we found that there are still failure cases where we did not have a good match. Like this:-

&nbsp;
&nbsp;
![img00090_4bit]({{< baseurl >}}uploads/2018/06/img00090_4bit-1024x341.jpeg)
&nbsp;
&nbsp;

We found that the number of different colors present in 4-bit color space is very low and this was costing us lots of mismatches. So we ended up adding more colors to our histogram pallet. In the end, we ended up with around 56 distinct popular colors. Here are some of the results from 56 colors pallet histogram matching.

&nbsp;
&nbsp;
![img00008]({{< baseurl >}}uploads/2018/06/img00008-1024x341.jpeg) ![img00090]({{< baseurl >}}uploads/2018/06/img00090-1024x341.jpeg) ![img00003]({{< baseurl >}}uploads/2018/06/img00003-1024x341.jpeg)
&nbsp;
&nbsp;

This looks as good result. We rerun our tests on hundreds of images and compared results of all three approaches ( CNN features, 16 color pallet Dominant color histogram and 56 color pallet dominant color histogram method ) and ended up picking 56 colors dominant histogram approach as the winner as this turned out to be best performing with most accurate recommendations.

