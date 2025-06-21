# Raspberry Pi Image Recognition Tool

A real-time object detection tool developed using a Raspberry Pi 5, Linux OS, and the YOLO (You Only Look Once) deep learning algorithm. This project was built as part of the **Pi Day Workshop** at the University of Toledo to demonstrate edge-based image recognition using accessible, low-cost hardware.
![pic](https://github.com/SakshiD16/Image-recognition-RaspberryPi/blob/main/Test%20result.jpeg)
---

## Objective

To showcase how a Raspberry Pi 5 can be used to run object detection models locally, enabling real-time computer vision tasks without relying on cloud-based APIs. The project was designed to be lightweight, educational, and highly adaptable for future student workshops or smart device applications.

---

## Tools & Technologies

| Category            | Tools / Frameworks                       |
|---------------------|------------------------------------------|
| Hardware            | Raspberry Pi 5, Pi Camera Module         |
| OS                  | Raspberry Pi OS (Linux)                  |
| Language            | Python 3                                 |
| AI Model            | YOLOv5 (via Ultralytics)                 |
| Libraries Used      | OpenCV, NumPy, Torch, Ultralytics YOLO   |

---

## Features

- Real-time object detection via Pi Camera
- Bounding box overlays and class labeling
- Lightweight enough to run on Raspberry Pi 5
- CLI interface for quick testing and retraining
- Adaptable for custom datasets or classroom use

---

## How It Works

1. The camera feed is accessed using `OpenCV`
2. Frames are passed to the YOLOv5 model for object detection
3. YOLO returns bounding boxes, confidence scores, and class labels
4. Processed frames are displayed live with annotations

---

## Setup Instructions

# Clone YOLOv5 repo
git clone https://github.com/ultralytics/yolov5
cd yolov5

# Install requirements
pip install -r requirements.txt

# Run object detection with Pi Camera
python detect.py --source 0  # 0 = default Pi camera

---

## Quick Start Guide for Beginners

### Step 1: Set Up Your Raspberry Pi
Make sure your Pi is running Raspberry Pi OS and has internet access.

```bash
sudo apt update && sudo apt upgrade
```

### Step 2: Enable the camera
```bash
Sudo raspi-config
```
interface options -> Enable Camera -> Reboot

### Step 3: Install Dependencies
Install Python packages and git
```bash
Sudo apt install git python3-pip
pip3 install torch torchvision opencv-python numpy
```

### Step 4: Clone YOLOv5 Repo
```bash
git clone https://github.com/ultralytics/yolov5
cd yolov5
pip3 install -r requirements.txt
```

### Step 5: Run Detection with Pi Camera
Plug in your Pi camera and run
```bash
python3 detect.py --source 0 --weights yolov5s.pt --conf 0.4
```
- --source 0: Pi camera (default video source)
- --weights yolov5s.pt: Pre-trained model (can be replaced with your own)
- --conf: Confidence threshold (adjustable)

![Camera set-up](https://github.com/SakshiD16/Image-recognition-RaspberryPi/blob/main/Camera%20pic.jpeg)

---

## Tips & Troubleshooting

- Camera not working? Make sure it’s enabled via raspi-config and connected properly
- Lagging? Try lowering resolution in detect.py or using a smaller model like yolov5n.pt
- Want to train on custom objects? Follow Ultralytics training guide

## Workshop Outcomes

- Learn basics of real-time object detection
- Understand YOLO model pipeline on embedded Linux
- Explore OpenCV + PyTorch in a beginner-friendly setting
- Build confidence working with hardware + AI on the edge

## Potential Extensions

- Use GPIO output to trigger events (e.g., LED if a person is detected)
- Build a Flask app for remote viewing
- Train YOLO on lab-specific datasets (plants, tools, safety gear)

## About the Creator

Sakshi Dhumma
Dual Major – Computer Science & Electrical Engineering
University of Toledo
📫 sakshidhumma@email.com
🌐 [Portfolio]() | [LinkedIn](https://www.linkedin.com/in/sakshidhumma/)

## License
This project is open for educational and workshop use. Based on Ultralytics YOLOv5 under GPL-3.0 License.
