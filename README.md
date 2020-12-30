# MNIST-Classifier
MNIST Classifier on Python- using only Torch Tensor manipulations.
NOT allowed to use:
○ Auto-differentiation - backward()
○ Built-in loss functions
○ Built-in activations
○ Built-in optimization
○ Built-in layers (torch.nn)

Obtained at least 75% accuracy on the test set (got 92%).

Inside the train file is the MNIST training process.
We got an input of 784 (28 pixels * 28 pixels), the training worked best for us with 1 hidden layer in size 64,
batch size of 100, learning rate = 1 and with 50 epochs.

We first set up a net with weights and biases (according to the size of the hidden layer).
We started the forward process where we used sigmoid on the hidden layer and softmax on the result.

Next, we performed the backward process, using the gradients we calculated in the theoretical part and the predicted
values from the forward phase.
In the backward process we tried to learn with learning rate = 0.001, then with 0.01 and in the end we got
the best result with learning rate = 1.
To know the percentage of accuracy on the net, we performed a loop that goes through each epoch
(at first we tried sizes 10, 30 and in the end we got the best result with a size of 50).
For each epoch we calculated whether we were right in our prediction.

In the evaluate file we performed the same process, on the test set.

At the end we printed the average accuracy on the test set and two graphs describing the accuracy
of the sets in relation to the time (the epochs).

Hyperparameters: 
input_size = 784 
hidden_size = 64 
num_classes = 10 
num_epochs = 50 
batch_size = 100 
learning_rate = 1

Files Description:
1. train.py - The MNIST training process
2. model.pkl - The trained network with trained weights
3. eval.py - A file with a function called "evaluate()". The function load the MNIST test-set, load our trained network, and return the average accuracy over the test-set.
