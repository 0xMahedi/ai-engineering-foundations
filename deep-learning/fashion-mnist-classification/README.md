# Fashion-MNIST Classification: Dense Neural Network vs. CNN

A deep learning project comparing a **Dense Neural Network (DNN)** and a **Convolutional Neural Network (CNN)** for image classification using the Fashion-MNIST dataset.

## Overview

The objective of this project is to understand how different neural network architectures perform on image classification tasks. Both models are trained and evaluated on Fashion-MNIST, a dataset containing grayscale images of clothing items belonging to ten categories.

The project explores model architecture, training behavior, validation performance, generalization, and classification errors.

## Dataset

Fashion-MNIST contains 70,000 grayscale images of clothing items.

| Dataset property | Details |
|---|---|
| Total images | 70,000 |
| Training images | 54,000 |
| Validation images | 6,000 |
| Test images | 10,000 |
| Image dimensions | 28 × 28 pixels |
| Color channels | 1 (grayscale) |
| Number of classes | 10 |
| Pixel range after normalization | 0–1 |

The original 60,000 training images were split into 54,000 training images and 6,000 validation images. The separate 10,000-image test set was reserved for final evaluation.

### Classes

1. T-shirt/top
2. Trouser
3. Pullover
4. Dress
5. Coat
6. Sandal
7. Shirt
8. Sneaker
9. Bag
10. Ankle boot

The dataset is loaded directly through TensorFlow/Keras, so no manual dataset download is required.

## Technologies Used

- Python
- TensorFlow and Keras
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab
- Git and GitHub

## Model Architectures

### 1. Dense Neural Network

The baseline model uses fully connected layers to classify the images.

**Architecture:**

`Input → Flatten → Dense(64) → Dense(128) → Dense(64) → Softmax(10)`

- ReLU activation in hidden layers
- Softmax activation in the output layer
- Adam optimizer
- Sparse categorical cross-entropy loss
- 10 training epochs
- Batch size of 128

### 2. Convolutional Neural Network

The CNN uses convolutional layers to learn spatial features from images.

**Architecture:**

`Input → Conv2D(32) → BatchNormalization → MaxPooling → Conv2D(64) → BatchNormalization → MaxPooling → Flatten → Dense layers → Softmax(10)`

The implementation also uses dropout for regularization.

**Key components:**

- Convolutional layers extract visual features.
- Max pooling reduces spatial dimensions.
- Batch normalization helps stabilize training.
- Dropout helps reduce overfitting.
- Dense layers perform final classification.
- Softmax produces probabilities for the ten classes.

The CNN was trained for 10 epochs with a batch size of 128 using Adam and sparse categorical cross-entropy.

## Results

### Validation Performance

| Metric | Dense NN | CNN |
|---|---:|---:|
| Training accuracy | 90.26% | 93.42% |
| Validation accuracy | 89.12% | 92.78% |
| Validation loss | 0.3001 | 0.2097 |
| Training epochs | 10 | 10 |
| Batch size | 128 | 128 |

*Note: Accuracy and loss values are taken from the recorded training results. Minor differences may occur if the models are retrained.*

### Test Performance

The test metrics should be filled in after evaluating both trained models on the held-out test set.

| Metric | Dense NN | CNN |
|---|---:|---:|
| Test accuracy | Pending | Pending |
| Test loss | Pending | Pending |
| Trainable parameters | Pending | Pending |

## Visualizations and Evaluation

The project includes:

- Training and validation accuracy curves
- Training and validation loss curves
- CNN confusion matrix
- Five examples of misclassified test images
- Classification report with precision, recall, and F1-score

These visualizations help evaluate learning behavior, generalization, and the classes that are most difficult to distinguish.

## Key Findings

The CNN achieved higher validation accuracy than the Dense Neural Network in the recorded experiment.

The main reason is that convolutional layers preserve and exploit the spatial structure of images. They learn local patterns such as edges, textures, and shapes, while weight sharing allows filters to be reused across image locations.

A Dense Neural Network flattens the image before learning, making spatial relationships less explicit. As a result, CNNs are generally better suited to image classification tasks.

The CNN's training and validation curves showed improving performance across the ten epochs, with no strong evidence of severe overfitting during this run.

## How to Run

### Option 1: Google Colab

1. Open the Jupyter notebook included in this repository.
2. Open it in Google Colab.
3. Run the cells in order.
4. Review the training curves, test metrics, confusion matrix, and misclassified images.

### Option 2: Local Environment

Clone the repository:

```bash
git clone https://github.com/0xMahedi/ai-engineering-foundations.git
cd ai-engineering-foundations
```

Install the required libraries:

```bash
pip install tensorflow numpy matplotlib scikit-learn
```

Open the notebook in Jupyter or VS Code and execute the cells sequentially.

## Future Improvements

- Experiment with different CNN architectures and filter sizes.
- Apply data augmentation to improve generalization.
- Tune the learning rate and batch size.
- Use early stopping to reduce unnecessary training.
- Compare model size, inference time, and parameter counts.
- Analyze class-specific errors and improve classification performance.

## Learning Outcomes

Through this project, I explored:

- Building and training neural networks using TensorFlow/Keras
- Comparing fully connected and convolutional architectures
- Splitting datasets into training, validation, and test sets
- Monitoring training and validation metrics
- Understanding overfitting and generalization
- Evaluating classification models using confusion matrices and classification reports

## Author

**0xMahedi**

GitHub: [@0xMahedi](https://github.com/0xMahedi)

---

*Part of my AI Engineering Foundations learning journey.*
