# Face Mask Detection using Convolutional Neural Network (CNN)

A deep learning project that classifies a face photo as **with mask** or **without mask**, using a Convolutional Neural Network built with **TensorFlow** and **Keras**.

## Project overview

The model is trained on about 7,500 face images in two classes (with mask, without mask). The images are resized, normalized and split into training and test sets before training a CNN. The notebook ends with a predictive system that takes the path of a photo and prints the result.

## Results

| Metric | Value |
|--------|-------|
| Train accuracy (epoch 5) | 92.3% |
| Validation accuracy (epoch 5) | 90.2% |
| **Test accuracy** | **89.5%** (1,511 test images) |
| Test loss | 0.330 |

Training and validation curves are plotted in the notebook. Validation accuracy peaked at 92.7% in epoch 4 and dropped to 90.2% in epoch 5, so training is not fully stable yet (see "Next steps").

## Dataset

- **Source:** Kaggle dataset [omkargurav/face-mask-dataset](https://www.kaggle.com/datasets/omkargurav/face-mask-dataset)
- **Size:** 7,553 images: 3,725 with mask and 3,828 without mask
- After extraction the notebook expects this structure:

```
data/
├── with_mask/
└── without_mask/
```

## Data preprocessing

1. Load the images from both folders.
2. Resize each image to **128 x 128** and convert it to RGB.
3. Convert the images to NumPy arrays and create labels (1 = with mask, 0 = without mask).
4. Split the data: 80% training (6,042 images) and 20% test (1,511 images).
5. Normalize pixel values by dividing by 255.

## CNN architecture

| Layer | Details |
|-------|---------|
| Conv2D | 32 filters, 3x3, ReLU |
| MaxPooling2D | 2x2 |
| Conv2D | 64 filters, 3x3, ReLU |
| MaxPooling2D | 2x2 |
| Flatten | |
| Dense + Dropout | 128 units, ReLU, dropout 0.5 |
| Dense + Dropout | 64 units, ReLU, dropout 0.5 |
| Output Dense | 2 units, sigmoid |

## Training

- Optimizer: **Adam**
- Loss: `sparse_categorical_crossentropy`
- Metric: accuracy
- 5 epochs, 20% of the training data used for validation

## Technologies

Python, TensorFlow, Keras, NumPy, OpenCV, Matplotlib, Pillow, scikit-learn

## How to run

1. Clone the repository:

```
git clone https://github.com/Arshavir01/DL_Project_FaceMaskDetection.git
```

2. Open the notebook in **Google Colab** (it uses Colab helpers and `/content/` paths).
3. Get the dataset: create a Kaggle API token (Kaggle > Settings > Create New Token), upload `kaggle.json` to your Colab session and run the download cell. Never commit `kaggle.json` to GitHub.
4. If you run locally, install the dependencies with `pip install -r requirements.txt`.
5. Run all cells.

## Project structure

```
DL_Project_FaceMaskDetection/
├── Face Mask Detection using Convolutional Neural Network (CNN).ipynb
├── README.md
└── requirements.txt
```

The dataset is not stored in this repository. It is downloaded from Kaggle.

## Next steps

- Add data augmentation and early stopping to make training more stable.
- Try transfer learning (MobileNetV2, ResNet50, EfficientNet).
- The output layer uses 2 sigmoid units with `sparse_categorical_crossentropy`. Switch to `softmax`, or use 1 sigmoid unit with `binary_crossentropy`.
- Report precision, recall and a confusion matrix for each class.
- Convert the model to TensorFlow Lite and run it in an Android app, or in real time with a webcam.

## Author

**Arshavir Voskanyan**

Senior Android Engineer | Machine Learning Enthusiast

## License

This project is created for educational and learning purposes. The dataset has its own terms on Kaggle.
