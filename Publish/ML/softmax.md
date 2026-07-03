# link


# Summary 

**Softmax** is an **activation function** primarily used in the **output layer of a neural network for multi-class classification problems**.
Its core purpose is to **convert a vector of arbitrary real-valued scores (or "logits") into a probability distribution**, where each value represents the probability of an input belonging to a specific class.
- **Input:** It takes a vector of raw scores from the previous layer (e.g., the outputs of the last [[fully connected layer]] before the final prediction). These scores can be any real number, positive or negative.
- **Output:** It squashes these scores into a vector of probabilities, where:
    - Each probability is between 0 and 1.
    - All probabilities sum up to 1.
- **Mathematical Operation (Simplified):** For each score, it applies an exponential function to make it positive, then divides by the sum of all exponential values. This normalizes the scores into probabilities.
    - P(classj​∣input)=∑k=1K​ezk​ezj​​
        - zj​ is the raw score (logit) for class j.
        - K is the total number of classes.

**In essence, Softmax acts like a "normalizer" or "decision-maker" at the end of a classification network. It takes a model's raw confidence scores for each possible category and turns them into a clear set of probabilities, allowing you to easily see how likely the input belongs to each class.
# Related Concepts

*  [[]]
