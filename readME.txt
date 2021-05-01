dataset source: https://deepai.org/datasets
data name is MNIST

data details:
The data is stored in a very simple file format designed for storing vectors and multidimensional matrices. 
General info on this format is given at the end of this page, but you don't need to read that to use the data files.

All the integers in the files are stored in the MSB first (high endian) format used by most non-Intel processors. 
Users of Intel processors and other low-endian machines must flip the bytes of the header.

There are 4 files:

train-images-idx3-ubyte: training set images 
train-labels-idx1-ubyte: training set labels 
t10k-images-idx3-ubyte:  test set images 
t10k-labels-idx1-ubyte:  test set labels
                           
The training set contains 60000 examples, and the test set 10000 examples.
There are 10 distinct labels in the training and testing sets (0 - 9). 

The first 5000 examples of the test set are taken from the original NIST training set. 
The last 5000 are taken from the original NIST test set. The first 5000 are cleaner and easier than the last 5000.



============
outline
================

1. pull in the model (i.e., load data and apply the model)

   The MNIST data was loaded and split into training and testing sets.
   Sequential model (found in Keras which is part of TensorFlow library) was applied to the data.
   We arbitrarily chose four layers: input, output and two hidden layers.
   The model was compiled using the adaptive moment estimation (adam) as the optimizer, sparse_categorical_crossentropy as the loss and accuracy as the metrics.

2. show iterations (hyperparameter tuning)
   The number of iterations used was 10.
   

3. Reflect model performance
   The model was evaluated using the test set.
   The first two images were visualized and it was realized that the second number which is index 1 was 2. To ascertain that the model could predict the numbers correctly, the argmax function was used to find the node/output with the highest probability. This corresponded to node 2.



