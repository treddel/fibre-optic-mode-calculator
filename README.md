# Fiber Optic Mode Calculator

A Python-based tool for calculating and visualizing the propagation modes in optical fibers. This project analyzes single-mode and multimode fiber characteristics, including modal patterns, cutoff wavelengths, and dispersion properties.

## Table of Contents

- [Overview](#overview)
- [Theory](#theory)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)
- [References](#references)

## Overview

Optical fibers guide light through a process of total internal reflection. Depending on the fiber's dimensions and refractive index profile, different electromagnetic field patterns (modes) can propagate through the fiber. This project provides tools to:

- Calculate supported modes in a given fiber
- Determine single-mode operation conditions
- Visualize modal field patterns
- Analyze dispersion characteristics
- Compute wavelength cutoff values

## Theory

### Modal Analysis in Optical Fibers

Optical fibers are cylindrical waveguides characterized by:
- **Core radius** ($a$)
- **Core refractive index** ($n_1$)
- **Cladding refractive index** ($n_2$)
- **Operating wavelength** ($\lambda$)

#### Normalized Frequency (V-number)

The V-number determines how many modes can propagate:

$$V = (\pi a/\lambda)\times \sqrt{(n_1^2 - n_2^2)}$$


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

$$\Delta\tau = \frac{Ln_1}{2c}\times\frac{\Delta n_g}{n_1}$$


### Implementation Approach

This project uses the **weakly guiding approximation** and **JWKB method** for mode calculation, solving the characteristic equation numerically.

## Features

- ✅ Calculate V-number and modal cutoff wavelengths
- ✅ Determine single-mode range for custom fiber parameters
- ✅ Visualize modal field patterns (intensity distributions)
- ✅ Generate dispersion curves
- ✅ Export results to CSV and plots to PNG/PDF
- ✅ Interactive CLI for custom fiber specifications
- ✅ Pre-defined fiber models (SMF-28, MMF, etc.)

## Installation

### Prerequisites

- Python 3.8+
- pip (Python package manager)

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/treddelWhat/fiber-optic-mode-calculator.git
   cd fiber-optic-mode-calculator
   ```
2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

### Dependencies
- numpy: Numerical computations
- scipy: Bessel functions and optimization
- matplotlib: Visualization
- pandas: Data handling and export

## Usage
To be added! 

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## References
### Textbooks
- Agrawal, G. P. (2012). _Fiber-Optic Communication Systems_ (4th ed.). Wiley.
- Saleh, B. E. A., & Teich, M. C. (2007). _Fundamentals of Photonics_ (2nd ed.). Wiley-Interscience
- Snyder, A. W., & Love, J. D. (2012). _Optical Waveguide Theory_. Springer Science.

### Academic Papers
- Snyder, A. W. (1969). "Asymptotic expression for eigenfunctions of a waveguide." _IEEE Transactions on Microwave Theory and Techniques_.
