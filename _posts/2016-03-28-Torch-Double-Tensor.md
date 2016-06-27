In Torch 7, one should pay attention to the Tensor type, especially when using GPU.

Suppose you have a 1000-by-1000 float Tensor and another 1000-by-1000 double Tensor. When you write it to a ".t7" data file, you will find the difference between their physical sizes is huge, not 2x.    