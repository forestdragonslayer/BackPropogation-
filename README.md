 Neural Network Architecture:
The architecture of the neural network is as follows:
Input Layer: It has 2 neurons (input_size = 2), which correspond to the features in the input data X.
Hidden Layer: It has 2 neurons (hidden_size = 2), where the weights from the input layer are connected to these neurons.
Output Layer: It has 1 neuron (output_size = 1), which gives the output of the neural network.
Backpropagation:
Backpropagation adjusts the weights to minimize the error. Here's how it works:
Compute the error in the output layer (error_output = y - output_layer_output), where y is the true label, and output_layer_output is the network's prediction.
Calculate the delta (gradient) for the output layer, which involves multiplying the error by the derivative of the sigmoid function applied to the output layer.
Propagate the error backward to the hidden layer by calculating the error in the hidden layer and then computing the hidden layer delta.
Update the weights and biases using gradient descent. The weight updates are proportional to the learning rate and the calculated gradients.
The following steps are implemented:
output_layer_delta = error_output * sigmoid_derivative(self.output_layer_output)
hidden_layer_delta = error_hidden * sigmoid_derivative(self.hidden_layer_output)
The weights and biases are updated accordingly:
self.weights_hidden_output += self.hidden_layer_output.T.dot(output_layer_delta) * learning_rate
self.weights_input_hidden += X.T.dot(hidden_layer_delta) * learning_rate
**Sigmoid and Derivative:**

sigmoid(x) computes the output of the sigmoid activation function. It maps any real-valued input into a value between 0 and 1.
sigmoid_derivative(x) is the derivative of the sigmoid function, which is used during backpropagation to calculate gradients.
