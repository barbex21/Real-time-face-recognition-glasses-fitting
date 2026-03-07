# Real-time Face Recognition for Personalized Eyeglass Frames

This project implements **real-time** face detection and facial landmark measurement in Python to support the design of personalized 3D-printed eyeglass frames. The system captures video from a webcam, detects the face, extracts key landmarks (eyes, ears, facial contour), and computes distances in millimeters using a scale factor. These measurements are then used to adapt eyeglass frame geometry in OnShape and 3D printing workflows. [file:16]

## Features

- Real-time video capture from webcam [file:16]  
- Face detection using dlib HOG frontal face detector [file:16]  
- Facial landmarks (68 points) via `shape_predictor_68_face_landmarks.dat` [file:16]  
- Integration with MediaPipe Face Mesh for dense facial contours [file:16]  
- Distance calculation between eyes and ears in pixels and conversion to millimeters with a scale factor [file:16]  
- Exportable measurements for CAD-based eyeglass frame design (OnShape) and 3D printing [file:16]

## Tech stack

- Python
- OpenCV
- dlib
- MediaPipe
- NumPy
- OnShape (for CAD modeling, documented in the thesis) [file:16]

## How it works (high level)

1. Open webcam stream and read frames in a loop.  
2. Detect the face using dlib's HOG face detector. [file:16]  
3. Predict 68 facial landmarks and/or use MediaPipe Face Mesh for dense landmarks. [file:16]  
4. Select key points (e.g., left/right eye, left/right ear) and compute Euclidean distances. [file:16]  
5. Convert pixel distances to millimeters using a calibrated scale factor (e.g. 0.00241 mm/pixel). [file:16]  
6. Use these measurements in CAD (OnShape) to adapt the eyeglass frame model to the user. [file:16]

## Installation

```bash
git clone https://github.com/USERNAME/real-time-face-recognition-glasses-fitting.git
cd real-time-face-recognition-glasses-fitting
pip install -r requirements.txt

