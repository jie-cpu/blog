# link


# Summary 

In machine learning, **Hyperparameters** are settings or configurations that are **set _before_ the training process begins**, and they control how the learning algorithm behaves.

Their core purpose is to **govern the learning process itself**, influencing the model's structure, performance, and training efficiency.

- **Difference from Model Parameters:**
    
    - **[[model parameter]]** (e.g., weights and biases in a neural network) are **learned by the model** _during_ training from the data.
    - **Hyperparameters** are **set by the user/developer** _before_ training.
- **Examples:** Common hyperparameters include:
    
    - **Learning Rate:** How big a step Gradient Descent takes.
    - **Number of Epochs:** How many times the model sees the entire training dataset.
    - **Batch Size:** How many samples are processed at once during training.
    - **Number of Hidden Layers/Neurons:** In a neural network, the architectural depth and width.
    - **Regularization Stregth:** How much to penalize model complexity (e.g., in Ridge/Lasso regression).
In essence, hyperparameters are like the "tuning knobs" or "recipe settings" for your machine learning model. You adjust them to get the best performance out of your model, but the model itself doesn't learn these settings from the data.
---

# Related Concepts

*  [[hyperparameter optimization]]
* [[learning rate]]
* [[number of layers]]
* [[training epochs]]
* [[hidden size]]
