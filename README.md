# Acoustic Wave Simulation with PSTD and PML

This repository contains a Python implementation of a **2D acoustic wave simulator** using the **Pseudo-Spectral Time-Domain (PSTD)** method with **Perfectly Matched Layers (PML)** for absorbing boundaries.
Based in the paper:
Qing Huo Liu, "The pseudospectral time-domain (PSTD) algorithm for acoustic waves in absorptive media," in IEEE Transactions on Ultrasonics, Ferroelectrics, and Frequency Control, vol. 45, no. 4, pp. 1044-1055, July 1998, doi: 10.1109/58.710587.

## Features
- 2D acoustic wave propagation solver
- Pseudo-spectral spatial derivatives (FFT-based)
- Perfectly Matched Layers (PML) for boundary absorption
- Configurable source (wavelet, frequency, position)
- Visualization of wavefield evolution

## Requirements
The notebook requires the following Python packages:
- `numpy`
- `matplotlib`
- `scipy`
- `tqdm` (optional, for progress bars)
- `jupyter`

Install them with:
```bash
pip install numpy matplotlib scipy tqdm jupyter
```

## Punctual source and Gibbs phenomena

The following animations show the acoustic wave propagation using PSTD, first uses a punctual source, where is possible to see the effect of the Gibbs phenomena spreading the signal.
The second animation is a smoothed source, where the source is occupying a 3x3 region multiplied by a gaussian kernel like.

### Wave propagation in a homogeneous medium with a punctual source
![Punctual Source](media/punctual_source.gif)

### Wave propagation in a homogeneous medium with a smoothed source
![Smoothed Source](media/smoothed_source.gif)
