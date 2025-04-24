# MLP
MLP (Multilayer Perceptron) implementation

1)Data Upload and Preprocessing:

It starts by uploading a file (names.txt) using Google Colab’s file upload feature. The file is read, and the names are split into a list of words. A vocabulary is built from the unique characters in the words, and two dictionaries are created for character-to-index (stoi) and index-to-character (itos) mappings. The input (X) and target (Y) sequences are prepared for training, where X contains the context characters and Y contains the next character to predict.

2) Neural Network Architecture:

Randomly initialized weights (W1, W2) and biases (b1, b2) are set up for a two-layer neural network. The hidden state (h) is computed using a tanh activation function.
The logits are calculated, and then the probabilities for the next character are obtained using the softmax function.

3)Loss Calculation: 

The final loss is calculated over the entire dataset using cross-entropy

4)Backpropagation and optimization:

A minibatch of data is selected. A forward pass computes the logits and loss using cross-entropy. A backward pass computes gradients. The weights are updated using gradient descent.

# Implementing Wavenet Architechure 

1) Learned about some module of pytorch and also pytorchify my code.

2) Take some inspiration from the architechure of wavenet. So basically in my MLP what I was doing is taking all these info about the word feature vector and squeeze initially in just 1 layer but as now adopting this wavenet approach I am not squeeshing it in 1 layer but I divide the batch size into bigrams(in this case) and introducing them one by one in the corresponding hidden layers. So, may be that can improve the performance of my model. 

3) I inc my dimensions of word feature vector to 10 and hidden layer's neurons to 200 and basically run the same MLP on context length of 8 and see the results. and they improved a bit.

4) Then I implemented the wavenet architechure ( not completely as already being told). In that case we need to introduce 3 dimensional tensor s into our neural net. For that I have to change my embedding class, flattening class. and then implemented and have seen no changes but later realised that I also have to change the batch normalization layer because it is sort of programmed to work on 2d tensor so, have to update that. then run it and the model definitely improved. 

5) I also learned about the problems that can be caused by the batch normalization layer. Basically you have to clearly defined a state or phase in which it is currently in. If you are in training phase and finding val loss then it will result into error.
A backward pass computes gradients. The weights are updated using gradient descent.
