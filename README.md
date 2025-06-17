# Eye-Gaze-Detection:
# Facial Landmark Detection and Head Pose Estimation

A Python notebook that demonstrates facial landmark detection using MediaPipe and head pose estimation using OpenCV and NumPy.

## Overview

This project processes images to detect facial landmarks and estimate head pose (including gaze direction) using OpenCV and MediaPipe. It reads a calibration file for camera parameters and uses these to project 3D facial landmarks onto the image for visualization and analysis.

## Features

- **Facial Landmark Detection:** Uses MediaPipe to detect facial landmarks in an image.
- **Head Pose Estimation:** Calculates the head pose by fitting a 3D facial model to the detected landmarks.
- **Gaze Estimation:** Optionally visualizes gaze vectors for both eyes.
- **Calibration:** Loads camera intrinsic parameters from a calibration file (`MultiMatrix.npz`).
- **Visualization:** Plots detected landmarks and pose vectors on the input image.

## Requirements

- **Python 3.10** (or compatible)
- **OpenCV** (`opencv-python`)
- **MediaPipe** (`mediapipe`)
- **NumPy** (`numpy`)
- **Matplotlib** (`matplotlib`)

You can install the required packages using pip:
`pip install opencv-python mediapipe numpy matplotlib`


## Calibration Data

The code expects a calibration file named `MultiMatrix.npz` in the working directory. This file should contain the following arrays:
- **camMatrix**: Camera intrinsic matrix.
- **distCof**: Distortion coefficients.

Example:
`camMatrix = np.array([[895.07101587, 0., 247.87265042],
[0., 892.0337803, 140.51830804],
[0., 0., 1.]])
distCof = ... # Distortion coefficients`


## Calibration Data

The code expects a calibration file named `MultiMatrix.npz` in the working directory. This file should contain the following arrays:
- **camMatrix**: Camera intrinsic matrix.
- **distCof**: Distortion coefficients.


## Usage

1. **Prepare your environment and install dependencies.**
2. **Place your calibration file (`MultiMatrix.npz`) in the working directory.**
3. **Prepare an input image (e.g., `pexels-simon-robben-55958-614810.jpg`).**
4. **Run the notebook or script.**

The code will:
- Load the calibration data.
- Detect facial landmarks using MediaPipe.
- Estimate head pose and gaze.
- Visualize the results using Matplotlib.


## Configuration

- **draw_gaze:** Set to `True` to visualize gaze vectors.
- **draw_full_axis:** Set to `True` to draw full head pose axes.
- **draw_headpose:** Set to `True` to draw head pose.
- **x_score_multiplier, y_score_multiplier:** Adjust gaze score multipliers.
- **threshold:** Set threshold for averaging gaze scores between frames.

## Output

- **Visualization:** Detected facial landmarks and estimated pose/gaze vectors are plotted on the input image.
- **Logging:** Debug and warning messages are printed to the console.

## Troubleshooting

- **MediaPipe initialization issues:** Ensure you have the correct version of MediaPipe installed. If you see warnings about importing Axes3D, check your Matplotlib installation.
- **Calibration file not found:** Place `MultiMatrix.npz` in the working directory.
- **Image not found:** Ensure the image file exists in the working directory.
