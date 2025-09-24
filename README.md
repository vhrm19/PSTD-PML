# Acoustic Wave Simulation with PSTD and PML

This repository contains a Python implementation of a **2D acoustic wave simulator** using the **Pseudo-Spectral Time-Domain (PSTD)** method with **Perfectly Matched Layers (PML)** for absorbing boundaries.

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
