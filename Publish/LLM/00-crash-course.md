# Regression
- regression
	- a line which shows the relation between house size and it's price
- loss = predicted value - actual value
- loss function = cost function
	- MSE/ MAE/ Huber Loss
	- Cross Entropy
		- binary/ categorical
- gradient decent : in this direction we can make our loss decreased, when the gradient is zero, then we can say we reach to an optimal point
- learning rate: it is always multiplied with the gradient, step to big/ small or grain too coarse/ fine
# Abritrary Function Approximation
- neural network is capable of approximating any function in the data, making it a universal function approximator. Let a nn learn the weights which would act as the parameters of the unknown function between the features and labels
# MINIST 
- import lib
- load the minist dataset
- define a simple neural network
- define loss function and optimizer
- train the network
- evaluate the network and visualize predictions
# NeuralNets
- backpropagation: of the gradients from the end(loss function result) to the beginning(inputs)
- activation function : tanh which adds non linearty 
- Pytorch: is a very popular library to build neural networks and train them
# Neurons
- task: of a neuron is to do multiply and accumulate.(doing a vector dot product between two vectors) one is the input x and the other is the weights w and then it passes through an activation function to introduce non linearity
- how to build a neural net: it is a n parties graph. Neurons are connected to each other in layers and no two neurons from the same layer have a connection between them, generally all neurons from one level are connected to all the other neurons in the next level