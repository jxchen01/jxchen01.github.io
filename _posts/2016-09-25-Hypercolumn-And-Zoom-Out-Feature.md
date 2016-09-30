---
layout: post
title:  "Hypercolumn And Zoom Out Feature"
date:   2016-09-25
excerpt: "The reading note of two papers related to hypercolumn"
tag:
- Deep Learning Study
- Reading Note
comments: true
---

## Reference 
Mostajabi M, Yadollahpour P, Shakhnarovich G. Feedforward semantic segmentation with zoom-out features. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition 2015 (pp. 3376-3385).[(link)](http://www.cv-foundation.org/openaccess/content_cvpr_2015/html/Mostajabi_Feedforward_Semantic_Segmentation_2015_CVPR_paper.html)

Hariharan B, Arbeláez P, Girshick R, Malik J. Hypercolumns for object segmentation and fine-grained localization. InProceedings of the IEEE Conference on Computer Vision and Pattern Recognition 2015 (pp. 447-456).[(link)](http://www.cv-foundation.org/openaccess/content_cvpr_2015/html/Hariharan_Hypercolumns_for_Object_2015_CVPR_paper.html)

## Summary

These two papers appear before the well-known fully convolutional network (FCN). I feel the core spirit of FCN was already well formulated in these two papers. 


The motivation is that in the conv-net, the early layers have smaller receptive field, and the deep layers have larger receptive field. Then, if we want to classify each pixel, or a superpixel, or even a small region, we want to take information at different scales (i.e., different receptive field sizes). 

The idea is illustrated in the picture below. 

<img src="{{ site.url }}/pic/hypercolumn.png" alt="Architecture of Hypercolumn" style="width: 300px;">

After downsampling, the size of the feature maps is not of the same scale as the original image. To associate the information at this scale with each pixel in the original image grid, upsampling is performed.

Zoom-out features essentially mean that we collect the features from receptive field of different sizes centered at the same position. It can be viewed as "zooming out" from a particular pixel (or superpixel) up to a very large context. 


## Related Papers

When the first time I read the following two papers, I was so surprised that why they perform much better than FCN or U-Net. The structure seems to be a "simple" extention of FCN. After I read the aforementioned two papers related to hypercolumn, I finally understand the consideration behind the design.

Chen H, Qi X, Yu L, Heng PA. DCAN: Deep Contour-Aware Networks for Accurate Gland Segmentation. arXiv preprint arXiv:1604.02677. 2016 Apr 10.

Chen H, Qi XJ, Cheng JZ, Heng PA. Deep contextual networks for neuronal structure segmentation. InThirtieth AAAI Conference on Artificial Intelligence 2016 Feb 21.


