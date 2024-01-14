# OneShotLearning
Implementation of the paper "One Shot Learning using Siamese Network"

We are using the Omniglot dataset for training our Siamese Network with a few examples of each character in provided alphabets. A Siamese Network is, as the name suggests (Siamese means "twins") consists of a pair of twin networks that process a pair of input (here, a pair of images) and provide a similarity score using the L1 Distance (also called the Manhattan Distance). The distance is passed though a deep Sigmoidal layer to generate a binary classification of "Similar" or "Dissimilar"

Here is an understanding of the base architecture upon which the Siamese Network is built:

## Input Layer:

Input(shape=input_shape): This line creates the input layer of the network. input_shape should match the shape of your input images. In the case of the Omniglot dataset, this would typically be the height, width, and number of channels of the images.

## Convolutional Layer:

Conv2D(64, (3, 3), activation='relu')(input): This line adds a 2D convolutional layer to the network. It has 64 filters, each with a 3x3 kernel. The activation function used is ReLU (Rectified Linear Unit). This layer will extract features from the input image.

## Max Pooling Layer:

MaxPooling2D((2, 2))(x): This line adds a 2D max pooling layer with a 2x2 pool size. Max pooling reduces the spatial dimensions (height and width) of the input volume for the next convolutional layer. It helps reduce computation and mitigates overfitting by providing an abstracted form of the representation.

## Flattening Layer:

Flatten()(x): This flattens the 2D arrays outputted by the previous max pooling layer into 1D arrays. This is necessary because the next layer is a dense layer, which requires 1D input.

## Dense Layer:

Dense(128, activation='relu')(x): This is a fully connected layer with 128 neurons and ReLU activation. It takes the flattened features from the previous layer and learns non-linear combinations of these features.
