+++
title = "RTIOW"
date = "2019-10-24"
author = "Philippe Nadon"
cover = "/3d/RTIOW.png"
+++

In the summer of 2019 I decided to work on the [Ray Tracing In One Weekend](https://github.com/RayTracing) tutorials, which walks you step by step through building a ray tracer in cpp.

I found the experience to be very interesting, and at the time of writing there were certain bugs in the official code which led to strange behaviour such as strange lighting:

![rtiow with bug](/3d/RTIOW_pre-patched.png)

Since each pixel was calculated by computing the sum of all light rays hitting the camera at that point, some extremely bright areas would have an integer overflow, and thus lead to a very *dark* area. This was corrected by ensuring that any value above `255` would be capped at that value, resulting in the below image:

![rtiow correct](/3d/RTIOW.png)
