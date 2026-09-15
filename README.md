# Real-Time Face Detection with OpenCV

A simple real-time face detector built using Python and OpenCV's Haar Cascade classifier. Detects faces through a live webcam feed and draws a bounding box around each one.

## About

This was built as a fundamentals project to learn how classical (pre-deep-learning) computer vision detection works in OpenCV, before moving on to a more advanced deep-learning-based object detector using YOLOv8 (see my [Object Detector project](https://github.com/altamash7ai/Object-Detector)).

## Features

- Real-time face detection via webcam
- Uses OpenCV's built-in pretrained Haar Cascade model (no external downloads needed)
- Draws a bounding box around each detected face

## Tech Stack

- Python
- OpenCV (Haar Cascade Classifier)

## Installation

```bash
git clone https://github.com/altamash7ai/Face-Detector.git
cd Face-Detector
pip install -r requirements.txt
```

## Usage

```bash
python face_detector.py
```

Press `q` to close the webcam window.

## How It Works

1. Loads OpenCV's pretrained `haarcascade_frontalface_default.xml` model, which ships with the library.
2. Converts each webcam frame to grayscale (Haar Cascades detect based on contrast patterns, not color).
3. Runs `detectMultiScale()` to find face-like regions at multiple scales.
4. Draws a rectangle around every detected face.

## What I Learned

- How Haar Cascade classifiers detect objects using contrast-based patterns
- Why grayscale conversion is required before detection
- Tuning detection parameters (`scaleFactor`, `minNeighbors`, `minSize`) to balance accuracy vs. false positives
- Safe camera-handling patterns (checking `cap.isOpened()`, checking `ret` before processing a frame)

## Possible Future Improvements

- Upgrade to a DNN-based face detector for higher accuracy
- Add face recognition (identify specific known people, not just detect a face)
- Add features like blink detection, drowsiness detection, or automatic face-blurring in video

## Author

Built by Altamash as a hands-on introduction to computer vision with OpenCV.
