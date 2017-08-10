---
layout: post
title: Exporting Images
subtitle: "More fiddly than it should be"
date:   2017-08-12 18:00:00
categories: [photography]
---

## Export the scans

Once you are happy with your images then you should export them all from Darktable. I leave the defaults as they are and choose JPG with a quality setting of 75. This will produce files of around 1Mb each in a subdirectory of your main film roll folder called 'darktable_exported'.

Why quality 75? Various articles on the internet suggest that there is little benefit to going higher. You will end up with significantly larger files for no perceptual increase in quality. If you have a very smooth image in which JPG artifacts become visible, then both analog film and JPG are poor choices in the first place. If you are more comfortable with a higher quality setting, then of course use it. Do your own research to find out more.

If you created local copies in darktable (perhaps to support remote laptop working as I do) then you can now remove them if you wish. You will not be doing any more work on them unless you wish to reprocess in the future.

## Update the EXIF tags

We now come to perhaps the trickiest part of the process. Your exported JPGs will retain the EXIF metadata from the camera that took the photos. Unfortunately, that is not your analog film camera, that is your digital scanning camera! You must now remove all traces of that metadata and replace it with your own to show the film camera that you used. You may think that this is an optional step. However, if you do not do this, then popular photo sharing websites will report that your scanning camera took the photo. This may also prevent you from sharing your photos in certain groups that insist on correct EXIF metadata.

Note that you may not need to do this if you are not using a digital camera to scan. If you are using dedicated scanning hardware, then the EXIF may already be written in some way via your software. I can't advise any further as I don't have such equipment, but I do suggest you see if you can pre-configure your EXIF data somehow in any scanning software you are using to represent your analog film camera.

I find that the easiest way to rewrite EXIF metadata is to use a command line tool called **exiftool**. This is a powerful utility and it can be hard for novices to comprehend. Once understood, the resulting commands are actually quite simple and can be reused. I give you the command that I use below to rewrite the EXIF metadata on all images in the current directory as per the given parameters. Make sure to run this in your 'darktable_exported' directory.

```
exiftool -all= -overwrite\_original -Make=Olympus -Model=OM-2n -ISO=400 *.jpg
```

0. `-all=` removes all EXIF metadata written by your scanning camera. You don't want any of this on your resulting image.
0. `-overwrite\_original` tells it to not bother creating a backup. We don't need the backup as we are operating on JPGs exported from darktable. You can always export again if you need to.
0. `-Make=Olympus -Model=OM-2n -ISO=400` a list of EXIF tags to add to the JPG for your analog camera and film speed. These will show up on many photo sharing websites.
0. `*.jpg` tells exiftool to operate on all JPG files in the current directory, which should be the appropriate 'darktable_exported' directory.

Sadly, there does not seem to be any standard EXIF tag for film type. Nevertheless, you may wish to use more fields. For example, there is a lens field in which you could report the lens you used. I don't personally do this. I often take two lens out on photo shoots and I can't always remember which one was used for each photo.

