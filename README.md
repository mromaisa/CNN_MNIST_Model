# MNIST Digit Classification using a Convolutional Neural Network (CNN)

This repository contains a Jupyter Notebook (`cnn_mnist_dataset.ipynb`) that demonstrates the process of building, training, and evaluating a Convolutional Neural Network (CNN) for classifying handwritten digits from the MNIST dataset.
The links to the dataset: 
https://www.kaggle.com/datasets/oddrationale/mnist-in-csv

## Project Overview

The goal of this project is to develop a CNN model capable of accurately recognizing handwritten digits (0-9). The notebook covers data loading, preprocessing, model architecture definition, training, and a comprehensive evaluation of the model's performance.

## Key Components & Steps

1.  **Data Loading and Initial Exploration**: The `mnist_train.csv` and `mnist_test.csv` datasets are loaded using pandas. Initial data inspection includes shape, column information, and a check for null values.
2.  **Data Preprocessing**: 
    *   Separation of labels from pixel data.
    *   Normalization of pixel values to the range \( [0, 1] \) by dividing by 255.0.
    *   Reshaping the image data to `(num_samples, 28, 28, 1)` to fit the CNN input requirements.
    *   Handling of `NaN` values by replacing them with zeros.
    *   One-hot encoding of target labels for categorical cross-entropy loss.
3.  **Model Architecture**: A sequential Keras CNN model is defined, featuring:
    *   Two `Conv2D` layers with `MaxPooling2D` for feature extraction.
    *   A `Flatten` layer.
    *   A `Dense` hidden layer with ReLU activation and a `Dropout` layer to prevent overfitting.
    *   A `Dense` output layer with softmax activation for 10-class classification.
4.  **Model Training**: The model is compiled with the Adam optimizer and `categorical_crossentropy` loss. It is trained for 10 epochs, with 20% of the training data used for validation.
5.  **Model Evaluation**: The trained model's performance is thoroughly evaluated using:
    *   Training and Validation Accuracy/Loss curves.
    *   Test Loss and Test Accuracy.
    *   A detailed Classification Report (Precision, Recall, F1-score for each class).
    *   A visual Confusion Matrix to understand class-wise prediction accuracy and misclassifications.

## Performance Highlights

The model achieved a **Test Accuracy of approximately 94.23%** on the unseen test dataset. Training and validation curves indicated good learning without significant overfitting. The confusion matrix showed strong performance across most digits, with minor misclassifications for visually similar digits.

## How to Use

1.  **Clone the Repository**:
    ```bash
    git clone <repository-url>
    cd <repository-name>
    ```
2.  **Download Datasets**: Ensure `mnist_train.csv` and `mnist_test.csv` are in the same directory as the notebook. (You can typically find these on Kaggle or other machine learning dataset repositories).
3.  **Open in Google Colab**: Upload `cnn_mnist_dataset.ipynb` to Google Colab or open it directly if you're viewing it on GitHub with the Colab integration.
4.  **Run Cells**: Execute the cells sequentially from top to bottom. The notebook is structured to guide you through each step of the process.