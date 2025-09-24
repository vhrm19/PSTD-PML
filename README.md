# Acoustic Wave Simulation with PSTD and PML

This repository contains a Python implementation of a **2D acoustic wave simulator** using the **Pseudo-Spectral Time-Domain (PSTD)** method with **Perfectly Matched Layers (PML)** for absorbing boundaries.
Based in the paper:
Qing Huo Liu, "The pseudospectral time-domain (PSTD) algorithm for acoustic waves in absorptive media," in IEEE Transactions on Ultrasonics, Ferroelectrics, and Frequency Control, vol. 45, no. 4, pp. 1044-1055, July 1998, doi: 10.1109/58.710587.

## Advantages of PSTD over FDTD according to the author of the paper:
- **High spatial accuracy**: infinite-order derivatives via FFT (vs. second-order in FDTD).  
- **Fewer grid points**: only 2 points per wavelength needed (FDTD requires 10–20).  
- **Lower dispersion error**: no spatial dispersion; only temporal error remains.  
- **More efficient**: drastically reduces memory and CPU use, especially in large-scale problems.  
- **Simpler grids**: fields stored at cell centers (no staggered grid issues).  
- **PML compatibility**: eliminates wraparound effects for unbounded media.  


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

## Wraparound effect and PML

In PSTD simulations, spatial derivatives are computed via FFT, which assumes periodic boundaries. This causes the **wraparound effect**, where waves exiting one side of the grid reappear on the opposite side, producing non-physical artifacts. To avoid this, **Perfectly Matched Layers (PML)** are used at the domain edges, absorbing outgoing energy and effectively suppressing the wraparound caused by FFT periodicity.

### Wave propagation in a nonhomogeneous medium without PML
![Punctual Source](media/wraparound_effect.gif)

### Wave propagation in a nonhomogeneous medium with PML
![Smoothed Source](media/pml_effect.gif)

In the case of a **nonhomogeneous medium** with velocities ranging from 1500 m/s to 4000 m/s, two animations illustrate the impact of boundary conditions. The first animation (without PML) clearly shows the **wraparound effect**, as waves reaching the boundaries reappear on the opposite side due to FFT periodicity. In contrast, the second animation (with PML) demonstrates how the absorbing layers suppress this artifact, allowing waves to exit the domain naturally.

## Large contrasts in material properties

As noted in the paper: *"large contrasts in material properties, little Gibbs phenomenon is observed."* Using a high source gain (`gain = 10e3`) and a interface from 4000 m/s to 300 m/s makes this subtle effect visible.

### Little Gibbs phenomenon in a nonhomogeneous medium with PML
![Smoothed Source](media/pml_effect.gif)
