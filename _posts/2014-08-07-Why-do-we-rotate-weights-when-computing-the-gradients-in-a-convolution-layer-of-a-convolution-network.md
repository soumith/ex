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
There is no magic.

Here's an explanation with a nice visualization!

Input

Kernel

Output



Section 1: valid convolution (input, kernel)


Section 2: gradient w.r.t. input of valid convolution (input, kernel) = weighted contribution of each input location w.r.t. gradient of Output


Section 3: full convolution(180 degree rotated filter, output)



