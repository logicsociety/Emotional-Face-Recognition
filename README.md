
# 😃 **Emotix – AI-Powered Facial Emotion Recognition System**

## 📑 **Index**

1. [Overview](#overview)
2. [Team Members](#team-members)
3. [Mentor](#mentor)
4. [Problem Statement](#problem-statement)
5. [Objective](#objective)
6. [Technology Stack](#technology-stack)
7. [Model Architecture](#model-architecture)
8. [Dataset & Preprocessing](#dataset--preprocessing)
9. [Workflow](#workflow)
10. [Training & Evaluation](#training--evaluation)
11. [Results](#results)
12. [Future Scope](#future-scope)
13. [How to Run](#how-to-run)
14. [Conclusion](#conclusion)

---

## 🔍 **Overview**

AI today is extremely advanced, but still lacks **emotional intelligence**, which is essential for creating more humane, empathetic, and interactive systems.
**Emotix** bridges this gap using **Facial Emotion Recognition (FER)** powered by **Deep Learning, CNNs, and YOLOv11** for real-time detection.

Emotix identifies and classifies facial expressions into **seven core human emotions**:

* Happy
* Sad
* Neutral
* Surprise
* Angry
* Fear
* Disgust

This system can be used for sentiment analysis, mental-health monitoring, user experience enhancement, surveillance, and human-computer interaction.

---

## 👥 **Team Members**

**Team Name: Mood-Vision**

* **Tanishq Madhwani (Team Leader)**
* Lavanya Jain
* Parth Vats
* Yug Sharma

---

## 🎓 **Mentor**

**Karan Dalal**

---

## ⚠️ **Problem Statement**

Artificial Intelligence still struggles to understand emotional context due to:

* Limited ability to understand subtle or mixed expressions
* Lack of empathy or genuine emotional reasoning
* Difficulty interpreting sarcasm, context, or cultural differences

This leads to interactions that sometimes feel robotic or emotionless.
Emotix solves this by enabling real-time **emotion classification** directly from facial data.

---

## 🎯 **Objective**

To design a **real-time, highly accurate Facial Emotion Recognition system** capable of:

* Detecting human faces
* Extracting facial features
* Classifying them into emotional categories
* Displaying real-time predictions on test images or video streams

---

## 🧰 **Technology Stack**

### **🔹 Python Libraries**

* **TensorFlow** – Deep learning framework for CNN-based emotion classification
* **OpenCV (cv2)** – Face detection & image preprocessing
* **NumPy & Pandas** – Data manipulation & numerical computation
* **Scikit-learn** – Label encoding & dataset preprocessing
* **KaggleHub / Roboflow** – Dataset downloading and preparation

### **🔹 Deep Learning & Vision**

* **YOLOv11** – Real-time face detection
* **Convolutional Neural Networks (CNN)** – Emotion classification
* **Google Colab / VS Code** – Training & development environment

---

## 🧠 **Model Architecture**

The system uses a two-stage approach:

1️⃣ **Face Detection (YOLOv11)**

* Detects face region
* Crops and prepares ROI

2️⃣ **Emotion Classification (CNN Model)**

* Input image resized to **48×48 grayscale**
* Normalized (0–1 scale)
* Passed through multiple CNN layers
* Outputs class probabilities for 7 emotions

---

## 🗂️ **Dataset & Preprocessing**

### **Preprocessing Steps**

* Convert RGB → Grayscale
* Resize all images to **48×48**
* Normalize pixel values (divide by 255)
* Label encode emotion categories
* One-hot encode labels
* Train-test split

### **Dataset Sources**

* Kaggle facial expression dataset
* Roboflow annotated dataset

---

## 🔄 **Workflow**

1. **Input Image** – User uploads image / captured via webcam
2. **Face Detection** – YOLOv11 identifies bounding box
3. **Cropping & Processing** – ROI extracted
4. **Emotion Classification** – CNN predicts emotion probabilities
5. **Display Output** – Emotion label overlaid on image

---

## 🏋️ **Training & Evaluation**

* Trained on thousands of labeled facial emotion images
* Used YOLOv11 for detection + CNN for classification
* Trained for multiple epochs to optimize accuracy
* Evaluated using:

  * Accuracy
  * Loss
  * Confusion matrix
  * Prediction speed

---

## 📊 **Results**

The system accurately classifies facial expressions and produces:

* Bounding boxes for detected faces
* Emotion labels like “Surprise”, “Happy”, “Angry”
* Confidence scores
* Real-time inference within **milliseconds**

Sample output includes images where multiple detected faces are labeled with predicted emotions.

---

## 🚀 **Future Scope**

* **Transfer Learning** with advanced pretrained models (ResNet, VGG)
* **Fine-tuning** top layers for accuracy boost
* Real-time webcam integration
* Integration with chatbots & virtual assistants
* Emotion-based recommendation systems
* Multimodal analysis (voice + face)
* Deployment as a web or mobile app

---

## ▶️ **How to Run**

### **1. Install dependencies**

```bash
pip install tensorflow opencv-python numpy pandas scikit-learn ultralytics kagglehub
```

### **2. Download dataset**

```python
import kagglehub
path = kagglehub.dataset_download("jonathanoheix/face-expression-recognition-dataset")
```

### **3. Train the YOLOv11 Model**

```python
from ultralytics import YOLO
model = YOLO("yolov8n.pt")
model.train(data="config.yaml", epochs=50, imgsz=640, batch=16)
```

### **4. Run Inference**

```python
results = model(source="test.jpg")
```

### **5. Display Output**

Bounding boxes + emotion labels appear on the image.

---

## 🏁 **Conclusion**

Emotix is an advanced **Facial Emotion Recognition AI** designed to push the boundaries of user-centric interaction.
By combining **YOLOv11**, **CNNs**, and modern deep learning techniques, the project delivers a fast, accurate, and real-time solution for classifying human emotions—bringing machines one step closer to emotional understanding.


