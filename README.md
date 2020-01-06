# Prediction-of-rotation-angle-of-hand-X-Ray-images

For this project, we used a dataset consisting of hand PA x-rays. The dataset has already been preprocessed such that they are all the same size, RBG images, cropped in around the hand, and oriented such that they are all right hands. The data is separated into 3 folders, train, valid, and test. Each of these folders contains the images for that data subset. These files list the image name in the 1st column and the label (rotation in degrees corresponding to that image) in the second column. I only submit a subset with smaller size. We used these to straighten out any coding errors, as using the full training set will make iteration very slow. 

Our job is to build a regression model to predict the rotation of these hands. We used resnet-18 to make the prediction and used MSE for the loss function.

The first task is to write the dataset class to read this data. This is the class that is fed into the data loader. This includes train-time augmentation of data. The only augmentation to perform is to rotate the images randomly. 

Once we have model training (from random initialization), we experiment with different learning rates and batch sizes. We also play around with including the imagenet pretrained weights and with freezing different layers of the pretrained model. 
