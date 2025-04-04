# Fashion MNIST Classification with CNN

This project implements a deep learning approach for classifying images from the Fashion MNIST dataset. The end-to-end pipeline includes data loading, augmentation, model building with regularization, training, and evaluation using TensorFlow and Keras.

---

## 1. Environment Setup

- **Library Installation and Imports:**  
  Required libraries such as TensorFlow, Keras, NumPy, and Matplotlib are imported. The Fashion MNIST dataset is loaded directly via Keras, and the Keras session is cleared for a fresh start.

- **Data Loading and Preprocessing:**  
  The dataset provides 60,000 training images and 10,000 test images. Images are normalized to a [0, 1] range, reshaped to add a single channel (28x28x1), and the labels are one-hot encoded for multi-class classification.

---

## 2. Data Augmentation

- **Augmentation Setup:**  
  Two `ImageDataGenerator` instances are created for both training and test data. They apply random rotations, shifts, shears, and zooms to create varied image samples.

- **Data Concatenation:**  
  Augmented batches are generated and concatenated to the original datasets to enrich the training and testing sets.

---

## 3. Model Building

- **CNN Architecture:**  
  A convolutional neural network is constructed using Keras' Sequential API:
  - **Block 1:** Two convolutional layers with 32 filters (ReLU activation) and L2 regularization, followed by batch normalization, max pooling, and dropout.
  - **Block 2:** Two convolutional layers with 64 filters, similar normalization and pooling, and dropout.
  - **Fully Connected Layers:** The output is flattened and passed through a dense layer with 256 units, followed by dropout and a final softmax layer for classification.

- **Model Compilation:**  
  The network is compiled using the Adam optimizer and categorical cross-entropy loss.

---

## 4. Training and Evaluation

- **Callbacks:**  
  EarlyStopping and ReduceLROnPlateau callbacks are utilized to monitor validation loss, reducing the learning rate or halting training to prevent overfitting.

- **Model Training:**  
  The model is trained for 10 epochs with a batch size of 64 using the augmented dataset. Validation performance is monitored throughout training.

- **Performance Visualization:**  
  Training and validation accuracy as well as loss curves are plotted to evaluate the model’s learning progress.

---

## Conclusion

This project demonstrates an effective pipeline for classifying Fashion MNIST images using a CNN. The approach incorporates data augmentation, L2 regularization, and performance monitoring to achieve robust results. The modular design of the pipeline makes it adaptable for other image classification challenges.

