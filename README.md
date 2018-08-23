# U-Net-Satellite

The aim of this project is road detection from satellite images using a variant of deep Convolutional Neural Networks which is known as U-Net. The output of the model is a segmentation mask which differentiates roads and other terrains.
 
 
 ## Dependencies
 
 - Keras
 - Numpy
 - Matplotlib
 - OS
 - OpenCV
 - H5py
 
 ## Overview
 
 ### Model

U-net is a encoder-decoder type network architecture for image segmentation. The name of the architecture comes from its unique shape, where the feature maps from convolution part in downsampling step are fed to the up-convolution part in up-sampling step. 




![alt text](U-Net-Satellite/images/u-net-architecture.png)
