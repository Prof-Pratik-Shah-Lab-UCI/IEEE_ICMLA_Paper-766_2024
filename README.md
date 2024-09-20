
# Uncertainty quantified deep learning and regression analysis framework for clinical regions of interest segmentation in skin lesions



 # Gallery of Model Outputs

## Schematic diagram of the proposed approach.
This workflow presents a schematic diagram of the proposed approach.
- **Figure**:<br>
![las1 (1)](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/12c56dd9-6f8c-4b07-934c-adb9d13902bb)

## Proposed Algorithm for Dice Performance Calculation

Algorithm 1 is proposed to calculate the estimated Dice performance of Deep Learning Models (DLMs) using uncertainties for clinical Regions of Interest (ROIs) of skin images used in this study.


- **Figure**:<br>
  ![image](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/1e895420-afc4-4179-8e88-9e3137baa77d)

## Segmentation and Uncertainty Maps

This figure displays segmentation and uncertainty maps obtained from Bayes-by-backprop and Monte Carlo dropout augmented transfer learning (TL) and trained from scratch (TFS) deep learning models


- **Figure**:<br>

![comb (1)](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/c53402bb-0d76-462c-9852-8e8ba925ca46)

- **GT**: Ground Truth labels
- **Pred**: Model prediction
- **Unc**: Uncertainty
- **Bc**: Backprop
- **D**: Dropout

## Model Output Segmentation and Uncertainty Maps using Monte Carlo Dropout Trained From Scratch Deep Learning Model

- **Visualization**: Visualization of model output and uncertainty explanations for skin lesion  segmentation by a Monte Carlo dropout (MCD) trained using the TFS deep learning model and ISIC (The International Skin Imaging Collaboration) dataset images.
- **Figure**: <br>
![fig4](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/47b39977-4386-4d1a-a874-5198e3e9fbe9)

### Figure Description

- **A**: Input RGB image
- **B**: Binary mask of clinical ground-truth label (GT)
- **C**: Binary mask of segmentation from MCD output image
- **D**: Uncertainty estimate maps of binary segmentation of MCD model
- **E**: Uncertainty estimate maps of binary segmentation of MCD model for tumor tissue regions
- **F**: Uncertainty estimate map of binary segmentation of MCD model for non-tumor tissue regions
- **G**: Uncertainty estimate map of MCD model binary segmentation for non-tissue regions
- **Color Bar**: Shows the degree of model uncertainty, with deeper red indicating greater uncertainty and deeper blue indicating the least uncertainty (lowest value being 0).



## Model Output Segmentation and Uncertainty Maps using Monte Carlo dropout transfer learning deep learning model

- **Visualization**: Visualization of model output and uncertainty explanations for skin lesion  segmentation by a Monte Carlo dropout (MCD) trained using the TL deep learning model and ISIC (The International Skin Imaging Collaboration) dataset images.
- **Figure**:<br>
![fig5](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/ed4dcb57-824a-4d43-9e84-1924dd50bba0)

### Figure Description

- **A**: Input RGB image
- **B**: Binary mask of clinical ground-truth label (GT)
- **C**: Binary mask of segmentation from MCD output image
- **D**: Uncertainty estimate maps of binary segmentation of MCD model
- **E**: Uncertainty estimate maps of binary segmentation of MCD model for tumor tissue regions
- **F**: Uncertainty estimate map of binary segmentation of MCD model for non-tumor tissue regions
- **G**: Uncertainty estimate map of MCD model binary segmentation for non-tissue regions
- **Color Bar**: Shows the degree of model uncertainty, with deeper red indicating greater uncertainty and deeper blue indicating the least uncertainty (lowest value being 0).


##  True vs. False Positive Rates in TFS/TL models using DLM MCD /DLM Bc techniques.

- **Figure**:<br>
![tpr vs fps 2](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/34934d86-b681-4008-b326-f6d3bcf22620)

##   Visualizing the comparison of AUROC with training from scratch and transfer learning deep learning models by Monte Carlo dropout and Bayes-by-backprop.

- **Figure**:<br>
![ar_over](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/f2afa5fb-6707-4acc-b79f-11773116b237)

##   Visualizing Uncertainty Mean vs. Standard Deviation values in TFS/TL using DLM MCD /DLM Bc.

- **Figure**:<br>
![means vs std (1)](https://github.com/bin112/MLHC_2024_skin_project/assets/20062780/5cf8041e-a472-4be0-9090-5df6a8a7eebe)

# FYI:

## Model Architecture

1. **Architecture Used**: VGG-16-UNet ( i.e., UNet encoder represents VGG-16 arch).

## Key Definitions

2. **TL** - Transfer Learning
   - TL indicates transfer learning using ImageNet pre-training.

3. **TFS** - Training from Scratch
   - TFS indicates training from scratch (no transfer learning involved).

4. **Data Folder**
   - Contains pre-processed skin data, split into TRAIN (80%) and TEST (20%).

- **Weights Folder**
  - Trained weights for skin lesion image segmentation are provided here.


# How to navigate output folders:

- [skin_cancer] (refers to dataset used)
  - [TFS/TL]_backprop (specifies which version of model used)
    - unc
      - unc_data.txt (mean/med/mode/stddev/min/max uncertainties for each image)
      - unc_data_threshold.txt (similar to unc_data.txt but all instances of 0.0 uncertainty removed)
      - [uncertainty maps generated by model]
    - evaluation.txt (data on model accuracy/TPR/FPR for each test image)
    - [segmentations generated by model]
  - [TFS/TL]_dropout (specifies which version of model used)
    - unc
      - unc_data.txt (mean/med/mode/stddev/min/max uncertainties for each image)
      - unc_data_threshold.txt (similar to unc_data.txt but all instances of 0.0 uncertainty removed)
      - [uncertainty maps generated by model]
    - evaluation.txt (data on model accuracy/TPR/FPR for each test image)
    - [segmentations generated by model]
  - [TFS/TL]_combined (combined means backprop and dropout unc. maps are combined)
    - [combined uncertainty maps from the backprop and dropout versions of model]



6. To get model outputs for the test images, navigate to the individual folder for transfer learning (folder 'seg_TL') and training from scratch (folder 'seg_TFS') and run: python test.py

# Dependencies:
 - Python 3.6.7, Tensorflow 1.12.0, Tensorflow-probability 0.5.0, OpenCV 4.1.1 

Create a conda environment and use conda installations (i.e., using the Anaconda distribution) within that environment on your machine for this and make sure these versions match. You can make a Python 3.6 environment using conda and install these within it.
