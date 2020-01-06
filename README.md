# Prediction-of-rotation-angle-of-hand-X-Ray-images

1. Introduction:

This project asks us to implement a convolutional neural network and to predict the rotation angle based on a set of hand PA x-rays. There are several core steps to complete:
* Read data and label dataset class to fed into the data loader.
* Build the structure of convolutional neural network by ResNet-18 module.
* Make regression to predict the rotation angles of hands
* For training fast, use GPU to compute the network.

2. Dataset

The dataset consisting of hand PA x-rays, it has already been preprocessed such that they are all the same size, RBG images, cropped in around the hand, and oriented.
* Training Set: 600 images
* validation Set: 208 images
* Test set: 200 images

There are also 3 files called train_labels.csv, valid_labels.csv, and test_labels.csv. These files list the image name in the 1st column and the label (rotation in degrees corresponding to that image) in the second column. I only submit a subset with smaller size. We used these to straighten out any coding errors, as using the full training set will make iteration very slow. 

3. Method:

We write a mydata class. In this class we load data and labels, do train-time augmentation and rotate the images 15o randomly. We augment the training set, rather than validation and testing set. Then we write the parameters into our file to find the best one. In the  ResNet-18 module, we set the learning rate of the third layer, fourth layer and fully connected layer. Then we use MSE as loss funtion.

4. Result

We trained for 100 epoches, and the final training loss is 7.94871353837351, the final validation loss is 12.91610410831009. Then we calculate the test loss, then get the result 9.745383987426758. So we think our parameter is a good fit for our code. 
