# Real-Time Driver Inattention Detection and Alert Generation System

A deep learning–based driver monitoring system that detects driver inattention and unsafe driving behaviours in real time using Computer Vision and Convolutional Neural Networks (CNNs).

The system classifies multiple driver states such as distraction, drowsiness, drinking, yawning, and dangerous driving, and generates safety alerts based on attention scores.

---

## Overview

Road accidents caused by distracted or fatigued driving remain a major global safety issue. Existing systems often focus on only one type of behaviour, such as drowsiness detection.

This project proposes a lightweight and efficient multi-class driver monitoring system capable of detecting several unsafe behaviours simultaneously from live camera input.

The system uses **EfficientNet-B0** for behaviour classification and is designed for potential integration into:

- Advanced Driver Assistance Systems (ADAS)
- Smart vehicles
- Fleet safety monitoring systems

---

# Features

- Real-time driver behaviour detection
- Multi-class classification system
- Lightweight EfficientNet-B0 architecture
- Attention score generation
- Safety status monitoring
- Compatible with live camera or recorded video input
- Designed for real-time deployment environments

---

# Driver Behaviour Classes

The model classifies driver activity into six categories:

1. Safe Driving
2. Distracted Driving
3. Dangerous Driving
4. Drinking
5. Sleepy Driving
6. Yawning

---

# Attention Score Logic

The system calculates an attention score based on predicted behaviour probabilities.

| Attention Score | Status |
|---|---|
| ≥ 70% | Safe |
| 40% – 69% | Mild Risk |
| < 40% | Unsafe |

---

# Tech Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Deep Learning Framework | TensorFlow / PyTorch |
| CNN Architecture | EfficientNet-B0 |
| Development Environment | Google Colab |
| Computer Vision | OpenCV |

---

# Model Architecture

The project uses **EfficientNet-B0**, chosen for its balance between accuracy and computational efficiency.

### Architecture Pipeline

- EfficientNet-B0 pretrained on ImageNet
- GlobalAveragePooling2D layer
- Dense layer with ReLU activation
- Dropout regularization
- Final Softmax classification layer

---

# Dataset

The Driver Inattention Detection Dataset contains grayscale driver images divided into:

| Dataset Split | Images |
|---|---|
| Training Set | 11,942 |
| Validation Set | 1,922 |
| Test Set | 985 |

The dataset includes varied driving behaviours such as:

- Distraction
- Fatigue
- Drinking
- Safe driving
- Dangerous driving
- Yawning

---

# Data Preprocessing

The preprocessing pipeline includes:

- Image resizing
- RGB conversion
- Standardization
- Label preprocessing
- One-hot encoding
- Data augmentation

### Augmentation Techniques

- Rotation
- Shifting
- Zoom
- Horizontal flipping

---

# Training Process

## Stage 1 — Feature Extraction

- Frozen EfficientNet-B0 convolutional layers
- Custom classification head training
- Adam optimizer
- Learning rate: `0.001`
- Data augmentation applied

## Stage 2 — Fine-Tuning

- Unfreezing top EfficientNet layers
- Very low learning rate: `2e-5`
- Continued augmented training
- Improved feature learning and accuracy

---

# Evaluation Metrics

| Metric | Score |
|---|---|
| Accuracy | 90.36% |
| Precision (Macro) | 86.15% |
| Recall (Macro) | 89.58% |
| F1-Score (Macro) | 88.72% |

---

# System Workflow

```text
Video Input
     ↓
Frame Extraction
     ↓
Preprocessing
     ↓
EfficientNet-B0 Model
     ↓
Behaviour Classification
     ↓
Attention Score Calculation
     ↓
Alert Generation
```

---

# Results

The system successfully detects and classifies driver activities in real time and generates alerts based on unsafe behaviour detection.

Example detections include:

- Safe Driving
- Distracted Driving
- Drinking While Driving
- Yawning
- Sleepy Driving

---

# Challenges Faced

- Selecting a lightweight yet accurate model
- Handling class imbalance in dataset
- Variations in lighting and camera angles
- Optimizing latency for real-time inference

---

# Future Improvements

- Real-time audio alert system
- Mobile and embedded deployment
- Eye tracking integration
- Infrared/night vision support
- Advanced temporal behaviour analysis
- Edge AI optimization for onboard systems

---

# Applications

- Advanced Driver Assistance Systems (ADAS)
- Smart vehicles
- Fleet safety monitoring
- Commercial transportation systems
- Accident prevention systems

---

# Installation

```bash
git clone https://github.com/your-username/driver-inattention-detection.git

cd driver-inattention-detection
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the project:

```bash
python app.py
```

---

# Project Structure

```text
driver-inattention-detection/
│
├── dataset/
├── models/
├── notebooks/
├── src/
├── app.py
├── requirements.txt
└── README.md
```

---

# Team Members

- Lakshya Prabhakar
- Gautam Dahiya
- Lakshay Joshi

### Mentor
Dr. Sitender Malik
Asst. Professor MSIT, New Delhi

---

# License

This project is developed for academic and research purposes.

---

# Acknowledgements

- TensorFlow
- PyTorch
- OpenCV
- EfficientNet
- Google Colab
- IEEE Research Papers
