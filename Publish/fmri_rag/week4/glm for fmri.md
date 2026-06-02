## **The Core Idea**

In fMRI, the General Linear Model (GLM) is used to determine whether a brain voxel responds to a specific experimental task.

The model is:

$$
y = \beta x + \varepsilon
$$
where:

- **y** = observed BOLD signal (dependent variable) ------- ----y(t)
- **x** = predicted BOLD signal derived from the experimental design  ----------------x(t) (independent variable/ REGRESSOR/ 自变量)
- **β** = strength of the relationship between the predictor and the observed signal
- **ε** = unexplained noise or error


- ![[Pasted image 20260602225614.png]]