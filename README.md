# Single Image Super-Resolution with Diffusion Models

This project focuses on enhancing the resolution of gravitational lensing images using diffusion models. The goal is to improve the clarity and detail of these images, aiding in better scientific analysis and discoveries.

## Project Overview

### Gravitational Lensing

Gravitational lensing is a phenomenon predicted by Einstein's theory of general relativity. It occurs when a massive object, like a galaxy cluster or black hole, bends the path of light from a distant source. This can create multiple images, arcs, or rings of the source, depending on the alignment and mass distribution of the lensing object.

### Importance of Super-Resolution

Enhancing the resolution of gravitational lensing images is crucial for:

- **Improved Accuracy:** Clearer images allow for more precise measurements of lensing effects, leading to better estimates of the mass and distribution of dark matter.
- **Detecting Faint Sources:** Higher resolution reveals faint, distant galaxies that are magnified by the lensing effect but obscured in lower-quality images.
- **Studying Cosmic Structure:** Enhanced images provide better insights into the structure and evolution of galaxies and galaxy clusters.

## Dataset

The dataset consists of 2,834 pairs of Low Resolution (LR) and High Resolution (HR) images. The LR images are derived from the HR images by adding Gaussian noise and applying blurring.

## Models and Techniques

### Denoising Diffusion Probabilistic Models (DDPM)

Introduced by Ho et al. in 2020, DDPMs learn to denoise a pure noise signal into a target sample. The process involves a forward diffusion that adds noise to data and a learned reverse denoising process.

### SR3 (Super-Resolution via Repeated Refinement)

Developed by Saharia et al. in 2021, SR3 starts with Gaussian noise and refines the image through denoising steps conditioned on the low-resolution input.

### SRDiff

Introduced by Li et al. in 2021, SRDiff uses diffusion probabilistic models to generate high-resolution images from low-resolution inputs. It employs a U-Net architecture for conditional noise prediction and an RRDB-based low-resolution encoder.

### ResShift

An efficient diffusion model for image super-resolution, ResShift transitions between high-resolution and low-resolution images by shifting their residuals. It achieves high-quality results with fewer steps, offering faster inference compared to previous methods.

### CG-DPM (Conditional Guided Diffusion Probabilistic Model)

A novel approach combining a conditional diffusion model with a score-based guided network. CG-DPM uses a redesigned U-Net architecture to incorporate conditional low-resolution images and a guided network trained with a score-based loss function for more accurate high-resolution outputs.

### Loss Function

The primary loss function used in training is Mean Absolute Error (MAE).

## Results

### Quantitative Results

| Model   | PSNR  | SSIM  |
|---------|-------|-------|
| DDPM    | 26.95 | 0.821 |
| SR3     | 28.81 | 0.854 |
| SRDiff  | 34.71 | 0.87  |
| ResShift| 35.55 | 0.879 |
| CG-DPM  | 33.447| 0.851 |

*Results on the Test Dataset*

## Future Work

- Exploring Score-Based Conditional Diffusion Models.
- Investigating Diffusion GANs.
- Exploring various loss techniques.
- Investigating the best techniques with a residual prediction approach.

## Installation

1. **Clone the repository:**

   ```sh
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name
