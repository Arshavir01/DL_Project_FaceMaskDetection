# Face Mask Detection using Convolutional Neural Network (CNN)

A Deep Learning project that classifies whether a person is **wearing a face mask** or **not wearing a face mask** using a Convolutional Neural Network (CNN) built with **TensorFlow** and **Keras**.

---

Project Overview

This project demonstrates how to build an image classification model capable of detecting face masks from facial images. The model is trained on two classes:

-  With Mask
-  Without Mask

The dataset is preprocessed, normalized, and split into training and testing sets before being used to train a CNN model.

---

## Objectives

- Learn image preprocessing techniques
- Build a CNN for binary image classification
- Train and evaluate a deep learning model
- Predict whether a person is wearing a face mask

---

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- OpenCV
- Matplotlib
- PIL (Python Imaging Library)
- Scikit-learn

---

## Dataset

The dataset contains two categories:

```
dataset/
│
├── with_mask/
└── without_mask/
```

Each image is:
- Resized to **128 × 128 pixels**
- Converted into a NumPy array
- Normalized by dividing pixel values by **255**

---

## Data Preprocessing

The following preprocessing steps were applied:

- Load images
- Resize images to 128×128
- Convert images to NumPy arrays
- Assign labels
- Normalize pixel values
- Split data into training and testing datasets

---

## CNN Architecture

The model consists of the following layers:

- Conv2D
- MaxPooling2D
- Conv2D
- MaxPooling2D
- Flatten
- Dense (ReLU)
- Dropout
- Output Dense layer (Sigmoid)

This architecture extracts image features through convolution layers and performs binary classification using fully connected layers.

---

## Training

The model is trained using:

- Optimizer: **Adam**
- Loss Function: **Binary Crossentropy**
- Evaluation Metric: **Accuracy**

---

## Model Evaluation

After training, the model is evaluated on the test dataset to measure its classification performance.

Typical evaluation metrics include:

- Test Accuracy
- Test Loss

Training and validation curves can also be visualized to monitor learning performance.

---

## Prediction

The trained model can predict whether a new image belongs to one of the following classes:

- With Mask
- Without Mask

---

## Project Structure

```
Face-Mask-Detection/
│
├── dataset/
│   ├── with_mask/
│   └── without_mask/
│
├── DL_Project_5_Face_Mask_Detection_using_CNN.ipynb
├── README.md
└── requirements.txt
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/Face-Mask-Detection.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the Jupyter Notebook:

```bash
jupyter notebook
```

---

## Future Improvements

- Use Data Augmentation
- Apply Transfer Learning (MobileNetV2, ResNet50, EfficientNet)
- Improve accuracy with a larger dataset
- Deploy as a web application using Flask or Streamlit
- Convert the model to TensorFlow Lite for mobile deployment

---

## Learning Outcomes

This project demonstrates:

- Image preprocessing
- Binary image classification
- Convolutional Neural Networks (CNN)
- Model training and evaluation
- Deep Learning workflow using TensorFlow/Keras

---

## Author

**Arshavir Voskanyan**

Senior Android Engineer | Machine Learning Enthusiast

---

## License

This project is created for educational and learning purposes.
