---
layout: post
title: Advanced -> Colour Correction
subtitle: "In a nutshell, it's hard"
date:   2017-08-16 18:00:00
categories: [photography]
---

Digitally processing colour negatives to get an accurate colour reproduction is hard. Early problems that you will encounter are the obvious orange cast to the negatives and also the fixed white balance of film. There is also the problem of 'what were the colours actually like when I took the photo?'. Furthermore, your scanning hardware and computer monitor will affect the colour in subtle ways. These things make getting realistic and 'correct' colours quite difficult.

The Darktable module 'invert' goes a long way towards getting accurate colours. It will remove the orange cast and correctly invert the negative image. You can then simply use the 'white balance' module to automatically adjust the image. Once this is done you are likely to be happy with your image, which will retain all influences on the colour throughout the process, including the influence of the film and your scanning camera. If that's what you want, then you're done with colour correction. However, if you would like to get your colours closer to reality and wish to reduce the influence of the various factors on the colour, then read on.

The 'proper' colour calibration process is about making sure that colours on your monitor and on your printer are as accurate to the inputs as possible and do not introduce any alteration. After proper calibration, the colours you see on your monitor will match the colours of your printout. The equipment needed to do this is expensive. Just the reference colour targets alone can cost a lot. Is it worth doing?

Let's think what can influence the colour...

0. The film you use, which will have a fixed white balance.
0. Changing ISO will change the colour (pushed or pulled).
0. Your lens will affect the colour slightly.
0. The development process will never be exactly identical, even when done at a lab.
0. Your scanning camera.
0. Your computer monitor.
0. Your digital darkroom processing.
0. Your own perception!
0. Other peoples monitors who are looking at your photos.

So even with proper colour calibration in place, there are factors beyond your control that prevent a fully automated process. Colour calibration does not control factors beyond the monitor and printer. You still have to get the colours 'right' somehow from your negative scan. This is the challenge I am attempting to solve here. My process complements 'proper' colour calibration and addresses the upstream variations in the analog process.

This process will compensate for the effect of everything, including your monitor. If it is not properly calibrated (mine isn't) then it will also be corrected, meaning that your colours will be out in relation to how far out your monitor is. I don't worry about this. I find it hard to get to a point where the accuracy of the monitor might play a large part in the colour variation. If you are worried about this, then you can still do a full calibration before starting this process. It will just make it more accurate.

In the process below, we take a photo of a calibration chart as displayed on your computer monitor. These calibration charts are very expensive to buy. If you have one, then you may want to take a photo of it instead. The problem with this approach is that you then don't have a reference to match against. You will have to eyeball what you see on the screen and try to get it to match your physical chart as you see it. This is harder. I leave it to your discretion.

0. Download a good macbeth colour chart from the internet.
0. Display the macbeth image full screen on your monitor.
0. Turn your monitor up to full brightness.
0. Darken the room you are in.
0. Put your camera on a tripod and set it up to take a photo of your colour chart being displayed by your computer.
0. Starting from the lowest ISO, take a photo at each setting you want to calibrate for. For my fuji C200 film, I use 200, 400, 800 and 1600. 
0. Develop, scan and load into Darktable.
0. Use the 'colour checker lut' module to adjust the target colours to match the source image as best you can. There is a 'darktable-chart' utility that promises to do this automatically. Unfortunately, I could not get it to work.
0. Save the resulting style in Darktable so you can reuse in the future with similar film/iso combinations.

This should improve your colour accuracy a lot. This process is still necessary even if you have properly calibrated your monitor. White balance is still a consideration, since the white balance of film is fixed. You will need to adjust for at least daylight vs indoors. You can do this with the white balance module. First, choose a representative image for each situation you want a white balance style for. You then use the white balance module in darktable to 'auto' balance the frame, excluding borders. This is good enough for me with just two styles, indoor and outdoor.

"But what about the colours of the film?" I hear you say. Unfortunately, this process corrects the colours in the film too, reducing their influence and getting them closer to real life. This may not be what you want. If that is your goal, then just using the 'invert' module in Darktable might be what you really want to do.
