# product_classification
This project is an implementation of image classification of products categories using neural network

My approach:

Data Collection: Before the model building process, the first step was data collection. This was done using various methods such as web scraping and gathering public datasets. The aim was to collect a diverse set of images for each class to ensure that the model would be able to generalize well to unseen data. The collected data was then organized into a directory structure where each subdirectory represented a class and contained images belonging to that class.

Data Preparation: The data is organized in a directory structure where each subdirectory represents a class and contains images belonging to that class. This structure is leveraged by Keras’ ImageDataGenerator for automatic labeling of the images based on their parent directory name.

Data Augmentation: To increase the diversity of the training data and reduce overfitting, the ImageDataGenerator is used to perform on-the-fly data augmentation. This includes random transformations such as rotation, width and height shifts, shear transformation, zooming, horizontal flipping, and brightness adjustment.

Model Architecture: A Convolutional Neural Network (CNN) is used for the image classification task. The model is built using Keras’ Sequential API and consists of three sets of Conv2D and MaxPooling2D layers, followed by a Flatten layer and two Dense layers. Dropout is applied after each MaxPooling2D layer and the first Dense layer to prevent overfitting.

Model Compilation: The model is compiled with the Adam optimizer (with a learning rate of 0.0001), the categorical cross-entropy loss function (since it’s a multi-class classification problem), and accuracy as the evaluation metric.

Model Training: The model is trained using the fit method of the Keras model. The training data is fed to the model using the flow_from_directory method of the ImageDataGenerator. Callbacks are used during training to save the best model and reduce the learning rate when the validation accuracy plateaus.

Functionalities:

Image Classification: The primary functionality of this script is to train a model to classify images into one of four classes.
Data Augmentation: The script uses Keras’ ImageDataGenerator to perform on-the-fly data augmentation, which helps increase the diversity of the training data and reduce overfitting.
Model Evaluation: The script includes functionality to evaluate the model’s performance on a validation set during training. This helps monitor the model’s learning progress and adjust the learning rate as needed.
Model Prediction: After training, the model can be used to predict the class of new images. The script includes a function to load and preprocess an image, and then use the trained model to predict its class.
Accuracy Calculation: The script includes functionality to calculate the accuracy of the model on a test set. This is done by comparing the model’s predictions to the true labels of the test images.
