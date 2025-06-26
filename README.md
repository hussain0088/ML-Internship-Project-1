# 🛣️ Lane Line Detection for Autonomous Driving

This project implements a lane line detection system using a CNN-based semantic segmentation model trained on the [TuSimple Dataset](https://github.com/TuSimple/tusimple-benchmark). The system performs binary segmentation on grayscale road images to identify lane lines for potential use in autonomous vehicle systems.

---

## 📌 Project Objectives

- Detect lane lines using deep learning (semantic segmentation)
- Train a custom lightweight CNN (ENet-inspired) for real-time lane detection
- Evaluate model accuracy and performance
- Suggest improvements for real-world deployment

---

## 🗃️ Dataset: TuSimple (Simplified Format)

This project uses a processed version of the TuSimple dataset, consisting of:

- **Grayscale road images**: 96x96 resolution
- **Binary masks**: 1 = lane pixel, 0 = background

### Folder Structure
dataset/
├── train/
│ ├── images/ # Training images (grayscale)
│ └── masks/ # Corresponding binary masks
├── test/
│ ├── images/ # Testing images
│ └── masks/ # Ground truth masks

---

## 🧠 Model Architecture

The model is based on a lightweight **encoder-decoder CNN** architecture inspired by ENet.

### Features:

- **Input size**: 1×96×96 (grayscale image)
- **Convolutional layers**: Extract features at multiple resolutions
- **Upsampling layers**: Restore segmentation mask to input size
- **Final layer**: Sigmoid activation for binary segmentation

### Summary

- **Loss function**: Binary Cross-Entropy Loss
- **Optimizer**: Adam (LR = 0.001)
- **Epochs**: 10+
- **Device**: CPU and GPU supported

---
Results
Metric	Value
Final Accuracy	73.78%
Final Loss	0.54

