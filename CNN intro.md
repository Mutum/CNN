

Here I am trying to explain below topics as simple as possible. My expectation from readers for now is to have good intuition.

# Convolution: 

Mathematically, Convolution is a way of combining two inputs/information/signal to give a third inputs/information/signal. Intuitively, you can imagine two jugs full of information, each having their own recipe describing rule of mixing with other, poured into a jug and mixed them with a specific rule. Anyway, Mathematical expression below:

![convolution](https://www.superdatascience.com/wp-content/uploads/2018/08/Convolutional_Neural_Networks_CNN_Step1_Img1.png)

In the below image, an image (5x5 green matrix) is convolve by a 3x3 orange matrix to give our output matrix. We slide orange matrix on greeen and do element wise matrix multiplication and adds them finally to give matrix output.


![convolution](http://deeplearning.stanford.edu/wiki/images/6/6c/Convolution_schematic.gif)


# Filters/Kernels

In above visualization, the orange 3x3 matrix which slide accross input image is called Filters or kernels in CNN. Filters are generally odd square matrix, though even square matrix is possible.It is quite clear that with different values in Filters, we 
have different outputs, Hence Filters acts as a feature detactor from our inputs.  

In image processing, with different kernel convolve to an image, we can get outputs for blurr,sharp,edge detection etc.

![Filters](https://www.superdatascience.com/wp-content/uploads/2018/08/Convolutional_Neural_Networks_CNN_Step1_Img6.png)
![Filters](https://www.superdatascience.com/wp-content/uploads/2018/08/Convolutional_Neural_Networks_CNN_Step1_Img7.png)
![Filters](https://www.superdatascience.com/wp-content/uploads/2018/08/Convolutional_Neural_Networks_CNN_Step1_Img8.png)


# Feature Maps

The output matrix after convolved by a filter to an image/input is called Feature map.In above visualization, the output "Convolved Feature" is the Feature Map. More generally, it is depicted as below:

![CNN](https://www.superdatascience.com/wp-content/uploads/2018/08/Convolutional_Neural_Networks_CNN_Step1_Img3.png)
![CNN](https://www.superdatascience.com/wp-content/uploads/2018/08/Convolutional_Neural_Networks_CNN_Step1_Img4.png)


We can extracts many features with different kernels resulting many feature maps.
![CNN](https://www.superdatascience.com/wp-content/uploads/2018/08/Convolutional_Neural_Networks_CNN_Step1_Img5.png)


Feature Map`s size depends on three parameters :
    Depth: Number of filters in convolution.
    Stride: Number of pixels by which kernels slide across input image.
    Zero-padding: Referring below convolution,Values on edges of input image are less expose to kernels slide than other values.     By adding layers with Zeroes values around input image,we can expose edge values on input image more to kernels.

![convolution](http://deeplearning.stanford.edu/wiki/images/6/6c/Convolution_schematic.gif)

# 1x1 convolution

Suppose our kernel is 1x1 matrix (say with value 2), then our kernel would slide accross input image and gives feature map with twice the value of each pixel in input image.Refer below visualization.Okay, so why 1x1 convolution required? 

It is useful when we want to reduced dimension of input/image, therby reducing computation. Consider an image with 32 dimensions/channels say 6x6x32 (32 channels) convolved by 16 filters of 1x1x32 (32 dimension), then our feature map is 6x6x16 (16 dimension = number of 1x1 convolution filters)

![convolution](https://raw.githubusercontent.com/iamaaditya/iamaaditya.github.io/master/images/conv_arithmetic/full_padding_no_strides_transposed_small.gif)

# 3x3 convolution

When kernel size 3x3 say in 2Dimensional, then we are performing a 3x3 convolution. An example of 3x3 convultion with matrix dot multiplication is shown in first image below. Later a visualization of two successive 3x3 convolution.

A 3x3 convolution:
![3x3convolution](https://i.stack.imgur.com/NU7y2.png)

Two successive 3x3 convulutions:
![3x3convolution](https://i.stack.imgur.com/5tp2P.png)

# Epochs

In Neural network, to learn weights and biases we go through a steps of forward and backpropagation. A single implementation of forward and backpropagation to the whole training data is one epochs. And since we need to optimize weights and biases, there is necessity to have good number of epoch in training Neural Networks.

# Feature Engineering

It is an art and science of creating feature which represent our data problems (says prediction) appropriately. An effective Feature engineering would provide better predictive power. It is important skill as most of our real world data are dirty.

Eg. Creating feature of Weeekend (Yes or No) in fraud detection when we know from domain expertise, fraud detection occurs mainly on weekend.

# Activation Function 

While convolution by kernel execute linear transformation, We require to bring non-linearity in our network to give more complex because with more complexity comes with more predictive power. This is done by Activation function. 

In other words, Activation function brings non-linear decision boundary calculated on top of linear combination of the weights and bias (done by convolution here in CNN).

Some of the Activation functions are Sigmoid, tanh, Softmax, ReLU, Leaky ReLU etc. 


![Sigmoid](http://ufldl.stanford.edu/wiki/images/c/ca/Sigmoid_Function.png)

![tanh](http://ufldl.stanford.edu/wiki/images/a/aa/Tanh_Function.png)


# Okay let me put a picture depicting the CNN architecture

![3x3convolution](http://www.wildml.com/wp-content/uploads/2015/11/Screen-Shot-2015-11-07-at-7.26.20-AM.png)
