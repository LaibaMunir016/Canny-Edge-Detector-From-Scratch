# Canny Edge Detector — From Scratch

A step-by-step implementation of the **Canny Edge Detection** algorithm built
from scratch using Python, NumPy, and OpenCV (used only for I/O and Sobel filters).

## Algorithm Pipeline
Input Image
│
▼

Noise Reduction       → Gaussian Blur (5×5, σ=1.4)
│
▼
Gradient Calculation  → Sobel X/Y → Magnitude + Angle
│
▼
Non-Maximum Suppression → Thin edges to 1-pixel width
│
▼
Double Threshold      → Classify pixels: strong / weak / none
│
▼
Hysteresis            → Keep weak pixels connected to strong ones
│
▼
Output Edge Map
## Stages Explained

| Step | Function | What it does |
|------|----------|--------------|
| 1 | `noise_reduction` | Smooths the image to suppress random pixel noise |
| 2 | `gradient_calculation` | Computes edge intensity and direction using Sobel operators |
| 3 | `non_max_suppression` | Thins thick edges by suppressing non-peak gradient pixels |
| 4 | `double_threshold` | Labels pixels as strong (255), weak (50), or background (0) |
| 5 | `hysteresis` | Finalizes edges — weak pixels survive only if adjacent to strong ones |


## Parameters You Can Tune

| Parameter | Location | Default | Effect |
|-----------|----------|---------|--------|
| Kernel size | `noise_reduction` | `(5,5)` | Larger = more blurring |
| Sigma | `noise_reduction` | `1.4` | Higher = smoother |
| `high_r` | `double_threshold` | `0.15` | Raise to detect fewer edges |
| `low_r` | `double_threshold` | `0.05` | Raise to keep more weak edges |

## Output

The `DisplayImage()` function renders a side-by-side Matplotlib figure:
- **Left:** Original grayscale image  
- **Right:** Final Canny edge map
