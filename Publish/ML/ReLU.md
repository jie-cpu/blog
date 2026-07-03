# link


# Summary 

**ReLU (Rectified Linear Unit)** is the most widely used **activation function** in artificial neural networks, especially in deep learning.

Its core purpose is to **introduce non-linearity into the network**, allowing it to learn more complex patterns than it could with only linear transformations.

- **Simple Operation:** It's a very simple function. It outputs the input directly if the input is positive, otherwise, it outputs zero.
    - Mathematically: f(x)=max(0,x)
    - If x>0, then f(x)=x
    - If x≤0, then f(x)=0
- **Why it's Popular:**
    - **Computational Efficiency:** It's very fast to compute compared to older activation functions like [[sigmoid]] or [[tanh]].
    - **Solves Vanishing Gradient Problem:** For positive inputs, its derivative is a constant (1), which helps prevent the gradients from becoming too small during backpropagation, a common problem in deep networks (vanishing gradient problem).
    - **Sparsity:** It can lead to "sparse" activations, where many neurons output zero, potentially making the network more efficient.
In essence, ReLU acts like a switch: it turns on a neuron if its input is positive, passing that signal forward, but effectively turns it off if the input is negative. This simplicity and efficiency have made it a cornerstone of modern deep learning.

# Related Concepts

*  [[]]
