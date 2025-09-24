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

## Simulation Results

The following animations show the acoustic wave propagation with PML absorbing boundaries:

### Example 1: Wave propagation in a homogeneous medium
![Homogeneous Medium](media/homogeneous.gif)

### Example 2: Wave propagation with a velocity anomaly
![Velocity Anomaly](media/anomaly.gif)
