# Driver-Drowsiness-Detection

This project is a real-time driver drowsiness detection system using Python, OpenCV, dlib, and machine learning concepts. It detects signs of drowsiness based on Eye Aspect Ratio (EAR) and alerts the driver through an alarm sound when prolonged eye closure is detected.

## Features

- Real-time face and eye detection using Haarcascade and dlib
- Eye Aspect Ratio (EAR) based drowsiness detection
- Audio alert using `alert.wav` when drowsiness is detected
- Works with webcam input

## Folder Structure

```
Driver-Drowsiness-Detection/
├── haarcascades/
│   ├── haarcascade_eye.xml
│   └── haarcascade_frontalface_default.xml
├── audio/
│   └── alert.wav
├── images/
│   └── test.jpeg
├── drowsiness_detect.py
├── face_and_eye_detector_single_image.py
├── face_and_eye_detector_webcam_video.py
├── shape_predictor_68_face_landmarks.dat
└── README.md
```

## Requirements

- Python 3.x
- OpenCV
- dlib
- imutils
- scipy
- pygame
- numpy

Install all dependencies using:

```bash
pip install opencv-python dlib imutils scipy pygame numpy
```

## How It Works

- Facial landmarks are extracted using `shape_predictor_68_face_landmarks.dat`.
- Eye coordinates are used to calculate the **Eye Aspect Ratio (EAR)**:

  \[
  EAR = \frac{\|p_2 - p_6\| + \|p_3 - p_5\|}{2 \times \|p_1 - p_4\|}
  \]

- When EAR drops below a threshold (e.g., `0.3`) for consecutive frames (e.g., `50`), the system detects drowsiness.
- An alarm sound (`alert.wav`) is played to wake the driver.

## Running the Project

### 1. Drowsiness Detection (Main Script)

```bash
python drowsiness_detect.py
```

> Make sure your webcam is connected and the required model files are in place.

### 2. Test Face & Eye Detection on Static Image

```bash
python face_and_eye_detector_single_image.py
```

### 3. Face & Eye Detection in Webcam Feed

```bash
python face_and_eye_detector_webcam_video.py
```

## Assets Used

- Haarcascade files from OpenCV:
  - `haarcascade_frontalface_default.xml`
  - `haarcascade_eye.xml`
- Pretrained model: `shape_predictor_68_face_landmarks.dat` (from [dlib's official site](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2))
- Alert sound: `audio/alert.wav`

## Disclaimer

This project is for **educational purposes only**. It is **not intended for real-life vehicle integration** without proper validation and certification.

## Author

**Vedant Kumbhar**  
GitHub: [Vedant-k07](https://github.com/Vedant-k07)
