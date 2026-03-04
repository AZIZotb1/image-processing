# Lab 4 – Intensity Transformations and Filtering: Spatial Domain

**Course:** ARTI 404 – Image Processing  
**Department:** Computer Engineering  
**College:** College of Computer Science and Information Technology  
**Session No.:** 4 

---

## Overview

This lab covers histogram-based image enhancement techniques including contrast stretching, histogram equalization, and histogram matching using Python and the `scikit-image` library.

---

## Assessment Tasks

### Task 1: Contrast Stretching (3rd – 80th Percentiles)

**Objective:** Rescale the intensity values of the moon image to include all intensities within the **3rd and 80th percentiles**.

**Approach:**
- Load `skimage.data.moon()`
- Compute `p3, p80 = np.percentile(img, (3, 80))`
- Apply `exposure.rescale_intensity(img, in_range=(p3, p80))`
- Plot original and contrast-stretched images with their histograms side-by-side

**Key Observation:** Stretching to the 3rd–80th percentile range clips the darkest and some of the brighter pixels, aggressively boosting contrast in the mid-tonal range.

---

### Task 2: Histogram Equalization

**Objective:** Equalize (flatten) the histogram of the moon image using `exposure.equalize_hist`.

**Approach:**
- Load `skimage.data.moon()`
- Apply `exposure.equalize_hist(img)` — returns a float image in range [0, 1]
- Plot original and equalized images with their histograms side-by-side

**Key Observation:** Histogram equalization redistributes intensities uniformly across the full range, revealing details in both dark and bright regions. The resulting histogram is approximately flat.

---

### Task 3: Histogram Matching

**Objective:** Match the histogram of the **chelsea** image (source) to the **rocket** image (reference) using `match_histograms`.

**Approach:**
- Load `source = skimage.data.chelsea()` and `reference = skimage.data.rocket()`
- Apply `match_histograms(source, reference, channel_axis=2)` (per-channel RGB matching)
- Visualise all three images side-by-side
- Plot per-channel (R, G, B) histograms for source, reference, and matched images

**Key Observation:** After matching, the tone distribution of each colour channel in the matched image closely mirrors that of the rocket reference. The chelsea image visually shifts to the cooler, darker palette of the rocket image.

---

## Repository Structure

```
Lab4/
├── Lab4_Assessment.ipynb          # Jupyter notebook with all tasks and outputs
├── task1_contrast_stretch.png     # Output image – Task 1
├── task2_histogram_equalization.png  # Output image – Task 2
├── task3_histogram_matching_images.png    # Output image – Task 3 (images)
├── task3_histogram_matching_histograms.png # Output image – Task 3 (histograms)
└── README.md                      
```

> **Note:** All images used in this lab are built-in datasets from `skimage.data` (`moon`, `chelsea`, `rocket`). No external image files are required.

---

## Requirements

Install dependencies with:

```bash
pip install scikit-image matplotlib numpy
```

Or using Anaconda:

```bash
conda install scikit-image matplotlib numpy
```

**Python version:** 3.8+

---

## How to Run

1. Open Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook Lab4_Assessment.ipynb
   ```
2. Run all cells sequentially (`Kernel > Restart & Run All`).
3. Output figures will be displayed inline and saved as `.png` files in the same directory.

---

## References

- [Hands-On Image Processing with Python](https://play.google.com/books/reader?id=gC59DwAAQBAJ&hl=ar)
- [scikit-image: Histogram Equalization](https://scikit-image.org/docs/stable/auto_examples/color_exposure/plot_equalize.html)
- [scikit-image: Histogram Matching](https://scikit-image.org/docs/0.24.x/auto_examples/color_exposure/plot_histogram_matching.html)
