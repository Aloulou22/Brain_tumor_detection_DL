# 🧠 Brain Tumor Detection using Deep Learning

An automatic brain tumor detection system based on Deep Learning using Transfer Learning with VGG16. This project classifies MRI images into 4 categories: Glioma, Meningioma, Pituitary, and No Tumor.

## 🎯 Overview

This project implements an intelligent brain tumor detection system capable of analyzing MRI images and automatically classifying tumors. The web application allows healthcare professionals to upload MRI images and instantly receive a diagnosis with a confidence level.

### Detected Tumor Types

- **Glioma**: Tumor of the brain's glial tissue
- **Meningioma**: Tumor of the meninges
- **Pituitary**: Tumor of the pituitary gland
- **No Tumor**: Absence of tumor

## ✨ Features

- ✅ **Transfer Learning** with pre-trained VGG16 architecture
- ✅ **Data augmentation** to improve robustness
- ✅ **Intuitive web interface** with Flask and Bootstrap
- ✅ **Real-time prediction** with confidence score display
- ✅ **Automatic image preprocessing** (normalization, resizing)
- ✅ **Results visualization** with uploaded image

## 🏗️ Model Architecture

The model uses the **VGG16** architecture pre-trained on ImageNet as a feature extractor, followed by custom fully connected layers:

```
VGG16 (Feature Extractor)
    ↓
Flatten Layer
    ↓
Dense Layer (128 neurons, ReLU)
    ↓
Dropout (0.5)
    ↓
Output Layer (4 neurons, Softmax)
```

### Hyperparameters

- **Image Size**: 128x128 pixels
- **Optimizer**: Adam
- **Loss Function**: Categorical Crossentropy
- **Batch Size**: 32
- **Epochs**: 20-30 (depending on convergence)

## 📊 Dataset

The dataset used contains MRI images organized as follows:

```
Dataset/
├── Training/
│   ├── glioma/
│   ├── meningioma/
│   ├── notumor/
│   └── pituitary/
└── Testing/
    ├── glioma/
    ├── meningioma/
    ├── notumor/
    └── pituitary/
```

**Applied data augmentation**:
- Random rotation
- Horizontal/vertical flip
- Contrast adjustment
- Brightness adjustment

  ### 2. Launching the Web Application

```bash
python main.py
```

The application will be accessible at: `http://localhost:5000`

### 3. Using the Interface

1. Access the web interface
2. Click "Choose File" and select an MRI image
3. Click "Upload and Detect"
4. View the result with tumor type and confidence level

## 📁 Project Structure

```
brain-tumor-detection/
│
├── main.py                           # Main Flask application
├── Brain_Tumor_Detection_DL.ipynb    # Training notebook
├── README.md                         # Documentation
│
├── models/
│   └── model.h5                      # Trained model (not included)
│
├── templates/
│   └── index.html                    # Web interface
│
├── uploads/                          # Uploaded images (auto-created)
│
└── Dataset/                          # Dataset (not included)
    ├── Training/
    └── Testing/
```

## 📈 Results

The model achieves the following performance on the test set:

- **Accuracy**: ~95-98% (varies depending on dataset)
- **Prediction time**: < 1 second per image
- **Detected classes**: 4 (Glioma, Meningioma, Pituitary, No Tumor)

### Prediction Example

```
Input: brain_scan_001.jpg
Output: Tumor: glioma
Confidence: 97.85%
```

## 🛠️ Technologies Used

### Backend & Machine Learning
- **TensorFlow/Keras**: Deep Learning framework
- **VGG16**: Pre-trained CNN architecture
- **NumPy**: Matrix manipulation and numerical computations
- **scikit-learn**: Preprocessing and evaluation

### Frontend & Deployment
- **Flask**: Python web framework
- **Bootstrap 5**: Responsive CSS framework
- **HTML/CSS**: User interface

### Development Tools
- **Jupyter Notebook**: Development and experimentation
- **Python PIL**: Image processing
