Digital noise can affect individual pixels in random ways. If we were to take two photos of a scene they would be affected by the noise in subtly different ways. The effect is however, always the same. That is, to report an incorrect luminance value +/- a given amount over a bell curve distribution. Take enough photos of the exact same scene and eventually the majority of them will have the 'correct' value for the pixel. Because the noise is distributed over a a bell curve, this will be the median value. An image comprised of the 'median' value for the pixel for a stack of images of the same scene is called [median blending](https://petapixel.com/2013/05/29/a-look-at-reducing-noise-in-photographs-using-median-blending/).

This is a fascinating technique that is used for various reasons from reducing noise in astrophotography to removing moving objects from a static scene (a moving object will not be present in most images of the collection, so the pixels from it will not be the 'median' value). It works on a stack of images of the same scene. It requires that the images are exactly aligned, either with a tripod or software such as Hugin. The median blending process compares the same pixel location across all images. It ranks them from low to high luminosity. It then chooses the 'median' pixel to use in the final image. And so on for every pixel. This has the effect of averaging out the image to the middle value. Assuming there are enough images in the collection, this middle value will be the one least affected by noise, since it will be in the middle of the bell curve.

Why might this be useful for negative scanning? Our situation fills the brief. Using our digital scanning camera we can take lots images of the negative, all exactly aligned simply by pressing the shutter multiple times for one negative, or using a burst mode. In theory, you can then do median blending on the image stack by running the following command from the [imagemagick](www.imagemagick.org) toolkit...

```
convert OUT_PREFIX* -evaluate-sequence median OUTPUT.jpg
```

However, in practice there are complications...

0. Imagemagick cannot write RAW format. Therefore median blending needs to be done on post-processed, exported JPGs.
0. You must ensure the output JPGs are as identical as possible. They must differ only in noise, nothing else. You may therefore want to set your scanning camera to fixed exposure and replace any automatic adjustments in Darktable (such as the one in the 'levels' module) with hardcoded equivalents.
0.  It will produce a huge amount of extra data. Using my XZ-1, a roll of 36 exposures requires about 500Mb for a single shot per frame. Multiply that by the number of images you want in the stack and it quickly becomes a lot more data.
0. It takes a long time and a lot of CPU to blend each file. You will be surprised and disappointed at just how long it takes and how hot your computer gets. This is a problem if you work largely on battery as I do.

There is not much written about this surprisingly simple technique. Nor does it appear to have made it in-camera yet, which is really where it needs to be in my opinion. I believe there are some phone camera apps that have the feature built in, so hopefully it will become more readily available. Personally, I think median blending is worth doing individually, on the best of your images that you want to print in large format or maybe even enter into a competition.

