## Introduction
[Gatys et al.](http://openaccess.thecvf.com/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) published in 2016 introduced a novel way of using CNNs to transfer the style of an image 
to the content of another image. This process is also known as Neural Transfer. 

The idea is to use the feature maps learned during the training of a CNN model to take a new image and reproduce it with a new artistic style.

## Implementation
The code was implemented using Pytorch 1.0

Following results were attempted to replicate as shown in the paper:-

* Given a content image and style image , output a new image that combines the style and content from original images(Figure 3 in the paper)
* Show the effect of relative weighting of content and style i.e. effect of ratio `alpha/beta`(Figure 4 in the paper)
* Effect of matching content representation in different layers of the network. (Figure 5 in the paper)
* Effect of initialization of target image from content image vs style image (Figure 6 in the paper)

#### CREDITS
The idea for this project came from the content and an exercise from an Udacity course
called [Intro to Deep Learning with PyTorch](https://www.udacity.com/course/deep-learning-pytorch–ud188).
Some of the code has been adapted from there, as well as the [official Pytorch tutorial](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html). 

## Results

#### STYLE TRANSFER USING DIFFERENT STYLE IMAGES
The following figure shows the results of applying the style transfer algorithm to a sample image for different style images. 
This figure is analogus to figure 3 of the paper.
* Parameters used: alpha/beta ratio was 1x10^(-4) and the optimizer was run for 8000 steps.
![Figure 3](/results/results_figure_3.png)



#### EFFECT OF INITIALIZATION OF GRADIENT DESCENT
This figure is analogus to figure 6 of the paper.
The following figure shows results after initializing the target image from different images(Content/Style/White Noise).
* Parameters for initialization from Content Image: Runs=8000, alpha/beta=1x10^(-4)
* Parameters for initialization from Style Image: Runs=15000, alpha/beta=1
* Parameters for initialization from White noise Image: Runs=25000, alpha/beta=1





Different parameters were used here because the parameters used in the paper i.e. alpha/beta ratio of 1x10^(-3) did not yield same results using same number of runs. It was noticed that the initialization with style or white noise images required more number of runs and a more balanced ratio of alpha/beta to give reasonable results.
![Figure 6](/results/results_figure_6.png)


#### FIGURE 4 and 5
No differentiable results could be reproduced for Figure 4 and Figure 5  shown in the paper by using the same set of parameters specified in the paper.
