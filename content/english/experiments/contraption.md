

---
title: "Contraption"
date: 2018-01-12T12:52:36+06:00
image_webp: uploads/2018/01/Pic_for-Blogpost.jpg
image: uploads/2018/01/Pic_for-Blogpost.jpg
author: 
description : ""
---

We all strive for great output, don’t we? Our entire work lives revolve around achieving targets, meeting expectations and on most instances, performing beyond them. Walking through these self imposed peaks of professional competency, how many of us do actually end up enjoying the journey – to get there, but watch some trees and lakes as we drive past?

The Contraption is one such experiment conducted by Kepler to highlight the importance of the process. Through this we look to communicate that the simplest of tasks, even the ones that are taken for granted, have a beautiful process running in the background which is completely lost on us. Once we get a peek into this very process, things start to make more sense and the value of the output takes a new height of excitement.

This contraption is a Rube Goldberg machine which combines various elements like Chain Reactions, Marble Machines and a combination of sensors and maker electronics to create a complex chain of actions to fulfil a simple task – take a selfie.


## The Journey

One of the core ideas was to create a chain reaction using off-topic elements. The user performs a completely unrelated action of pressing a bicycle pump to start the experience. This activates a flap switch which activates levitating ping-pong ball. Next up is a swing-arm mechanism which releases a steel ball through a funnel on to a marble track. A spot light also turns on at this stage, throwing light onto the next segment of the track.

The steel ball travels some distance, changing levels on a double storied path with lifting mechanisms. The ball then falls through a pipe onto a plate which triggers off another spot light onto the third segment of the journey.

Here, some more distance is covered on a marble track before the steel ball is raised by one level and directed onto a domino set. These dominos fall to trigger off the digital segment of the experience where a short animation leads onto a clapboard, setting off spot light number 3.

This final spot light activates a Robotic arm to click a picture of the person standing at the bicycle pump and a style transfer algorithm running at the backend applies a filter to the picture taken and projects it onto the wall in front of the user – thus taking the perfect Selfie.
&nbsp;
&nbsp;

{{< youtube lcEZ_o5haCU >}}

&nbsp;
&nbsp;

  
## The Hardware
&nbsp;
The entire circuit is controlled using an Arduino.

The levitating ping pong ball is made using a blower fan and covering it with a channel. This mechanism also houses an LDR which picks up the trigger for opening the swing arm and switching on light #1 and lift mechanisms #1 and #2.

As the ball drops through the pipe, it lands on to a piezo sensor which triggers light #2 and the third lift mechanism.

The dominos are made off cut Aluminum plates and assembled in such a way that their reset time is less than 20seconds.

Another LDR on light #3 triggers off the Robotic arm made using a Lego Mindstorm kit and converted into a keyboard action using a Makey-Makey kit. And finally, the last piece of technology, which manages the style transfer using Neural Networks to apply the look & feel of one image to another.

This experiment done recently at Kepler was a great combination of enormous amounts of fun as well as a lot of hands-on-learning of bringing together puzzle pieces from different domains and stitching them together to create a fresh perspective on things. The beauty of the whole experience being the scalability it offers to be implemented across countless applications and across all user segments – definitely making it a potentially great tool for brand stories.
