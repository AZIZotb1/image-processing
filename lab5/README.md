# Lab 5 – Spatial Filtering: Smoothing and Sharpening

**Course:** ARTI 406 – Image Processing  
**Department:** Computer Engineering, College of Computer Science and Information Technology  
**Academic Year:** 2025–2026

---

## Overview

This lab explores spatial filtering techniques for image smoothing and sharpening using Python and OpenCV. It covers box filtering, Gaussian filtering, and Laplacian-based sharpening.

---

## Files

| File | Description |
|------|-------------|
| `Lab5_Spatial_Filtering.ipynb` | Main Jupyter notebook with all tasks |
| `boat.png` | Input image used for all tasks |
| `unsharp_masking.png` | Procedural example output |
| `task1_box_filter.png` | Task 1 output |
| `task2_gaussian_filters.png` | Task 2 output |
| `task3_laplacian_sharpening.png` | Task 3 output |
| `README.md` | This file |

---

## Tasks

### Procedural Example – Unsharp Masking
Applies Gaussian blur then subtracts it from the original (scaled by `amount`) to sharpen the image.

### Task 1 – 7×7 Box Filter
Convolves the image with a 7×7 averaging (box) filter using `cv2.blur()`. Displays the original and smoothed images side by side.

### Task 2 – Gaussian Filtering (5×5 vs 21×21)
Applies two Gaussian filters of different sizes to demonstrate the effect of kernel size on blur strength. Shows original, 5×5, and 21×21 results side by side.

### Task 3 – Laplacian Sharpening
1. Read the image
2. Convert to float32
3. Apply `cv2.Laplacian()` with a 3×3 kernel
4. Sharpen using: `sharpened = np.clip(image_float - laplacian, 0, 1)`
5. Display original, Laplacian output, and sharpened image

---

## Requirements

```
Python 3.x
opencv-python
numpy
matplotlib
```

Install with:
```bash
pip install opencv-python numpy matplotlib
```

---

## How to Run

1. Place `boat.png` in the same directory as the notebook.
2. Open `Lab5_Spatial_Filtering.ipynb` in Jupyter or JupyterLab.
3. Run all cells (Kernel → Restart & Run All).
