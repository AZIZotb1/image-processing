# Lab 3: Image Manipulations using OpenCV Library

**Session Number:** 3  
**Session Duration:** 150 minutes  
**Session Topic:** Image Transformations using OpenCV

## Session Outcomes
- Explain how digital images are represented and manipulated in a computer
- Apply geometric transformations to images (scaling, rotation, shearing)
- Apply intensity transformations to images (negative, log, power law)

## Tools/Software
- **Programming Language:** Python 3
- **IDE:** Jupyter Notebook
- **Libraries:** OpenCV (cv2), NumPy, Matplotlib

## Project Structure
```
lab3_solutions/
│
├── Lab3_Image_Transformations.ipynb    # Main Jupyter notebook with all solutions
├── README.md                           # This file
├── Lab3_Report.pdf                     # Detailed lab report
│
└── images/                             # Directory containing all images
    ├── input.jpg                       # Original input image
    ├── task1_scaled.jpg               # Scaled image (Task 1.1)
    ├── task1_rotated.jpg              # Rotated image (Task 1.2)
    ├── task1_sheared_horizontal.jpg   # Horizontal shear (Task 1.3)
    ├── task1_sheared_vertical.jpg     # Vertical shear (Task 1.3)
    ├── task1_sheared_combined.jpg     # Combined shear (Task 1.3)
    ├── task2_negative.jpg             # Negative transformation (Task 2.1)
    ├── task2_log.jpg                  # Log transformation (Task 2.2)
    └── task2_power_law.jpg            # Power law transformation (Task 2.3)
```

## Assessment Tasks Completed

### Task 1: Geometric Transformations
1. **Scaling** - Increased image size by 1.5x using `cv2.resize()`
2. **Rotation** - Rotated image by 120 degrees using affine transformation
3. **Shear** - Applied horizontal, vertical, and combined shear transformations

### Task 2: Intensity Transformations
1. **Negative Transformation** - Inverted pixel intensities (s = 255 - r)
2. **Log Transformation** - Applied logarithmic transformation with appropriate constant
3. **Power Law Transformation** - Used gamma correction (γ = 2.0) for contrast enhancement

## Installation and Setup

### Prerequisites
```bash
pip install opencv-python numpy matplotlib jupyter
```

### Running the Notebook
1. Navigate to the lab directory:
   ```bash
   cd lab3_solutions
   ```

2. Launch Jupyter Notebook:
   ```bash
   jupyter notebook Lab3_Image_Transformations.ipynb
   ```

3. Run all cells in sequence to see the transformations

## Key Concepts

### Geometric Transformations
- **Scaling**: Changes the spatial dimensions of an image
- **Rotation**: Rotates image around a center point using rotation matrix
- **Shear**: Distorts the shape by shifting pixels in specific directions

### Intensity Transformations
- **Negative**: Inverts brightness values, useful for enhancing dark details
- **Log**: Expands low intensities, compresses high intensities
- **Power Law (Gamma)**: Controls overall brightness and contrast
  - γ < 1: Brightens image
  - γ > 1: Increases contrast
  - γ = 1: No change

## Technical Details

### Transformation Matrices

**Scaling:**
```
M = [sx  0   0]
    [0   sy  0]
```

**Rotation (θ degrees):**
```
M = [cos(θ)  -sin(θ)  tx]
    [sin(θ)   cos(θ)  ty]
```

**Shear:**
- Horizontal: M = [[1, sx, 0], [0, 1, 0]]
- Vertical: M = [[1, 0, 0], [sy, 1, 0]]

### Intensity Transformation Formulas

1. **Negative:** s = L - 1 - r (where L = 256 for 8-bit images)
2. **Log:** s = c × log(1 + r)
3. **Power Law:** s = c × r^γ

## Results
All transformations were successfully applied to the input image. The results demonstrate:
- Proper scaling with maintained aspect ratio
- Accurate rotation without clipping
- Correct shear deformations
- Appropriate intensity adjustments for each transformation type

## Resources
- [OpenCV Documentation](https://docs.opencv.org/)
- [Image Transformations using OpenCV - GeeksforGeeks](https://www.geeksforgeeks.org/image-transformations-using-opencv-in-python/)
- [The Python Code - Image Transformations](https://www.thepythoncode.com/article/image-transformations-using-opencv-in-python)
- [Medium - Basic Intensity Transformation Functions](https://medium.com/@khanhson0811/basic-intensity-transformation-functions-and-example-with-opencv-1a56932f34ac)

## Submission
This lab includes:
- ✅ Jupyter notebook with complete solutions
- ✅ All transformed images in the images/ directory
- ✅ README documentation
- ✅ GitHub repository link (to be provided)

## Author
Lab completed as part of Image Processing course requirements.

## Notes
- All code is well-documented with explanations
- Results are displayed using matplotlib for better visualization in Jupyter
- Both color and grayscale transformations are supported
- Error handling is included for image loading operations
