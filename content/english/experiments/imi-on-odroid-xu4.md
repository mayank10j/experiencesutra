---
title: "IMI on ODROID XU4"
date: 2018-09-12T12:52:36+06:00
image_webp: uploads/2018/08/365-1920x600_c.jpg
image: uploads/2018/08/365-1920x600_c.jpg
author: 
description : ""
---


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

