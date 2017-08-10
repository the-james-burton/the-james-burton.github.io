---
layout: post
title: Advanced -> Lens Correction
subtitle: "Probably not necessary"
date:   2017-08-14 18:00:00
categories: [photography]
---

Your scanning camera will introduce distortion into your scans, especially if you are using a close macro setting, just as I do. Darktable has a large database of cameras and lens and yours will likely be on it. These corrections come from the [lensfun](http://lensfun.sourceforge.net) project, which Darktable depends on.

My XZ-1 was indeed available as a built in correction. However, I found that the correction for super macro mode was not sufficiently strong. Unfortunately, it is not possible to simply tweak the settings in Darktable. Instead, one must make a manual edit in the lensfun database file. This file can be found on your linux computer at `/usr/share/lensfun`. In there, you will find a file that contains your camera and lens (if removable). As long as you can find it, you can add an extra entry if you need to. What, then are the numbers that you need to add?

You can perform a semi-automatic lens calibration by using the [hugin](http://hugin.sourceforge.net/) software, which comes with a lens calibration tool that helps you create a correction that can be entered into your local lensfun database. You first need to take a photograph of an image that has clear horizontal and vertical lines in it. **provide a good target** This photograph should be taken at the focal length and aperature that you intend to scan your negatives at. You can simply display the image on your computer screen and then take the photo. Use a tripod and ensure that the horizontal and vertical lines in the image are indeed horitonzal and vertical with respect to the image boundaries. Once taken, transfer the image to your computer.

You then use Hugin to correct this image. After you install Hugin, you will have a 'Hugin Calibrate Lens' item in your menu. Launch this program or just type `calibrate_lens_gui` into a terminal prompt. To do the correction, try this...

**review this process**

0. Add the image with the 'Add' button.
0. Enter the focal length. You can enter one less than the lowest value present in your lensfun database for the camera/lens you are calibrating.
0. Tweak the options and preview until the lines are nicely detected.
0. Click the 'Optimise' button to generate the correction numbers
0. Preview the corrected image to see if it looks good. Tweak again until you are happy.
0. Edit the lensfun database you wish to add the new entry to.
0. Copy the closest 'distortion' entry, set the focal length and enter the numbers for a, b and c as you see them in the Hugin calibration tool.
0. Update the 'focal' entry min and max values as required to cater for your new row.
0. Save the file and restart Darktable.


{% highlight xml %}
<lens>
    <maker>Olympus</maker>
    <model>XZ-1 &amp; compatibles (Standard)</model>
    <model lang="en">fixed lens</model>
    <model lang="de">festes Objektiv</model>
    <mount>olympusxz1</mount>
    <focal min="5" max="24"/> <!-- min edited -->
    <aperture min="1.8" max="8"/>
    <cropfactor>4.68</cropfactor>
    <calibration>
        <!-- I added the next line -->
        <distortion model="ptlens" focal="5" a="0" b="-0.031" c="0" /> 
        <distortion model="ptlens" focal="6" a="0.01604" b="-0.05047" c="0"/>
        <distortion model="ptlens" focal="6.5" a="0.01062" b="-0.03568" c="0"/>
        <!-- file continues... -->
{% endhighlight %}

You can search around for more help with this process, for example, [here](http://libregraphicsworld.org/blog/entry/creating-lens-distorsion-models-with-hugin-lens-calibrator).

