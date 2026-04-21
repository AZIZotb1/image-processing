# Lab 6 – Frequency Domain Filtering

**Course:** ARTI 404 – Image Processing  
**Department:** Computer Engineering, College of Computer Science and Information Technology  
**Academic Year:** 2025–2026

---

## Overview

This lab explores image filtering in the **frequency domain** using the 2D Fast Fourier Transform (FFT). Filters are applied by multiplying their frequency-domain representation with the FFT of the image, then transforming back to the spatial domain via the inverse FFT.

---

## Files

| File | Description |
|------|-------------|
| `Lab6_Frequency_Domain.ipynb` | Main Jupyter notebook with all tasks |
| `procedural_laplacian.png` | Procedural example output |
| `task1_sobel_frequency.png` | Task 1 output |
| `README.md` | This file |

> **Note:** No external image file is needed. The Cameraman image is loaded directly via `skimage.data.camera()`.

---

## Tasks

### Procedural Example – Laplacian in Frequency Domain
Constructs the Laplacian filter analytically in the frequency domain using `-4π²(u² + v²)`, multiplies with the image FFT, then recovers the result via inverse FFT.

### Task #1 – Sobel Filters in the Frequency Domain
1. Define Sobel-X and Sobel-Y kernels
2. Embed each kernel into a zero-padded array of image size, centered and shifted with `ifftshift`
3. Compute the FFT of each padded kernel
4. Multiply with the image FFT in the frequency domain
5. Apply inverse FFT to recover edge maps
6. Compute gradient magnitude: √(Sobel_X² + Sobel_Y²)
7. Display: original, spectra, spatial outputs, and gradient magnitude

---

## Requirements

```
Python 3.x
numpy
matplotlib
scikit-image
```

Install with:
```bash
pip install numpy matplotlib scikit-image
```

---

## How to Run

1. Open `Lab6_Frequency_Domain.ipynb` in Jupyter or JupyterLab.
2. Run all cells (Kernel → Restart & Run All).
3. No image upload needed — the Cameraman image loads automatically.
