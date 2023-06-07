# Computer Vision in Tennis

### Group: 22
### Members: 

#### Alexandru Bobe: 
#### Bogdan Simion: 5850185
#### Onno Verberne:
             
### This project was done in part to satisfy the requirements for the Seminar Computer Vision by Deep Learning course at TU Delft.
### We aim to reproduce some parts of the paper "TenniSet: A Dataset for Dense Fine-Grained Event Recognition, Localisation and Description". In this blog we’ll be elaborating on our efforts to reproduce the results, the issues we faced and the discussion about the possibility of reproducing the paper.

## Introduction

### 

## Project goals

### 

## Methodology
### Our work was divided into multiple steps from gathering the data to actually reconstruct the whole image. We worked with RetinaMNIST only as the time did not permit us to work with the ISIC dataset too.
### The first step was to gather the images from the dataset and split them into training and testing. There is nothing special about it, therefore we can move on to the second step, constructing the neural network for training. We mainly used the authors’ setup, although we changed it a little: we used 4 linear layers, after each one a ReLU layer and at the end a softmax layer. This layer is used for computing the probabilities of one image being labelled.
### The third step was to actually train the neural network and gather the important data: all the gradients from the network. The loss function was Cross Entropy Loss as we deal with softmax and for the optimizer we chose SGD (Stochastic Gradient Descent) with a learning rate of 0.005. The number of epochs was set to 1000.
### The fourth step and the most important one was to implement the algorithms presented in the paper: B.1, B.2 and B.3. The first algorithm is for determining the loss and the labels using the gradient at the last layer. The second algorithm is for determining the exact label reconstruction from the loss vector [1] and the last algorithm and the most important one is used for determining the activation patterns across the neural network.
### The fifth step involved reconstructing the data from the gradients and the losses. We start from a noise image and then, step by step we are reconstructing the image based on making the loss and the gradients closer and closer to the ground truth (the trained neural network).

## Results
## We do not have any significant results as we did not manage to finish the paper reproduction in time, although we have some results for the network training part, which is shown below.


## Issues
### The issues related to reproducing the paper is that even though we finished the implementation of all the algorithms, we didn’t successfully run the algorithms in the paper. The main issue is that the gradient value is not guaranteed to be non-zero, and the algorithm took the first gradient value inside a layer as the denominator to calculate the common results after dividing the gradient of the current layer by the gradient of the previous layer. The reason for the failure of the reconstruction of the results could also be the misuse of the mathematical notations, which will be discussed in the next session. During the process of reproducing the paper, we did find the concept is easy to handle, the mathematical model is understandable on a conceptual level, but it is hard to implement the algorithm due to the vague connection between the algorithm and the description of the algorithm. 

## Discussion
### The paper was written in a logical order, and readers can see the efforts authors put into the paper. For instance, the authors gave us a general background knowledge for deep learning and also explained in detail how the method works with intuitive illustration. However, the misuse of the mathematical notations are confusing in the process of reproducing the paper. The paper, unlike which paper usually keeps mathematical notations clear to readers, was full of mixed mathematical notations, and also the authors put too many mathematical notations embedded in the text, which we found annoying and confusing. What is more, in the description of the algorithm and the actual algorithm, it is hard to find connections in between. From where we stuck in reproducing the paper, we found it is hard to guarantee the gradients of the previous layer that we are aiming at has non-zero value. The authors neglect the fact that gradients could be zero, and it is impossible to reconstruct from zero gradients because of the divide by zero error.

## References

### [1] Pan X, Zhang M, Yan Y, Zhu J, Yang Z. Exploring the Security Boundary of Data Reconstruction via Neuron Exclusivity Analysis. In31st USENIX Security Symposium (USENIX Security 22) 2022 (pp. 3989-4006).
### [2] Rumelhart DE, Hinton GE, Williams RJ. Learning representations by back-propagating errors. nature. 1986 Oct 9;323(6088):533-6.
### [3] Yang J, Shi R, Ni B. Medmnist classification decathlon: A lightweight automl benchmark for medical image analysis. In2021 IEEE 18th International Symposium on Biomedical Imaging (ISBI) 2021 Apr 13 (pp. 191-195). IEEE.
### [4] Codella NC, Gutman D, Celebi ME, Helba B, Marchetti MA, Dusza SW, Kalloo A, Liopyris K, Mishra N, Kittler H, Halpern A. Skin lesion analysis toward melanoma detection: A challenge at the 2017 international symposium on biomedical imaging (isbi), hosted by the international skin imaging collaboration (isic). In2018 IEEE 15th international symposium on biomedical imaging (ISBI 2018) 2018 Apr 4 (pp. 168-172). IEEE. 



