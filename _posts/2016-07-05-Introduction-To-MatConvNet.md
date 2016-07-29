---
layout: post
title:  "Introduction to MatConvNet"
date:   2016-07-05
excerpt: "A brief introduction to MatConvNet, a deep learning framework in Matlab. Installation, basic usage, coding philosophy, and examples will be introducted."
comments: true
---

# Introduction to MatConvNet



## Installation

I have successfully installed it on Windows 7. It is not hard if you follow the guide [here](http://www.vlfeat.org/matconvnet/install/). But, setting up all the required compiler on Windows 7 made me crazy. I would suggest to use Visual Studio (Community Edition) as the compiler and install the required .Net library (not the newest one). 

One terrible issue I encounted was that cl.exe (a .net library) cannot be found anyway. One possible solution was suggested [here](http://stackoverflow.com/questions/32091593/cannot-install-windows-sdk-7-1-on-windows-10).

## Building New CNN Models

In general, MatConvNet supports two types of model: simple chain model and DAG (directed acyclic graph) model. It is very easy to implement any CNN model as long as the layers are supported (even multiple criterions). (For instance, dilated convolution is not supported, yet. So, it may take considerable time to write your own.)

There are several nice things about MatConvNet. 
* It is easy to understand and tweak, if you are already familiar with Matlab. 
* It is easy to set different learning rate for each layer, which is necessary for fine tuning
* It is easy to assign different weights on the ground truth images. This is important when errors in certain areas should be highly penalized. 

The key limitation of MatConvNet is the limited number of supported functions, such as different types of layers, different optimization algorithms, etc..


## Examples

An illustration of VGG using MatConvNet. See [link](http://www.robots.ox.ac.uk/~vgg/practicals/cnn/)

A nice github repository containing quite a few CNN structures can be found [here](https://github.com/jxchen01/matconvnet-calvin). 

A Matlab plugin has been developed to visualize layers in MatConvNet models. See [link](http://vision03.csail.mit.edu/cnn_art/index.html)


