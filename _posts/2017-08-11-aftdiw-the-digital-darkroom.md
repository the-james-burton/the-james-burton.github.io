---
layout: post
title: The Digital Darkroom
subtitle: "Working effectively and quickly in Darktable"
date:   2017-08-11 18:00:00
categories: [photography]
---

## Import and local copy

Once you have Darktable up and running, the next thing to do is to import the folders that contain your negatives scans. This is a simply process of importing a folder. You will notice a little checkbox about 'ignore JPG files', which you should check if you want to use your RAW images.

If you stored your scans on your NAS at home and wish to process them on a laptop away from home then there is a fantastic feature to support this in Darktable. It offers the ability to 'copy images locally'. As it says, this creates local copies of the master folders and will keep the masters automatically in sync with all your changes whenever your laptop is reconnected to your home network.

When you are done with editing, simply select the 'resync local copy' option for the images. I do most of my digital processing during my commute on a train with my laptop. This feature is invaluable to me and I strongly recommend you use it if you will be working in the same way.

If you use this local copy feature and Darktable hangs during startup, it may be because linux is struggling to find your network drives. To cleanly mount and unmount your network, simply use these commands. Once the connection is removed or re-added as appropriate, then restart Darktable and it will work again.

To remove a connection when on the move: `sudo umount -l /media/yourNasName`

To re-add a conection when you return home: `sudo mount -a`

## Process the scans

Now for another fun part of the process. This is where you will see your negative scans turned into real digital images. Before you ask, I am afraid there is no one size fits all magic button you can press to get everything to always look its best. You will need to spend some time designing presets in Darktable that get you 90% of the way there and then manually adjust per-image until you are happy. I have provided copies of my Darktable presets that I use on every batch.

Summarizing the active modules for my presets:

0. **levels** - This 'normalised' the images, effectively making the darkest pixel black, the lightest white and scales everything in between. This expands the dynamic range to using all brightness levels and increases contrast without making the image look unnatural. You will not need to adjust this from its 'automatic' setting. I find that a very low black level is good for reducing shadow noise in very dark areas. You can disable this and use the tone cure entirely, but I prefer to use both as the 'automatic' levels correction once or twice. I don't use any other modules.setting allows a more generic curve to be used, making for a better preset.
0. **tone curve** - Allow you to adjust the brightness of each pixel based on its current brightness. A straight line low to high has no effect. The S-curve makes dark pixels darker and light ones lighter, reducing the dynamic range and increasing contrast giving a 'punchier' image. Many striking high-contrast images have had a strong tone curve applied.
0. **monochrome** - Removes the tint to B&W negatives. The colour adjustment that is available will not have any effect here.
0. **local contrast** - I used this to give some images a little more 'punch'. It is optional and the purist will not like it.
0. **crop and rotate** - Used to strip off the sprockets from the scanand give a borderless image. If you managed to keep all your scans centred in the same way, then a single crop preset will work nicely for all. Note that when you rotate an image to get it portrait, Darktable does not properly rotate your crop. Bug report [11566](https://redmine.darktable.org/issues/11566) seems to cover this problem. To work around this, I have another preset to rotate and crop the image to portrait.
0. **orientation** - Used to rotate the image to portrait if needed.
0. **lens correction** - This is very helpful and allows you to simply select your camera to remove known lens distortions and vingetting. If you are using a close macro setting, you will need this if your camera does not offer effective automatic correction, since distortion at macro distances is high. Simply choose your camera, focal length and f-stop and the module should make the best corrections with no further input.
0. **spot removeal** - It is very hard to keep your negatives completely clean while scanning. Use this to remove dust marks that are inadvertently part of your scan.
0. **invert** - This is a very useful module that lets you select a blank part of your negatives and automatically 'invert' the image based on that. Essential with colour negatives. This does most of the work of colour correction for you.

Those modules are the ones I use to prepare my images for publication. With the exception of the tone curve, the above modules don't impart an artistic effect to your image. The tone curve is an interresting one. It can have a dramatic effect if overused but is necessary. What curve gives the most 'natural' image? Impossible to say! There isn't a right answer so you will need to experiment and find your preference.

Regarding other modules, I have on occasion used the perspective correction module once or twice. This should be forgivable by the purist, since it replicates to a certain extent what large format lens shifting can achieve.

Notice that I do not use the denoise option. My little Olympus XZ-1 scanning camera is quite noisy, even at ISO 100. Use the darktable denoise and both digital noise and film grain disappear. The grain and noise are thus sadly inseperable as far as I can tell. I intend to try median blending to see if it produces better results. However, I expect that in reality the film grain and my digital noise are pretty close in terms of noise floor. Using a scanning camera with a larger sensor is probably the answer.

**Add a list of presets here**
