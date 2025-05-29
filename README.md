# Predicting Retina Blood Vessel Segmentation using U-Net

## Dataset Description - 

The Retina Blood Vessel Segmentation dataset is a valuable resource for advancing the field
of medical image analysis and enhancing the diagnosis of retinal vascular diseases. This
dataset contains a comprehensive collection of retinal fundus images, meticulously annotated
for blood vessel segmentation. Accurate segmentation of blood vessels is a critical task in
ophthalmology as it aids in the early detection and management of various retinal
pathologies, such as diabetic retinopathy and macular degeneration.  
Content:  
The dataset comprises a total of 100 high-resolution retinal fundus images captured using state-
of-the-art imaging equipment. Each image comes with corresponding pixel-level ground truth
annotations indicating the exact location of blood vessels. These annotations facilitate the
development and evaluation of advanced segmentation algorithms.  
The dimension of each data sample is 512*512.  
The label of this dataset is the binary mask. Blood vessel pixels are labeled
1 and background pixels are labeled as 0.  

## Problem Statement -

This Retina Blood Vessel Segmentation dataset is being used to predict the
segmentation of retina blood vessels in retinal fundus images which is crucial for
diagnosing retinal vascular diseases.  

## Models -

U-Net 2 Layers 
U-Net 3 Layers 
U-Net 4 Layers 

## Dataset Preprocessing -

I first applied Histogram Equalization which increases the overall contrast of
the image by redistributing the intensity values of the entire image.  
Then I applied Contrast Limited Adaptive Histogram Equalization (CLAHE) which is an
adaptive technique used to enhance the contrast in local regions of the image.  
Next, I applied Data Augmentation to increase the size of my training dataset as the train
set originally had only 80 images and 80 masks. I used Random Rotation and Random
Flipping.  
In Random Rotation padding is added to make the images and masks square shaped.
Then, the images and masks are randomly rotated using a rotation angle from the given
range. The resulting images and masks are then cropped to match the 512*512
dimension.  
In Random Flipping, the images and masks are chosen randomly with a 50% probability
to be flipped horizontally.  
After Data Augmentation -  
Training Data Images - 320  
Training Data Maks - 320  
Once the augmented dataset is generated, I normalized the images and masks by
dividing by 255.0.  

## Training and Test Split -

The dataset was already split into Train and Test sets (80 and 20 respectively).
I split the Train set randomly into 80% Train and 20% Validation set.  

## Best Performed Models -

U-Net 2 Layer model with batch normalization layer with learning rate of 0.00001.
