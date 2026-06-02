# Industrial Surface Crack Detection using Deep Learning (CNN)

## Project Overview

Industrial Surface Crack Detection using Convolutional Neural Networks (CNN) is a computer vision-based quality inspection system designed to automatically identify cracks on industrial surfaces.

The system uses deep learning techniques to classify images into two categories:

* **Crack**
* **No Crack**

The project aims to reduce manual inspection efforts, improve defect detection accuracy, and support automated quality control processes in manufacturing and industrial environments. The model is trained using a labeled image dataset and can predict whether a surface contains visible cracks in real time.

---

## Key Features

* Automated crack detection using Deep Learning
* Image preprocessing and data augmentation
* CNN architecture with Batch Normalization and Dropout
* Train, Validation, and Test dataset splitting
* Model checkpointing and early stopping
* Learning rate optimization
* Performance evaluation using:

  * Accuracy
  * Loss
  * Confusion Matrix
  * Classification Report
* Single image prediction functionality
* Industrial-grade training pipeline

---

## Technology Stack

| Technology         | Purpose                 |
| ------------------ | ----------------------- |
| Python             | Programming Language    |
| TensorFlow / Keras | Deep Learning Framework |
| NumPy              | Numerical Computation   |
| Matplotlib         | Data Visualization      |
| Scikit-Learn       | Evaluation Metrics      |
| OpenCV / PIL       | Image Processing        |

---

## Project Structure

```text
Industrial_Surface_Crack_Detection/
│
├── CrackDataset/
│   ├── Positive/
│   └── Negative/
│
├── Processed_CrackDataset/
│   ├── train/
│   │   ├── Crack/
│   │   └── NoCrack/
│   │
│   ├── validation/
│   │   ├── Crack/
│   │   └── NoCrack/
│   │
│   └── test/
│       ├── Crack/
│       └── NoCrack/
│
├── Best_Crack_Detection_Model.keras
├── Final_Marvellous_Crack_Detection_Model.keras
├── crack_detection.py
└── README.md
```

---

## Dataset Description

The dataset contains images of industrial surfaces categorized into two classes.

### Crack (Positive)

Images containing visible surface cracks.

### No Crack (Negative)

Images without any visible cracks.

### Dataset Split

| Dataset    | Percentage |
| ---------- | ---------- |
| Training   | 70%        |
| Validation | 15%        |
| Testing    | 15%        |

The dataset is automatically shuffled and divided into these subsets before model training.

---

## Data Preprocessing

The following preprocessing techniques are applied:

* Image resizing to **128 × 128**
* Pixel normalization (**0–255 → 0–1**)
* Rotation augmentation
* Zoom augmentation
* Width shifting
* Height shifting
* Horizontal flipping

These augmentations help improve model generalization and reduce overfitting.

---

## CNN Architecture

### Feature Extraction Layers

| Layer              | Filters |
| ------------------ | ------- |
| Conv2D + BatchNorm | 32      |
| Conv2D + BatchNorm | 64      |
| Conv2D + BatchNorm | 128     |
| Conv2D + BatchNorm | 256     |

Each convolutional layer is followed by:

* ReLU Activation
* Batch Normalization
* Max Pooling

### Classification Layers

```text
Flatten
   ↓
Dense (256) + Dropout(0.5)
   ↓
Dense (128) + Dropout(0.3)
   ↓
Dense (1) + Sigmoid
```

The Sigmoid activation function provides binary classification output.

---

## Training Configuration

| Parameter     | Value               |
| ------------- | ------------------- |
| Image Size    | 128 × 128           |
| Batch Size    | 32                  |
| Epochs        | 15                  |
| Optimizer     | Adam                |
| Loss Function | Binary Crossentropy |
| Metric        | Accuracy            |

### Training Enhancements

#### Early Stopping

Stops training when validation performance stops improving.

#### Model Checkpoint

Automatically saves the best-performing model.

#### Reduce Learning Rate on Plateau

Reduces the learning rate when validation loss stagnates.

These techniques improve model stability and prevent overfitting.

---

## Model Evaluation

The model performance is evaluated using:

### Accuracy

Measures the percentage of correctly classified images.

### Loss

Measures prediction error during training and testing.

### Confusion Matrix

Provides insight into:

* True Positives
* True Negatives
* False Positives
* False Negatives

### Classification Report

Includes:

* Precision
* Recall
* F1-Score
* Support

These metrics provide a comprehensive assessment of model performance.

---

## Single Image Prediction

Example:

```python
predict_single_image("sample_crack.jpg")
```

Output:

```text
Single Image Prediction
Image Path       : sample_crack.jpg
Prediction Value : 0.9821
Final Result     : Crack Detected
```

The system also displays the image with the predicted label.

---

## How to Run the Project

### 1. Clone Repository

```bash
git clone https://github.com/Sarvesh457/Surface-Crack-Detection.git
cd Surface-Crack-Detection
```

### 2. Install Dependencies

```bash
pip install tensorflow numpy matplotlib scikit-learn pillow
```

### 3. Prepare Dataset

```text
CrackDataset/
├── Positive/
└── Negative/
```

### 4. Run Training

```bash
python crack_detection.py
```

### 5. View Results

The program automatically:

* Trains the CNN model
* Displays accuracy graphs
* Displays loss graphs
* Evaluates on test data
* Saves the trained model

---

## Applications

* Manufacturing Quality Control
* Infrastructure Inspection
* Railway Track Monitoring
* Bridge Crack Detection
* Building Safety Assessment
* Concrete Surface Analysis
* Predictive Maintenance Systems

---

## Future Enhancements

* Real-time webcam crack detection
* Mobile application deployment
* Edge AI implementation
* Transfer Learning using ResNet50/EfficientNet
* Object Detection using YOLO
* Segmentation-based crack localization
* Cloud-based monitoring dashboard

---

## Results

The developed CNN model successfully learns surface crack patterns and distinguishes between defective and non-defective surfaces. The combination of data augmentation, deep convolutional layers, batch normalization, and regularization techniques improves robustness and classification performance, making the system suitable for industrial inspection applications.

---

## Author

**Sarvesh Mahajan**
Computer Science Student
Deep Learning | Computer Vision | AI Applications

---

## License

This project is intended for academic, research, and educational purposes. Feel free to modify and extend it for industrial applications and further research.
