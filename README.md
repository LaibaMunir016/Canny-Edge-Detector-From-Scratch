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
