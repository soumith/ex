---
layout: post
title: "Why do we rotate weights when computing the gradients in a convolution layer of a convolution network?"
tagline: ""
category: pages
tags: [beginner, deeplearning, convnets, convolutions, gradient]
---

Today someone asked on Google+

> Hello, when computing the gradients CNN,  the weights need to be rotated, Why ? 

![question](http://soumith.ch/ex/assets/post1/question.png "Question")


I had the same question when I was pouring through code back in the day, so I wanted to clear it up for people once and for all.

Simple answer: 

This is just a efficient and clean way of writing things for:

> Computing the gradient of a **valid** convolution w.r.t. the inputs.

_There is no magic here_

Here's a detailed explanation with visualization!

Input
![question](http://soumith.ch/ex/assets/post1/input.png "input")
Kernel
![kernel](http://soumith.ch/ex/assets/post1/kernel.png "kernel")
Output
![output](http://soumith.ch/ex/assets/post1/output.png "output")


###Section 1: valid convolution (input, kernel)
![section1](http://soumith.ch/ex/assets/post1/section1.png "section1")


###Section 2: gradient w.r.t. input of valid convolution (input, kernel) = weighted contribution of each input location w.r.t. gradient of Output
![section2](http://soumith.ch/ex/assets/post1/section2.png "section2")


###Section 3: full convolution(180 degree rotated filter, output)
![section3](http://soumith.ch/ex/assets/post1/section3.png "section3")

As you can see, the calculation for the first three elements in section 2 is the same as the first three figures in section 3.

Hope this helps!




