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

Understanding the 3D nature of our data, we opted for a robust architecture:

- **Model Type:** 3D U-Net
- **Convolution:** Applied across all three dimensions for comprehensive feature extraction.

## Training Configuration

Ensuring optimal learning, our training configuration is as follows:

- **Loss Function:** Crossentropy
- **Optimizer:** Adam
- **Learning Rate:** 0.0001
- **Epochs:** 25

## Results and Performance

After 25 epochs of intensive training, our model demonstrated notable proficiency:

- **Validation Dice Score:** 0.5

Feel free to delve into the codebase, tailor it to your needs, and explore further improvements. If you have any inquiries or suggestions, don't hesitate to reach out—we're here to collaborate and enhance this impactful project!
