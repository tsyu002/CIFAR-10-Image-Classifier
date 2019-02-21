CIFAR-10 Image Classifier Using MLP Neural Network
In Collaboration with Anudeep Yeijala

Dataset Description:

The CIFAR-10 dataset is composed of 60,000 images and their corresponding class labels. The data is split into a training set of 50,000 images and their class labels and test set of 10,000 images and their class labels. There are 10 classes, represented as numerical values in the range of 0 to 9. The 10 classes in order from 0 to 9 are airplane, automobile, bird, cat, deer, dog, frog, horse, ship, and truck. There are 6000 images per class, a 1000 of each class in the test set and 5000 of each in the training set. For this project, the training set of 50,000 was further split into a training set of 48,000 and a validation set of 2,000.

Each image in the dataset is 32x32 pixels per channel. The images are in color and therefore represented by 3 channels, red, green, and blue. The total number of elements per image is 3072 (32x32x3). Each pixel ranges in intensity value from 0 to 255. For this project, the pixels were normalized by 255. Normalizing the pixel values is essential for updating the weights and optimizing performance of the neural network.

Multilayer Perceptron Model Description:

The model has a total of 3072 inputs, 1024 neurons for the first hidden layer, and each subsequent hidden layer with a quarter of the number of neurons as the last, until the final layer with 10 neurons, representing the 10 classes. The neural network has an input layer, followed by 4 hidden layers, and an output layer. The first hidden has 1024 neurons followed by three additional hidden layers of 256, 64, and 16 neurons, respectively. Each of these neurons utilizes a ReLu activation function. The final or output layer consists of 10 neurons and utilizes a softmax activation function. The use of a ReLu function at the output layer was attempted but the results were significantly lower than when a sigmoid or softmax activation function was used.

The various combinations of layers and activation functions tested and can be seen below.

1)	ReLu-ReLu-ReLu-ReLu-Softmax (Final Neural Network)
2)	ReLu-ReLu-ReLu-ReLu-Sigmoid
3)	ReLu-ReLu-ReLu-ReLu-Tanh
4)	Sigmoid-Sigmoid-Sigmoid-Sigmoid-Softmax
5)	Tanh-Tanh-Tanh-Tanh-Sigmoid
6)	Tanh-Tanh-Tanh-Tanh-Softmax

The neural network utilizes a Gradient Descent Optimizer (tf.train.GradientDescentOptimizer) and measures loss, accuracy, and error rate. For the final model, a learning rate of 0.05 was used and 20 epochs were run. The validation error was logged at every 5 epochs. Once the 20 epochs were finished, the test data was run through the model. The model then predicted the classes of the test images and stored them into an array that was compared to the test labels to generate a confusion matrix and classification report.
