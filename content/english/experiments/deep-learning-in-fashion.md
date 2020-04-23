
---
title: "Deep Learning in Fashion"
date: 2017-11-01T12:52:36+06:00
image_webp: uploads/2017/11/traditional-vs-transfer-learning.png
image: uploads/2017/11/traditional-vs-transfer-learning.png
author: 
description : ""
---

Deep Learning in Fashion
------------------------


Recommendation engines are crucial for the fashion e-commerce business. Showing relevant items from the inventory has proven to be a sales booster. For fashion, building a recommendation engine involves multiple tasks. One such task is to appropriately tag clothing items. When you shop on a website the recommendation engine would try to find items similar to whatever you have selected based on tags. These tags can specify multiple things, i.e., type, color, texture. The intent of this experiment was to automate the tagging process using machine learning. To be specific, we are identifying the type (i.e., shirt, top), pattern (i.e., checked, stripped), and color palette from clothing images.

Convolutional Neural Nets or ConvNets, in short, has gained tremendous popularity in recent years. Deep Neural Networks built using ConvNets has been proven to be extremely efficient in tasks such as image recognition. Neural networks trained with a large amount of data (e.g. ImageNet, which contains 1.2 million images with 1000 categories) has even surpassed human level accuracy in image recognition. We are using Deep Convolutional Neural Nets to recognize clothing type and the patterns on the cloths.

There are two major difficulties:

1.  Training these deep convolutional neural nets requires a tremendous amount data.
2.  Our models still lack the ability to generalize to conditions that are different from the ones encountered during training.

To address these limitations, researchers have come up with a newer technique for training deep neural networks called transfer learning.

### What is Transfer Learning?

In traditional machine learning, we train a model A with data and labels for a particular task or domain A. On another occasion, for a task or domain B we again require labeled data to train model B. For example, a model trained on images of cats and dogs will fail to detect pedestrians.

Transfer Learning allows us to store and use the knowledge gained in one task or domain A in some other related task or domain B. We achieve it by storing the weights of model A and initializing model B with the stored weights before training. The major advantage is that transfer learning allows us to train a deep learning model with relatively fewer data.

![traditional-vs-transfer-learning](/static/uploads/2017/11/traditional-vs-transfer-learning.png)

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

