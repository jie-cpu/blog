# link


# Summary 

**Bayesian Optimization** is an advanced, **sequential strategy for hyperparameter optimization** (or optimizing any expensive, black-box function).

Its core purpose is to **efficiently find the best hyperparameters** by intelligently choosing which combinations to test next, rather than trying them randomly or exhaustively.

- **Intelligent Exploration:** Unlike Grid Search or Random Search, Bayesian Optimization doesn't just try hyperparameters blindly. It uses information from past evaluations to decide which set of hyperparameters to try next, aiming to minimize the cost function with fewer attempts.
    
- **Two Key Components:**
    
    1. **Probabilistic Model (Surrogate Model):** It builds a statistical model (often a Gaussian Process) of the objective function (e.g., your model's validation performance) based on the hyperparameters already tested. This model estimates both the mean performance and the uncertainty at unobserved points.
    2. **Acquisition Function:** This function uses the probabilistic model to suggest the next best hyperparameter combination to evaluate. It balances **exploration** (trying uncertain but potentially good areas) and **exploitation** (focusing on areas already known to be good).
- **Efficiency:** It's particularly useful when evaluating each hyperparameter combination is computationally very expensive (e.g., training a large deep learning model).
    In essence, Bayesian Optimization is like having a smart guide searching for the lowest point in a foggy landscape. Instead of randomly wandering, the guide uses a map (the probabilistic model) that gets better with each step taken, and then strategically decides where to go next (using the acquisition function) to find the bottom most efficiently.
---

# Related Concepts

*  [[]]
