---
layout: post
title:  "Unpack Function"
date:   2016-04-15
excerpt: "The usage of unpack in Torch/Lua"
tag:
- Torch 7
- Deep Learning Programming
comments: true
---

When using torch, you may encounter the function "unpack" in the code of quite a lot of packages. I am really curious about what it is, because I didn't find its definition as a Torch function.  

I finally found it as function in Lua. See [this](https://www.lua.org/pil/5.1.html).

In short, 
>An important use for unpack is in a generic call mechanism. A generic call mechanism allows you to call any function, with any arguments, dynamically.

One example is 
>f = string.find

>a = {"hello", "ll"}

>f(unpack(a))  will return 3 and 4