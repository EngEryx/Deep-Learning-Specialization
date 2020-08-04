# Convolutional Neural Networks

Are powerful algorithms/technics used in computer vision to understand images.

Vertical Edge Detection

It's a technic to analyze edges, or contents in a picture.

To perform edge detection, we construct a filter, aka Kernel, for example, a grey image that is 6x6 is multiplied by a 3x3 kernel to get a 4x4 matrix. The kernel or filter is overlayed on a potion and shifted to the right by 1 step.

Padding

Pixels on the corners of the pictures are usually covered a few times.

Padding helps in the convolution process to solve this problem

nxn and convolve by fxf filter result is usually n-f+1 * n-f+1

After padding n+2p-f+1 * n+2p-f +1

**Valid** convolutions meaning no padding i.e n*n image convolved with a f*f filter 

**Same** means apply padding so that the output size is the same as the input size. i.e n+2p-f+1 

In computer vision the f values are usually odd, if f was even you would need some isometric padding and second is to have a central filter.

Strided Convolutions

Instead of the 1 step convention when applying a filter, if you apply a stride, it will take the stride size steps vertically and horizontally in the convolution process.

nxn * fxf  with padding p and strides s  = 2 ;output: n+2p-f/2 + 1 * n+2p-f/2 + 1

Cross-correlation vs Convolutions

The Convolutions used in ML are in math books referred to as Cross Correlations.

ML apps do need the flipping of the filter matrix.

Convolution over 3D volumes.

This is a guide on how to perform convolutions over a coloured image i.e RGB

In this case, the filter dimensions ad are adjusted  i.e height width and the number of channels

e.g 6x6x6 * 3x3x3 =  4x4x1

One Layer of Convolutional Neural Networks

Types of ConvNets

1. Convolutions
2. Pooling
3. Fully Connected

Pooling : 

Max Pooling - We take the max number within the filter area, other concepts such strides or padding are still applied.

Average Pooling - We take the average the filter area

One shortcoming on pooling is that there are no parameters to learn.

Assignment

Implementing building blocks of a convolutional neural networks:- 

- Convolution functions, including:
    - Zero Padding
    - Convolve window
    - Convolution forward
    - Convolution backward (optional)
- Pooling functions, including:
    - Pooling forward
    - Create mask
    - Distribute value
    - Pooling backward (optional)
1. Zero-padding implementation 

    Zero padding adds zeros around the border of an image.

    Some of the benefits of padding include;

    - It allows one to use a CONV later without necessarily shrinking the height and width of the volumes. This is important of DNNs since as you go deeper the height/width shrink esp. in SAME in convolution.
    - It helps keep more information at the border of an image.
2. Single Step Convolution

    Takes input volume, applies filter at every position of the input and outputs another volume, usually of a different size.