# Fiber Optic Mode Calculator

A Python-based tool for calculating and visualizing the propagation modes in optical fibers. This project analyzes single-mode and multimode fiber characteristics, including modal patterns, cutoff wavelengths, and dispersion properties.

## Table of Contents

- [Overview](#overview)
- [Theory](#theory)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [References](#references)

## Overview

Optical fibers guide light through a process of total internal reflection. Depending on the fiber's dimensions and refractive index profile, different electromagnetic field patterns (modes) can propagate through the fiber. This project provides tools to:

- Calculate supported modes in a given fiber
- Determine single-mode operation conditions
- Visualize modal field patterns
- Analyze dispersion characteristics
- Compute wavelength cutoff values

### Target Application
This project is designed for students and engineers learning photonics, particularly those pursuing advanced courses like the EPSRC CDT in Photonics and Electronic Systems.

## Theory

### Modal Analysis in Optical Fibers

Optical fibers are cylindrical waveguides characterized by:
- **Core radius** ($a$)
- **Core refractive index** ($n_1$)
- **Cladding refractive index** ($n_2$)
- **Operating wavelength** ($\lambda$)

#### Normalized Frequency (V-number)

The V-number determines how many modes can propagate:

$$V = (\pi\times a/\lambda)\times \sqrt{(n_1^2 - n_2^2)}$$


**Key thresholds:**
- V < 2.405: Single-mode operation (only fundamental HE₁₁ mode)
- V > 2.405: Multimode operation (multiple modes supported)

#### Mode Classifications

Modes are designated as HE_mn, TE_0n, TM_0n, or EH_mn where:
- **HE/EH**: Hybrid modes (dominant in weakly guiding approximation)
- **TE/TM**: Transverse electric/magnetic modes
- **m, n**: Azimuthal and radial mode numbers

#### Cutoff Wavelength

The cutoff wavelength for mode mn is:

$$\lambda_{\text{cutoff}(mn)} = \frac{\pi a \times \sqrt{(n_1^2 - n_2^2)}}{p_{mn}}$$


where p_mn is the m-th zero of the Bessel function derivative.

#### Modal Dispersion

Different modes travel at different velocities, causing signal broadening:
