# Virtual Mouse Using Hand Gestures

Welcome to the **Virtual Mouse Using Hand Gestures** repository! 🖐️🖱️
This project demonstrates an AI-powered, contactless mouse system that replaces a physical mouse with real-time hand gesture recognition. Built as a mini project, it highlights practical applications of computer vision and human-computer interaction (HCI).

---
## 🏗️ System Architecture

The system pipeline follows three processing stages, **Capture → Detect → Act**:

1. **Capture Layer**: A webcam continuously streams live video frames to the application in real time.
2. **Detect Layer**: Each frame is converted from BGR to RGB and passed through MediaPipe to identify 21 hand landmarks, from which the active finger gesture is determined.
3. **Act Layer**: The recognized gesture is mapped to a mouse action (move, click, scroll, drag) and executed on the system using PyAutoGUI / pynput.

---
## 📖 Project Overview

This project involves:

1. **Hand Tracking**: Detecting hands and fingertip landmarks in real time using MediaPipe.
2. **Gesture Recognition**: Interpreting finger positions and distances to classify a specific gesture.
3. **Cursor Mapping**: Translating fingertip coordinates from the webcam region into full-screen cursor coordinates.
4. **Mouse Automation**: Triggering native OS mouse events (move, left/right click, scroll, drag & drop) based on the recognized gesture.

🎯 This repository is a useful resource for professionals and students looking to showcase expertise in:
- Computer Vision (OpenCV)
- Human-Computer Interaction (HCI)
- Gesture Recognition
- Python Automation (PyAutoGUI / pynput)
- Real-time Video Processing

---

## 🛠️ Tools Used

- **Python:** Core programming language used to build the application.
- **OpenCV:** Captures webcam video and handles image/frame processing.
- **MediaPipe:** Google's open-source framework used for real-time hand landmark detection.
- **PyAutoGUI:** Automates mouse movement and click actions based on detected gestures.
- **pynput:** Handles precise mouse button click events.
- **Tkinter:** Provides the GUI to start/stop the motion tracker application.
- **VS Code:** IDE used for development.

---

## 🚀 Project Requirements

### Building the Virtual Mouse (Computer Vision & Automation)

#### Objective
Develop a real-time, camera-based virtual mouse system that lets a user control all standard mouse functions using only hand gestures, without any physical or wearable hardware.

#### Specifications
- **Input Source**: Live video feed from a standard laptop/PC webcam — no external sensors or colored markers required.
- **Hand Tracking**: Detect hand landmarks and fingertip positions frame-by-frame using MediaPipe.
- **Gesture Mapping**: Recognize distinct finger-up combinations and distances to distinguish between move, click, and scroll actions.
- **Cursor Translation**: Map a defined rectangular region of the webcam frame to the full computer screen for smooth cursor control.
- **Scope**: Right-hand, single-hand gesture control; real-time performance on standard consumer hardware.
- **Documentation**: Provide clear module-level documentation to support understanding of the detection and automation pipeline.

---

## 🎯 Gesture-to-Function Mapping

| Gesture | Condition | Mouse Function |
|---|---|---|
| Index finger up (or Index + Middle up) | Fingers raised inside tracking region | **Move Cursor** |
| Thumb + Index up | Distance between tips < 30px | **Left Click** |
| Index + Middle up | Distance between tips < 40px | **Right Click** |
| Index + Middle up, moved upward | Fingers move up together | **Scroll Up** |
| Index + Middle up, moved downward | Fingers move down together | **Scroll Down** |
| All five fingers up | No specific gesture matched | **No Action** |

---
## 📊 Test Results

The system was tested 10 times each by 3 users (90 total gesture trials) across varying lighting conditions and distances from the webcam.

| Mouse Function | Success | Failure | Accuracy (%) |
|---|---|---|---|
| Mouse Movement | 100 | 0 | 100% |
| Left Button Click | 98 | 2 | 98% |
| Right Button Click | 99 | 1 | 99% |
| Scroll Function | 93 | 7 | 93% |
| No Action Performed | 100 | 0 | 100% |
| **Overall** | **681** | **19** | **97.28%** |

Scroll function showed the lowest accuracy since it depends on tracking gesture *movement direction* rather than a static hand shape, making it the hardest gesture for the system to interpret consistently.

---

## 🔭 Future Scope

- **Smart Movement**: Adaptive zoom based on user-to-webcam distance to extend the usable tracking radius beyond ~25cm.
- **Two-Hand Support**: Extend gesture recognition to support both hands for a wider range of actions.
- **Better Accuracy in Low Light**: Improve robustness of hand detection in dark or highly variable lighting conditions.
- **Mobile Port**: Adapt the gesture-control concept to Android devices as an alternative to touchscreen input.

---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and share this project with proper attribution.

## 🌟 About Me

**Jeremy David Christopher**

Aspiring Data Analyst

Skills: SQL | Excel | Power BI | Data Analytics

🔗 LinkedIn: https://www.linkedin.com/in/jeremy-david-643870201/

Let's stay in touch!
