# Image Resizing with Domain Generalization: A Focus on Faces & Endoscopic Imagery

This project investigates the challenges of using machine learning to resize images, particularly in the context of domain shifts. The goal is to upscale face images and endoscopic images while maintaining image quality across various resizing operations.

## Introduction

With the increasing adoption of big data applications, there's an emergent need to optimize storage, especially in the context of image data. However, domain shifts like hardware variations, differing light conditions, and the innate differences in image types pose challenges.

## Objectives

1. Use ML to upscale face and endoscopic images while maintaining image quality.
2. Account for domain generalization.
3. Test the viability of training on one image type and resizing another using the same algorithm.

## Methodology

### Datasets:
- **Human Faces Dataset**: Images were downscaled to half their original resolution and split using an 80:20 ratio for training and testing.
  
- **Endo41E Dataset**: This dataset required no additional processing.

### Implementation:
1. **Baseline Models**: Used RDN and SRCNN.
   - Trained on the Endo41E training set and tested on both test datasets.
   - Trained on the Human Faces training set and tested on both test datasets.
   - Calculated RMSE between the original and reconstructed images.
   
2. **Diffusion Models**: 
   - Intra-domain and inter-domain errors were assessed.
   - The speed was also a consideration, with a focus on producing high-quality images quickly.
   - The hypothesis that diffusion models trained on faces might not work well on endoscopy images was tested and evaluated.

## Key Findings:

- **Baseline Analysis**:
  - SRCNN trained on the Endo41E dataset produces optimal results for overexposed cases.
  - RDN trained on face images exhibits the best performance for certain scenarios.
  - The effect of domain transfer is evident but not extremely drastic.
  
- **Diffusion Model Analysis**:
  - Reduced error both within and across domains without compromising speed.
  - The results contrasted with some of our initial hypotheses.

## Conclusion:

Through this project, we showcased the potential of diffusion models in enhancing image resizing tasks. By accounting for domain generalization, we were able to achieve significant improvements in resizing quality across both face and endoscopic images.
