# 🩸 White Blood Cell Classification Using CNN

A Deep Learning and Computer Vision project developed to automatically classify microscopic white blood cell images into five different categories using a Convolutional Neural Network (CNN). The model is built using TensorFlow and Keras and achieves approximately **95% classification accuracy** on unseen test data.

This project demonstrates the practical application of Deep Learning in medical image analysis and healthcare diagnostics.

---

## 🎯 Project Objective

Manual identification and classification of white blood cells can be time-consuming and prone to human error. The objective of this project is to develop an automated classification system using Convolutional Neural Networks (CNNs) that can accurately identify different types of white blood cells from microscopic images.

This project also helped strengthen my understanding of:

* Deep Learning Fundamentals
* Convolutional Neural Networks (CNNs)
* Medical Image Processing
* TensorFlow and Keras
* Data Augmentation Techniques
* Model Evaluation and Performance Analysis

---

## 🛠️ Technologies Used

### Core Technologies

* Python
* TensorFlow
* Keras
* Google Colab

### Data Processing & Visualization

* NumPy
* Pandas
* Pillow (PIL)
* Matplotlib
* Seaborn
* Scikit-learn
* KaggleHub

---

## 🚀 Features

### Advanced Image Processing

* Automatic image resizing (128×128)
* Pixel normalization
* Data augmentation using rotations and flips
* Balanced class handling
* Efficient image preprocessing pipeline

### Robust CNN Architecture

* 4-stage convolutional neural network
* Batch Normalization
* MaxPooling layers
* Dropout Regularization
* Fully Connected Dense Layers

### Performance Optimization

* Early Stopping
* Learning Rate Scheduling
* Model Checkpointing
* GPU Acceleration Support

### Comprehensive Evaluation

* Confusion Matrix Analysis
* ROC Curve Generation
* Per-Class Accuracy Metrics
* Real-Time Prediction Visualization

---

## 🏗️ Model Architecture

```text
Input Layer (128x128x3)

│
├── Conv Block 1
│   ├── Conv2D (64 Filters)
│   ├── Batch Normalization
│   ├── MaxPooling2D
│   └── Dropout (0.25)
│
├── Conv Block 2
│   ├── Conv2D (128 Filters)
│   ├── Batch Normalization
│   ├── MaxPooling2D
│   └── Dropout (0.25)
│
├── Conv Block 3
│   ├── Conv2D (256 Filters)
│   ├── Batch Normalization
│   ├── MaxPooling2D
│   └── Dropout (0.25)
│
├── Conv Block 4
│   ├── Conv2D (512 Filters)
│   ├── Batch Normalization
│   ├── MaxPooling2D
│   └── Dropout (0.25)
│
├── Dense Layer (1024)
│   └── Dropout (0.5)
│
├── Dense Layer (512)
│   └── Dropout (0.5)
│
└── Output Layer (5 Classes)
    └── Softmax Activation
```

---

## 📊 Dataset Information

**Dataset Source:** White Blood Cells Dataset

### White Blood Cell Categories

| Cell Type  | Training Images |
| ---------- | --------------- |
| Neutrophil | 6,231           |
| Lymphocyte | 2,427           |
| Monocyte   | 561             |
| Eosinophil | 744             |
| Basophil   | 212             |

### Dataset Statistics

| Description            | Count  |
| ---------------------- | ------ |
| Total Images           | 14,514 |
| Training Images        | 10,175 |
| Training Split (80%)   | 8,140  |
| Validation Split (20%) | 2,035  |
| Test Images            | 4,339  |

---

## 📈 Model Performance

| Metric              | Score   |
| ------------------- | ------- |
| Training Accuracy   | ~94%    |
| Validation Accuracy | ~95%    |
| Test Accuracy       | ~95%    |
| Inference Time      | <100 ms |
| Model Size          | ~50 MB  |

The model demonstrates strong generalization performance across all five white blood cell categories.

---

## 🧠 Skills Demonstrated

* Deep Learning
* Convolutional Neural Networks (CNN)
* Computer Vision
* Medical Image Analysis
* TensorFlow
* Keras
* Python Programming
* Data Visualization
* Model Optimization
* Performance Evaluation

---

## 🚀 Quick Start

### 1. Install Dependencies

```bash
pip install kagglehub tensorflow numpy pandas matplotlib seaborn pillow scikit-learn tqdm
```

### 2. Download Dataset

```python
import kagglehub

path = kagglehub.dataset_download(
    "masoudnickparvar/white-blood-cells-dataset"
)

print("Path to dataset files:", path)
```

### 3. Run the Notebook

Execute all cells in the notebook sequentially.

The notebook will:

* Load and preprocess the dataset
* Display class distributions and sample images
* Build and train the CNN model
* Evaluate performance metrics
* Save the trained model

```text
wbc_classification_model.keras
```

---

## 💡 Making Predictions

```python
from tensorflow.keras.models import load_model
from PIL import Image
import numpy as np

model = load_model("wbc_classification_model.keras")

img = Image.open("image.jpg").convert("RGB")
img = img.resize((128, 128))

img_array = np.array(img) / 255.0
img_array = np.expand_dims(img_array, axis=0)

prediction = model.predict(img_array)

classes = [
    "Neutrophil",
    "Lymphocyte",
    "Monocyte",
    "Eosinophil",
    "Basophil"
]

predicted_class = classes[np.argmax(prediction)]
confidence = np.max(prediction)

print(
    f"Predicted: {predicted_class} "
    f"with {confidence:.2%} confidence"
)
```

---

## ⭐ Project Highlights

✔ Developed a CNN-based medical image classification system.

✔ Achieved approximately 95% test accuracy.

✔ Implemented data augmentation and regularization techniques.

✔ Applied Batch Normalization and Dropout to improve generalization.

✔ Evaluated model performance using confusion matrices and ROC analysis.

✔ Utilized GPU acceleration for faster model training.

---

## 📚 Key Learnings

During this project, I learned:

* Designing CNN architectures from scratch
* Working with large image datasets
* Preventing overfitting using regularization techniques
* Evaluating classification models effectively
* Saving and deploying trained deep learning models
* Applying AI techniques to healthcare-related problems

---

## 🚀 Future Enhancements

* Develop a web application using Flask or FastAPI
* Deploy the model on cloud platforms
* Integrate Explainable AI (Grad-CAM)
* Support additional blood cell categories
* Build a real-time prediction dashboard

---

## 👨‍💻 Developed By

**Avadhesh Kumar Bind**

B.Tech – Computer Science & Engineering (AI Specialization)

Galgotias University

📧 Email: [avadheshkumarbind3@gmail.com](mailto:avadheshkumarbind3@gmail.com)

💻 GitHub: https://github.com/Avadh912573

---

## 🚀 About Me

I am a B.Tech CSE (AI) student at Galgotias University with a strong interest in Artificial Intelligence, Machine Learning, Deep Learning, Computer Vision, and Software Development.

I use GitHub to showcase academic and personal projects while continuously improving my technical and problem-solving skills.

If you found this project useful, consider giving it a ⭐ on GitHub.
