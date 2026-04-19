# Image Reconstruction using DeepWSD (Perceptual Optimization)

## Overview
This project implements a DeepWSD-inspired image reconstruction framework where a blank image is iteratively optimized to match a reference image using perceptual feature distributions. Instead of pixel-wise comparison, deep features extracted from a pretrained VGG16 network are compared using a Wasserstein-based distance metric.

## Methodology
- Initialize a blank (gray) image  
- Extract deep features using VGG16  
- Convert feature maps into patch-wise distributions  
- Compare distributions using 1D Wasserstein distance  
- Optimize the image using gradient descent  

## Improvements over Base Method
- Simplified 1D Wasserstein distance (efficient approximation)  
- Multi-scale feature comparison  
- L1 loss for pixel alignment  
- Total Variation (TV) loss for smoothness  
- InSAR-compatible preprocessing using grayscale conversion  

## Results
- Achieved >50% perceptual improvement  
- Successfully reconstructs images from blank initialization  
- Works on both natural image datasets (e.g., CIFAR-10) and scientific data (InSAR)

## Sample Outputs
Place generated results inside the `sample_outputs/` folder:
- comparison_1.png  
- comparison_2.png  
- improvement_plot.png  

## Dataset
Supports:
- CIFAR-10 (structured dataset)
- InSAR images (grayscale scientific data)

## How to Run

### Install dependencies
```bash
pip install -r requirements.txt
