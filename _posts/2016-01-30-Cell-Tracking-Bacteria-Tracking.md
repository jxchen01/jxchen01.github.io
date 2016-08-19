---
layout: post
title:  "Cell/Bacteria Tracking"
date:   2016-01-30
excerpt: "Tracking biomedical objects, like bacteria or cells, is a foundamental problem for quantitative analysis of dynamics. I developed a tracking algorithm based on Earth Mover's Distance. The effectiveness has been demonstrated in various real applications."
project: true
comments: true
---

# Cell/Bacteria Tracking 



Object tracking is a fundamental problem in computer vision. In natural scene images, there are a lot of effective schemes, from classic model-based algorithms to recent [deep learning solutions](https://github.com/kjw0612/awesome-deep-vision#object-tracking). Common benchmarks can be found [here](https://motchallenge.net/). 

However, tracking cells, mostly in microscopy images (confocal or fluorescent), poses a very different problem. Intuitively, every cell looks almost the same in lots of situations. Suppose you mask out all the cells in one frame except one, and you want to find the corresponding cell in the next frame, this can be extremely difficult, especially when cells are packed densely. 

When retrospecting how I track cells by eyes in a sequence of images, I have implicitly used two strategies: anticipating the future positions by interpreting the motion/position of each cell in previous few frames or find matches between two small groups of cells, within which cell-to-cell correspondence can be easily determined. (For comparison, when you are tracking two cars, one yellow and one red, in a movie, it is nothing more than searching for car-shaped objects with either yellow or red color.)

Actually, two mainstream frameworks in the literature share a common spirit with the aforementioned intuitions. Namely,

* Framework 1: Tracking cells by propagating the position of each cell from frame to frame
* Framework 2: Tracking cells by finding an optimal matching between all cells in two (or more) consecutive frames

To this end, I developed an new approach for cell tracking problems. First, I proposed a matching algorithm based on [Earth Mover's Distance (EMD)](http://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/RUBNER/emd.htm) to perform matching between cells in consecutive frames. Based on that, I design a new hybrid scheme combining active contours (an important method in Framework 1) and EMD matching which takes the complimentary advantages of the two frameworks and achieves state-of-the-art performance in real applications. 



## A Matching Model Based on Earth Mover's Distance

#### What is EMD?

Briefly, EMD is a type of measurement quantifying the minimum effort for moving several piles of dirt of certain quantities to several holes of certain capacities. (Note: This is an intuitive definition on a discrete space. A similar definition between probability distributions in a metric space can be found as [Wasserstein distance or Mallows distance](https://en.wikipedia.org/wiki/Wasserstein_metric). 

#### What is EMD Matching?

When you think of all cells in frame K as several piles of dirt and all cells in frame K+1 as a set of holes, it is not hard to interprete EMD as a model for matching model. (It is necessary to modify the original definition of EMD in order to handle some practical issues, such as missing detection or cells moving in/out of imaging region. More details can be found in [1,4])

#### Why EMD?

There have been lots of matching models in the literature. Why EMD is better than the others? The key reason is that EMD is so flexible that it is able to handle all different situations in matching two groups of cells (like mitosis, cell fusion, leaving, entering, etc.), and takes polynominal time (w.r.t the number of cells) to solve. 



## A Hybrid Approach for Tracking Cells



#### Why do we want to combine the two frameworks?

A key problem in framework 2 (such as EMD matching) is that such methods can do nothing with the segmentation or detection step. In other words, it takes the segmentation results for granted. When segmentation results occur, there is no opportunity to correct it in the matching step, even though the matching algorithm is designed to be robust to segmentation errors. 

On the other hands, the method in framework 1 (such as active contour based methods) can solve segmentation and tracking simultaneously, but with a much higher computation cost and some strong assumptions (e.g., small cell displacement) that cannot hold in out situations. 

#### How the hybrid approach works?

Briefly, the hybrid approach calls two modules, one for matching and one for propagation, iteratively. 

1. Perform a quick pre-segmentation
2. Manually correct the errors in frame 1 (for fully automated version, see [3])
3. From frame K, 
   * perform EMD matching on frame K-1, K, K+1, ..., K+t (t is a constant, called context depth)
   * identify reliable segmentation and matching, and identify bad cases (maybe error segmentation or error matching)
   * conduct active contours only on bad cases, while the confirmed reliable cells can provide more context for contour evolutions
   * update segmentation in frame k

#### How does each module help the other?

* Matching --> Contour Evolution:  
  * The matching step helps to reduce the amount of computation needed for evolutions, because only a portion of cells are involved in contour evolution in practice.
  * The matching step helps to provide good contour initialization in the next frame for contour evolution, which alleviates the strong assumption of small cell displacement in classic contour evolution based methods
* Contour Evolution --> Matching
  * The contour evolution module helps to provide an opportunity to refine the segmentation results. It is easy to understand that better segmentation can lead to better matching, especially when pre-segmentation quality is poor.



## References

[1] Jianxu Chen, Cameron W. Harvey, Mark S. Alber, and Danny Z. Chen. "A Matching Model Based on Earth Mover’s Distance for Tracking Myxococcus xanthus." In *International Conference on Medical Image Computing and Computer-Assisted Intervention*, pp. 113-120. Springer International Publishing, 2014. 

[2] Jianxu Chen, Shant Mahserejian, Mark S. Alber, and Danny Z. Chen. "A Hybrid Approach for Segmentation and Tracking of Myxococcus xanthus Swarms." In *International Conference on Medical Image Computing and Computer-Assisted Intervention*, pp. 284-291. Springer International Publishing, 2015.

[3] Jianxu Chen, Mark S. Alber, and Danny Z. Chen. "A Hybrid Approach for Segmentation and Tracking of Myxococcus xanthus Swarms." To appear in *IEEE Transactions on Medical Imaging*, 2016.

[4] Jianxu Chen, Yiqing Cai, Chen Wei, Lin Yang, Mark S. Alber, and Danny Z. Chen. "Segmentation and Tracking of Pseudomonas aeruginosa for Cell Dynamics Analysis in Time-Lapse Images." In *IEEE International Symposium on Biomedical Imaging (ISBI)*, pp. 968-971, 2016.







