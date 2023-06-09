# Computer Vision in Tennis

### Group: 22
### Members: 

#### Alexandru Bobe: 5069831
#### Bogdan Simion: 5850185
#### Onno Verberne: 5883407

<!-- <details>

<summary>

*Introduction*
  
*Previous work*
  
*Project goals*
  
*Methodology*
  
*Results*
  
*Issues*
  
*Discussion*

</summary>

* Vegetables

</details> -->
             
### This project was done in part to satisfy the requirements for the Seminar Computer Vision by Deep Learning course at TU Delft.
### We aim to reproduce and to improve some parts of the paper "TenniSet: A Dataset for Dense Fine-Grained Event Recognition, Localisation and Description". In this blog we’ll be elaborating on our efforts to reproduce the results, the issues we faced and the discussion about the possibility of reproducing the paper.

## Introduction

### Sports, like every field, has enjoyed a steep advancement in technologies and algorithms. This is also the case for tennis. Since Hawk-Eye developement [1] many algorithms detecting the players' action, the score and tracking the ball were made. Some of the recent improvements in the field were encompassed by TrackNet [2], which trains a deep learning network, addressing the problem of tracking fast moving tiny objects and Optical Flow [3], a currently widely used technique for detecting moving objects. In terms of datasets, an important advancement was made by Faulkner and Dick [4], who created the TenniSet, a dataset focused on event detection based on the players movements and ball's position. However, we found some flaws: the slow computation time makes it impossible to use these approaches for any real-time analysis of a tennis match, useful in all the topics described above and these techniques are not yet cheap and viable ways to create an annotated dataset that could be further used in research. Further, we would like to divide our discussion into several parts: the previous work related to annotation using computer vision in sports; our project goals and what we are trying to implement; the results we have for this setting and in the end, the discussion about the results and issues we faced.

## Previous work

### One of the first groundbreaking innovations in terms of technologies used is Hawk-Eye [1]. It is a Computer Vision system that does automatic refereeing by tracking the ball using a set of expensive cameras. The data collected by this system is incredibly valuable for any tennis player in preparing for a match, however, usually hidden behind a huge paywall. 

### Targeting the entertainment part of tennis and focusing on the spectators, IBM developed a solution called Pre-Match Insights with Watson that tried to create a pre-match summary to attract spectators. The research is only explained in high-level and it is unclear if the tool can utilise computer vision techniques. However, it creates a direction of interesting research.

### Passionate tennis fans and researchers created different types of open-source datasets, like this charting project or the THETIS data set with videos of the different tennis shots. However, the difficulty to use these datasets has already been discussed in previous research (Mora, 2019).   

### Faulkner et. al (2017) created a database of annotated tennis matches for automatic tennis commentary generation, that we can use to build upon his research and improve the existing techniques of event recognition and detection.  

## Project goals

### We aim to reproduce some parts of the Computer Vision algorithms presented in "TenniSet: A Dataset for Dense Fine-Grained Event Recognition, Localisation and Description", namely event detection and recognition as well as providing a new approach. To improve the performance of tennis annotation we propose adding an optical flow component to the network which will serve as a secondary input to the annotation network. To address the computational costs of optical flow calculations we propose two methods: 
### a. Frame interpolation: https://arxiv.org/pdf/2011.06294v11.pdf where we use a network to calculate the intermediate optical flow frames. The paper here uses network distillation to improve the performance of an existing optical flow frame interpolation network.
### b.	Network distillation: We distill an existing optical flow network layer by layer using Craft Distillation: https://par.nsf.gov/servlets/purl/10171699

### In order to make sure that we were right about what is missing and that our proposed solution is feasible, we start by reproducing the results obtained by Faulkner et. al (2017). Afterwards, we try to see if their solution generalizes to unseen videos of official tennis matches. To test our proposed solution, we use the same dataset and analyse our newly trained models from different perspectives including accuracy and training time.    

## Methodology

###

## Results

###

## Issues
### 

## Discussion
### 

## References

### [1] Owens, N. E. I. L., Harris, C., & Stennett, C. (2003, July). Hawk-eye tennis system. In 2003 international conference on visual information engineering VIE 2003 (pp. 182-185). IET.
### [2] Huang, Y. C., Liao, I. N., Chen, C. H., İk, T. U., & Peng, W. C. (2019, September). TrackNet: A deep learning network for tracking high-speed and tiny objects in sports applications. In 2019 16th IEEE International Conference on Advanced Video and Signal Based Surveillance (AVSS) (pp. 1-8). IEEE.
### [3] Dosovitskiy, A., Fischer, P., Ilg, E., Hausser, P., Hazirbas, C., Golkov, V., ... & Brox, T. (2015). Flownet: Learning optical flow with convolutional networks. In Proceedings of the IEEE international conference on computer vision (pp. 2758-2766).
### [4] Faulkner, H., & Dick, A. (2017, November). Tenniset: a dataset for dense fine-grained event recognition, localisation and description. In 2017 International Conference on Digital Image Computing: Techniques and Applications (DICTA) (pp. 1-8). IEEE.
###



