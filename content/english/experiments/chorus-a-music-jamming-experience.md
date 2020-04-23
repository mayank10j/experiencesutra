---
title: "Chorus – A Music Jamming Experience"
date: 2018-09-12T12:52:36+06:00
image_webp: images/blog/blog-post-3.webp
image: uploads/2018/09/IMG_20180903_153109_HDR-397x310_c.jpg
author: John Doe
description : "This is meta description"
---


Augmented Reality is considered to be the future of experience. AR provides an immersive experience into a land of imaginations that otherwise would not have been possible to experience. Thus, whenever the term Augmented Reality appears in a newsprint or any other media, this technology has often been compared with the Holodeck of Star Trek. And rightfully so.

[![Data_and_Riker_leaving_the_holodeck-antique](/uploads/2018/09/Data_and_Riker_leaving_the_holodeck-antique.jpg)

Collaboration, remote control, and remote assistance are some of the key elements we wanted to showcase using an AR application. We built Chorus, an AR music jamming application to present the capabilities and explore the challenges of building an AR application. Chorus, as the name suggests, can be used by multiple people simultaneously to create music out of some very unusual instruments.

Sequential harmonic beats, when played in a loop, create music. And one can create beats using virtually anything. We choose some spare electronic equipment like a Relay, a Piezo and a stepper motor, and an old Floppy drive which again has a stepper motor inside. Providing MIDI signals of different frequencies in different time intervals and playing that in a loop we were able to generate some very awesome music.

We have used On-Device Machine Learning to classify the devices each person can play. Used some paper markers stuck to a cardboard to use as dials for changing the Volume and Beats Per Minute values for the music sequencer. Again the paper marker and their rotation were found using machine learning and some clever math.

The entire Augmented Reality world was created using ARKit and is run on multiple iPads. Withing the 3D world inside the iPads the user experiences a virtual disco, and there they get the control of different devices.

To make all those different users give instructions to all those different instruments we created a middleware that was written in Node.js.

Chorus combines AR, AI, and IoT in a very creative way. Innovation requires exploration and creative thinking. Chorus represents a perfect amalgamation of creativity + technology, an effective skill recipe for impact transformative work.  This represents a wonderful example of the culture of “thinking” with “hands”.

The following video does not justify the experience you get using the application but have a look.

{{< youtube nM45coaVIis >}}

We had showcased the Chorus in JSFoo 2018, the 8th Edition of India’s first JavaScript conference, held at Bengaluru. Here’s a quick bite from the same event.

{{< youtube qvvHO8oBvjQ >}}
