---
title: "Mobile deployment of deep learning models"
date: 2018-09-12T12:52:36+06:00
image_webp: uploads/2018/09/AR-1920x600_c.jpeg
image: uploads/2018/09/AR-1920x600_c.jpeg
author: 
description : ""
---


Mobile deployment of deep learning models
-----------------------------------------


With the proliferation of deep learning libraries, we are facing the paradox of choices, there are so many different libraries where we can train our deep learning models. To choose one of these is giving us lots of anxiety.

We can use some of the comparatively old but still very powerful [caffe](http://caffe.berkeleyvision.org/) , [Theanao](https://github.com/Theano/Theano) or [torch](http://torch.ch/), or you can join cutting edge deep learning research by becoming part of [Tensorflow](https://www.tensorflow.org/), [Pytorch](https://github.com/pytorch/pytorch) or [MxNet](https://mxnet.apache.org/) community, as always devil lies in details. Hence we set out on a journey for finding out which library would be best suited for our newest secret Augmented reality experience.

The problem statement was simple: How to classify between some unique items on top of the table, to be specific a floppy drive, Pizo, Stepper motor, and Relay. But constraint was that the trained model should be able to run on alongside ios arkit with good accuracy. Preferable able to use hardware acceleration using ios coreml neural network format. Why do we have such unique requirements and why do we need to classify between these weird items is a suspense which would be revealed in our upcoming blog posts ;-).

We started out with FastAI / PyTorch combo so for people who do not know fastai is library written on top of pytorch which enables writing industry grade deep learning models in the minimal line of codes. Writing deep learning model this way enables us to get optimal accuracy in a short span of time. [http://www.fast.ai/](http://www.fast.ai/) also host a very popular MOOC course which incidentally we are also using for our AI Saturdays initiatives. We were able to get quite a good accuracy for our collected data on fastai with accuracy after transfer learning with resnet64 in range of 98 percent.  One of the recommended ways for converting FastAI/Pytorch trained models in mobile devices is using Onyxx which is being a universal way for neural network compatibility, so ideally they way convert pytorch model is pytorch -> Onnyx and then onnyx to coreML for iOS or Caffe2 for android. while trying to convert pytorch model to onnyx we stumbled on a bottleneck that some of the functions namely dynamic avg pooling is not supported on onnyx for now. After a lot of debugging and web search, we concluded that pytorch is not suitable for now for mobile porting as these features are still being worked upon. So we had to move on to other approaches.

So next we used one interesting project called [turicreate](https://github.com/apple/turicreate) which is an ML library written in-house at apple and support direct export of coreML models. ( coreML is official neural network format for running on iOS if you want to use hardware acceleration)

So we were able to use our training data for mobilenet transfer learning in turicreate and able to integrate with our new secret app/project. But on testing, it’s accuracy we found it less than satisfactory. This we confirmed with the online community. There is a general consensus that neural networks trained on turicrete sometimes gives suboptimal accuracy. So our recommendation, for now, for anybody exploring turicrete is to re-confirm results obtained from turicreate with more mature libraries like tensorflow etc.

So, at last, we used Tensorflow for training and able to convert tensorflow modlel to coreML using this project [tf-coreml](https://github.com/tf-coreml/tf-coreml) . After initial hiccups, we were able to run the whole network with quite a good accuracy on mobile. You can see the results:

&nbsp;
&nbsp;

{{< youtube PHphtCOODzA >}}

&nbsp;
&nbsp;