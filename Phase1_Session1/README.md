## Result for the assignment: 

### print(score)

[0.034417986512565765, 0.9915] 



## Definitions:

# Convolution:

Convolution is a process of extracting features from the image or any given data, it is mostly used in image & signal processing. Given the input image dimensions, we take a filter with certain dimensions & convolve through out the image and perform the dot product between the values in image & filter data. 

if the image size is 5X5 and we choose 3X3 filter to convolve, the filter will go from top left to right & down with given stride for example 1, we get an output of 3X3.

![alt](https://i.ibb.co/jWzYM5p/IMG-20190227-111402.jpg)



# Filters/Kernels:

Filter or a Kernel is a matrix of a desired N*N shape used to extract features from an Input Image or any given data. Different kind of filters are used for different tasks in Image pre processing like Edge Detection, Blurring, Sharpening etc..

Sobel filter is one of the important filter used to do edge detection in the images, by changing the values we can do horizantal edge detection as well as vertical edge detection in images. 

![alt](https://i.ibb.co/HGn3NL0/IMG-20190227-112955.jpg)



# Epochs:

Epoch is basically one single pass of all the data through the network, in our case all the training data through the neural network. Epoch is one of the parameter that we can tune as we need.

For example you have a dataset with 10 images & you kept a batch size of 2, then that means it will take (10/2 = ) 5 iterations to complete 1 epoch. At the end you can specify epochs too..

It is good to go for more epochs, if you have a huge dataset, running through all the data more times will increase in accuracy too....because weights are updated after every epoch through back propagation. 



# 1x1 convolution:

Main advantage of using 1* 1 convolution is to reduce the parameters by decreasing no.of filters & maintaining the height and width parameters of an input. These technique is used in some of the state of the art architectures like Inception & others....

Suppose you have a 25x25x162 & you want to decrease the channel number to 32 for the output, we can use 1X1X162 of 32 filters which gives output as 25x25x32. 

![alt](https://i.ibb.co/hFhdQH3/IMG-20190227-113713.jpg)



## 3x3 Convolution:

This is a filter or kernel which is used mainly for Feature Extraction. Mostly only odd number filters used to do feature extraction, because we need to maintain the symmetry on all sides when extracting features per pixel in the image. 

3x3 is most used in the recent architectures because it is computationally efficient when compared with others bigger kernels and most compilers accelerated 3X3 kernel handle efficiently. 

Most import thing is less parameters 3x3 kernel will have 9 parameters which means 9 operations are required to compute. While 5X5 kernel will have 25 parameters it can be replaced with 2 3X3 kernels which has 18 parameters which are less than 25. 



## Feature Maps

Feature maps are the outputs you get after you do a convolution with some filter/kernel here let's say that convolution of 3X3 kernel on an input image. This feature maps consist of  all the features accumulated by that convolution as an output. Mostly at the starting layers, theses will be low level features like edges, textures and going down the layers, you can accumulate more important features like parts of objects & objects at last layers. 

1X1 is said to be good feature extractor accumulate the similar features together in single feature map. 



# Activation Function:

Activation function is a way of introducing (or) adding non linearity to our neural network model. Without activation functions our model just outputs a linear functions, it is said that without activation function & backpropagation our neural network is more or less like Linear Regression. 

While linear regression is good, it fails to learn complex functions, so in our neural network we introduce non-linearity so that our model learns better.  There are many types of activation functions, now a days most commonly used are Relu & Softmax. Relu is mostly used because it solves the problem of vanishing gradient by converting all negative values to zero. Softmax is used in  multi-class classification, it will give you the normalized output of all classes & all that adds up to 1, so that it will be easy to decide which output is activated. 

Main function of any Activation Function is, given the weighted sum , it transforms &  give you an number in a range of (0, 1) or max(0,input) depending on the type of activation. 



## Receptive Field

In layman terms, it means after every convolution, from the each pixel of feature map what is field of your view on the input image. Different kind of layers add different receptive filed to the network. 

Receptive Field basically means the field of view your network has, its good to keep the Global Receptive Field at least equal to the size of your objects in images or size of your images or more in some cases where you need to analyze the scene too...

Receptive Field is built based on your network architecture i.e.. layers you build in the network.