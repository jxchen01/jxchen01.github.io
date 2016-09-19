---
layout: post
title:  "Torch Memory Optimization"
date:   2016-03-28
excerpt: "The memory issue in Torch 7 and its solution"
tag:
- Torch 7
- Deep Learning Programming
comments: true
---

The current version of Torch 7 is not very efficient in memory usage, yet. [This nice work](https://github.com/fmassa/optimize-net) can be used to optimize the memory usage. In short, it recycles some buffer spaces.
