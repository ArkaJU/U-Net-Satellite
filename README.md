# U-Net-Satellite; Segmentation based road detection framework using Keras

The aim of this project is road detection from satellite images using a variant of deep Convolutional Neural Networks which is known as U-Net. The output of the model is a segmentation mask which differentiates roads from other terrains.
 
 
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
The details of the architecture can be clearly seen in the notebook as the output of the "model.summary()" cell.

![](images/u-net-architecture.png)


### Advantages of U-Net

1. This architecture is really versatile and can be used for any reasonable image masking task.
2. It does not have any fully connected layers, therefore has no restriction on the size of the input image. 
   This feature allows us to extract features from images of different sizes.
3. High accuracy given proper training, adequate dataset and training time.


### Data

The inputs are resized to 256x256 from the original size of 600x600. The ground truths are binarized version of the input satellite images. Images are separated into train and test sets and stored in separate h5 files for convenience. Training set consists of 2087 images and test set consists of 20 images.


### Training

The model was trained for 30 epochs and took about 3 hours on colab GPU. After 30 epochs, the model training accuracy was about 97% and validation accuracy was about 95.25%.
The training vs validation loss is shown below :


![](images/Loss.jpeg)




## Results

The following images show the comparison of the original satellite image, ground truth, and it's corresponding prediction:

![](images/1.JPG)
![](images/2.JPG)

## References

- Original paper: [Arxiv](https://arxiv.org/abs/1505.04597)
- Useful blogs: 
     - [Vehicle Detection](https://chatbotslife.com/small-u-net-for-vehicle-detection-9eec216f9fd6)
     - [Medical Image Segmentation](https://towardsdatascience.com/medical-image-segmentation-part-1-unet-convolutional-networks-with-interactive-code-70f0f17f46c6)
- Original Dataset: https://people.eecs.berkeley.edu/~tinghuiz/projects/pix2pix/datasets/maps.tar.gz

