Overview
This project trains a Convolutional Neural Network (CNN) to classify images into 3 categories. It uses TensorFlow/Keras to implement the model and leverages TensorBoard's HParams plugin for hyperparameter tuning and visualization.

The primary goal of the project is to:

1.Tune CNN hyperparameters like filter size and filter number.
2.Log and analyze the performance of different hyperparameter combinations using TensorBoard.
3.Identify the best-performing model configuration.


Here’s a detailed README file for your code, summarizing its purpose, functionality, and benefits:

README: CNN Hyperparameter Tuning with TensorBoard
Overview
This project trains a Convolutional Neural Network (CNN) to classify images into 3 categories. It uses TensorFlow/Keras to implement the model and leverages TensorBoard's HParams plugin for hyperparameter tuning and visualization.

The primary goal of the project is to:

Tune CNN hyperparameters like filter size and filter number.
Log and analyze the performance of different hyperparameter combinations using TensorBoard.
Identify the best-performing model configuration.
Project Components
1. Data Preparation
The code loads training, validation, and test datasets from .npz files. It preprocesses the image data by scaling the pixel values between 0 and 1 to ensure optimal model convergence.

2. Hyperparameters
The code tunes the following hyperparameters:

filter_size (3, 5, 7): The size of the convolutional filters.
filter_num (64, 96, 128): The number of filters (channels) in the convolutional layers.
These hyperparameters impact the CNN's ability to extract meaningful features from images.

3. CNN Architecture
The model uses a sequential CNN structure:

Conv2D Layers: Two convolutional layers with ReLU activation.
MaxPooling: Reduces spatial dimensions to avoid overfitting.
Flatten Layer: Converts the 3D feature maps into a 1D vector.
Dense Layer: Outputs logits for 3 categories.
The model is compiled with:

Adam Optimizer: Ensures efficient gradient updates.
SparseCategoricalCrossentropy: Suitable for multi-class classification.
Accuracy: Monitored as the evaluation metric.

4. Hyperparameter Tuning
The project:

Iterates through all combinations of filter_size and filter_num.
Trains the CNN for 15 epochs with a batch size of 64.
Implements EarlyStopping to stop training when validation loss plateaus.
Each trial logs:

Hyperparameters used.
Accuracy achieved.

5. TensorBoard Integration
HParams Plugin: Logs and visualizes hyperparameter tuning trials.
TensorBoard Dashboard: Displays training/validation accuracy, loss curves, and hyperparameter performance metrics.
The logs are saved in:

logs/Model 1/hparam_tuning/: Hyperparameter tuning logs.
logs/Model 1/fit/: Training metrics for each session.
