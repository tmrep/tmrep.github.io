---
layout: post
title:  "String art - newly rediscovered idea"
author: tom
categories: [ projects ]
image: assets/images/string_art/string_art.jpg
---
When I first spotted a string art by <a href='http://artof01.com/vrellis/works/knit.html'>Petros Vrellis</a>, I was astonished. Interestingly enough, when I came across it a few years later again, I did not remember it at all, but I revived apparently revived all the same feelings. This time, I did not stand aside.

## String art

<a href="https://en.wikipedia.org/wiki/String_art">String art</a> is a specific way of creating images and ornaments by winding a string around nails or pins attached to a plane. Although it is a quite interesting and nice technique for creating decorations by itself, an artist name <a href='http://artof01.com/vrellis/works/knit.html'>Petros Vrellis</a> came up with string art pieces reproducing photographic images. It is obvious that such thing is impossible to be done by heart and that some assistance of computer and mathematics was involved.

Indeed, the task can be formulated as an optimization problem when we try to find such sequence of nail numbers forming a "winding plan" that would create an image resembling as much as possible a given input photo (converted to shades of gray). This alikeness is measured by a so-called cost function or optimization criterion. In my case, I simply simulated the final look of the string art following a given plan using Bresenham line algorithm for drawing the thread lines. Just note that the resolution of such rendered image can not be arbitrary, because size of the pixel should correspond to the width of used thread. This image is then downscaled to the size of the input photo. Sum of squared differences between the two images forms the desired criterion.

## Optimization process 
The solution I used is definitely not the best available, but it just worked right away without much tuning.  The optimization process starts from a completely random settings - meaning that the thread follows a randomly generated sequence of 4000 nails. In each optimization step a random mutation of the solution is performed. One particular but randomly chosen nail in this sequence is replaced by a different (again randomly chosen) nail. The only limitation is that this substitute nail can not be identical to the next nor previous nails in the original plan. The optimization criterion (or cost function) is then evaluated and depending on its value (whether it forms a better solution than was the original one before performing the mutation) the proposed modification is preserved or discarded. This process repeats many times until it gives a satisfactory solution or the value of the cost function stops to decrease. The following video shows the course of optimization process as it improves the initial random winding solution.

<iframe width="734" height="403" src="https://www.youtube.com/embed/4NKHhIdZKY8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Winding procedure
The following video then demonstrates how would the winding procedure itself look like. By routing the string From an initially blank canvas into the final artwork following the previously computed winding plan.

<iframe width="734" height="403" src="https://www.youtube.com/embed/kq9_pR1jl64" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

For those of you, who would like to create your own string art decoration or at least experiment a little bit with the problem and for example try different and more effective optimization solvers, the solution is available in the following <a href="https://github.com/tmrep/string-art">Github repository</a>.

## A few practical aspects
Although I do not present here any of the real photos, I actually build the whole thing. It was nice and it decorated our apartment for a couple of years. Recently, it was, however, damaged during a sad accident involving our curious little boy. Only then I realized I do not have any direct photo of the artwork.

### Frame shape
These kind of string images are usually made in a circular shape. That does not mean that any other more conventional shapes of frames are not possible.  By a pure intuition, however, the circular frame ensures the most uniform access of the string to the whole image plane. I decided for a setup consisting of circular canvas having a 50cm diameter with 316 nails equally spaced around its circumference.

### Frame stiffness
As I proceeded with winding the string, it become more and more apparent that the tension of so many stretched strings is definitely not negligible. The whole frame was bending like a bow due to the uneven string distribution. It was necessary to reinforce the quite light-build frame from plywood by a rigid steel ring.

### String strength
Since the winding process is quite daunting as I will describe below, it is a good idea to choose a high-quality and high-strength string. It is nothing more frustrating when a recent part of your the work gets ruined by a torn string.

### Automation
The manual winding procedure is definitely something that I would not wish to do again. Although I printed quite nice and matching numerical labels for all of the 316 nails and an audio and video guide with adjustable speed helping me a lot with the procedure, it is not very entertaining. I did not have enough patience to wind the whole thing as I originally planed stopping somewhere in the middle when the resulting image was already satisfactory enough for me.

The winding process could of course be automated and there, indeed, already exist a few of very good solutions out there:
- <a href="https://www.youtube.com/watch?v=UBQLxOoSbzA&ab_channel=TUWien">industrial robot</a>
- <a href="https://hackaday.com/2019/02/23/polar-platform-spins-out-intricate-string-art-portraits/">specialized winding setup</a>

I tried to come up with my own personal solution resembling the second one mentioned (before I knew someone other did it) and the most important advice I can give you is not to underestimate the importance of robust and stiff mechanical design.

## Related projects
Few of the other similar projects that I came across:
- <a href="https://www.youtube.com/watch?v=9XmnfOtUVKw&ab_channel=MAKinteract">A Computational Approach for Spider Web Inspired Fabrication of String Art</a>
- <a href="https://eheitzresearch.wordpress.com/implementation-and-realization-of-petros-vrellis-knitting/">Implementation and realization of Petros Vrellis’ knitting</a>

