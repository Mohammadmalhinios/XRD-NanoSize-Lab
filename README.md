# XRD-NanoSize-Lab
🚀 Conceived, Engineered & Presented by Youssef Attia  
🎓 University spin-off competition  
📅 Advanced Materials Research & Engineering Initiative | 2025

XRD-NanoSize-Lab was developed as part of a technical competition organized in collaboration with a materials science spin-off, with the objective of designing a robust and reproducible computational tool for quantitative X-ray diffraction (XRD) analysis.

---

![Math](https://img.shields.io/badge/Math-Levenberg--Marquardt-9b59b6?style=for-the-badge&logo=gnuplot&logoColor=white)
![Physics](https://img.shields.io/badge/Physics-Scherrer--Equation-3498db?style=for-the-badge&logo=physics&logoColor=white)
![C++](https://img.shields.io/badge/C++-17-blue?style=for-the-badge&logo=c%2B%2B&logoColor=white)

This project provides a C++ pipeline for analyzing X-ray diffraction (XRD) data of alumina samples. It fits peaks using a **pseudo-Voigt profile** and calculates crystallite sizes using the Scherrer equation. The Levenberg-Marquardt fitting is implemented using **Eigen** for accurate and robust optimization.

---

## Pseudo-Voigt Profile

The pseudo-Voigt function used for peak fitting is:

$$
V(x, A, \mu, \sigma, \gamma) = \eta \cdot G(x, A, \mu, \sigma) + (1 - \eta) \cdot L(x, A, \mu, \gamma)
$$

where:

- **G(x, A, μ, σ)** is the Gaussian component  
- **L(x, A, μ, γ)** is the Lorentzian component  
- **η** is the mixing factor (0 ≤ η ≤ 1)  
- **A** is the amplitude  
- **μ** is the peak center  
- **σ** is the Gaussian width  
- **γ** is the Lorentzian widthth  
---

## Features

- Load XRD data from CSV files
- Preprocess data with smoothing and normalization
- Detect peaks in 2θ space
- Fit Voigt peaks using Levenberg-Marquardt (Eigen)
- Calculate FWHM and crystallite size
- Monte Carlo estimation of FWHM uncertainty
- Compute residuals and statistical anomaly score

---
## Scientific Highlights

- Fully self-contained nonlinear Voigt fitting implemented from first principles  
- Analytical Jacobian construction and LDLT-based Levenberg-Marquardt solver  
- Physics-constrained peak parameters for meaningful and reproducible results  
- Monte Carlo uncertainty propagation using residual-driven noise injection  
- Statistical residual anomaly scoring to detect peak asymmetry, secondary phases, or fitting inadequacy  
- Designed for longitudinal and comparative XRD analysis across multiple datasets

---
## Available databases

- [Crystallography Open Database (COD)](http://www.crystallography.net/cod/) — open-access
- Inorganic Crystal Structure Database (ICSD) — commercial
- Powder Diffraction File (PDF-4/PDF-2) — commercial

---

## Dependencies

- **C++17** compatible compiler (GCC ≥ 9, Clang ≥ 10, MSVC ≥ 2019)  
- **Eigen** (header-only library, version 3.4+)

No other external libraries are required. All other functionality uses standard C++17 libraries.

---

## Compilation

```bash
g++ -std=c++17 main.cpp xrd_analysis.cpp -I /path/to/eigen -o xrd_analysis
```
