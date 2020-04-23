---
title: "Quest for Real time Object detection in Mobile Browsers"
date: 2017-06-03T12:52:36+06:00
image_webp: uploads/2018/08/365-640x480_c.jpg
image: uploads/2018/08/365-640x480_c.jpg
author: 
description : ""
---


If you are following Kepler work closely for past few months a certain emerging trend is going on, we are extensively seeking out opportunities for developing solutions based on Augmented Reality. Just take a look at  
Some of our past works [dinner tonight ar app for recipe recommendation](http://experiencesutra.com/experiments/dinner-tonight-ar-app-for-recipe-recommendation/) and [Reimagining The Tour Guide](http://experiencesutra.com/experiments/reimagining-the-tour-guide/)  
Both of these work has one thing in common. Here we are using Native Augmented Reality Platforms specifically iOS ARKit.  
One of the challenges of developing Native Augmented Reality / Machine Learning based app is customer Reach.  
It is very difficult to convince people to install a new App. Here Mobile Browser-based applications shine.  
The first Step of Development of Interactive ML-AR application is Real-time Object detection on Mobile.  
So how can we develop them? So we set out on the mission to find the secret solution.

&nbsp;
&nbsp;

![tenor]({{< baseurl >}}uploads/2018/08/tenor.webp)

&nbsp;
&nbsp;


So how do we start you may ask ?

We started with using Tiny YOLO object detection model in darknet network, pretty Dark path have we choson ![:)]({{< baseurl >}}uploads/2018/08/simple-smile.png)

Converted it into Tensorflow js model and then started detection.

This is how detection looks like.

&nbsp;
&nbsp;

{{< youtube DEOr8XO5s8A >}}

&nbsp;
&nbsp;


A problem, It takes 800 ms for each frame we need a solution.

TO BE CONTINUTED…

