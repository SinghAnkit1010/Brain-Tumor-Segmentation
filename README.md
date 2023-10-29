# Brain Tumor Segmentation Project

## Overview

Welcome to the Brain Tumor Segmentation project! This initiative focuses on leveraging advanced techniques to perform accurate segmentation of brain tumors using 3D MRI scans sourced from the BRATS dataset. The dataset comprises 3D MRI scans of the brain stored in the NIfTI format, offering four modalities: "FLAIR," "T1w," "T1gd," and "T2w." Our specific investigation hones in on the "FLAIR" modality for detailed analysis.

## Dataset Details

- **Data Format:** all MRI scans are stored in NIfTI file format
- **Modalities:** This dataset have 4 modalities FLAIR, T1w, T1gd, T2w
- **Label Classes:**
  - Class 0: Background
  - Class 1: Edema
  - Class 2: Non-enhancing Tumor
  - Class 3: Enhancing Tumor
- **Image Dimensions:** (240, 240, 155)

- **this is the axial view of MRI scan of a single patient:**

https://github.com/SinghAnkit1010/Brain-Tumor-Segmentation/assets/103994994/6aaac3b8-57eb-4f7a-ac15-b08de6695249



## Preprocessing 

we applied some preprocessing steps to prepare dataset for training:

1. **Cropping:** We applied cropping along each axis to resize the images to a more manageable shape of (128, 128, 128).
2. **Normalization:** Prior to model input, we normalized MRI scans for consistent and effective data processing.
3. **Augmentation Techniques:** we applied some augmentation techniques on training data such as RandomFlip and RandomBlur
4. **Data Split:** we have used 350 MRI scans for training and 50 MRI scan for validation
5. **Memory Optimization:** since our MRI data are of dimension (128,128,128),it is not feasible to fit into memory,
                             so we have used patching technique in which we have divided original MRI scans into 8 patches
                             of shape (64,64,64)

## Model Architecture

Understanding the 3D nature of our data, we opted for a robust architecture.
we have used 3D UNet model in which we feed 3D data to our model and convolution will apply along height,width and depth.
It is better to use model which take 3D MRI scans instead of using model which take 2D Slices of MRI scans,because it will leads to better accuracy.

## Training 

Ensuring optimal learning, our training configuration is as follows:

- **Loss Function:** Crossentropy
- **Optimizer:** Adam
- **Learning Rate:** 0.0001
- **Epochs:** 25

## Evaluation

After training our model for 25 epochs, we achieved dice score of 0.5 on validation data which can be improved by further training.
**this is the prediction of our model on a single validation data:**
##**Actual**


