# link


# Summary 
What is a Cost Function?

A **Cost Function** (also known as a **Loss Function** or **Objective Function**) is a crucial component in machine learning.

Its core purpose is to **quantify how "wrong" a model's predictions are compared to the actual truth**.

- **Measuring Error:** It takes the model's prediction and the true (target) value as input and outputs a single number representing the "cost" or "penalty" for that prediction. A higher cost means a worse prediction.
- **Guiding Learning:** During the training process, the goal of the machine learning algorithm (like [[gradient descent]]) is to **minimize this cost function**. By finding the parameters ([[weights]] and [[biases]]) that lead to the lowest cost, the model learns to make more accurate predictions.
- **Specific to Task:** The choice of cost function depends on the type of machine learning task (e.g., Mean Squared Error for regression, Cross-Entropy for classification).
In essence, a cost function is like a scorekeeper that tells the model how well it's doing. The model's primary goal during training is to get the lowest score possible, thereby making its predictions as accurate as possible.
---

# Related Concepts

*  [[regression]]
* [[gradient descent]]
* [[supervised learning]]
