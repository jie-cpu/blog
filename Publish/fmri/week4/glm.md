### I. Core Concepts of GLM: Analysis & Summary

The video breaks down the three main pillars of Generalized Linear Models (GLMs) from a beginner's perspective:

#### 1. Starting with Classical Linear Regression

- The formula for classical linear regression is $y = mx + b$ (or $y = \beta_0 + \beta_1x + \epsilon$).
    
    - **$x$**: The independent variable (predictor/explanatory variable).
        
    - **$y$**: The dependent variable (the outcome to be predicted).
        
    - **$m$ or $\beta_1$**: The slope/weight (representing how much $y$ changes with each incremental increase in $x$).
        
    - **$b$ or $\beta_0$**: The intercept (the baseline value of $y$ when $x = 0$).
        
- Real-world data is rarely a perfect fit, which is why models must account for **Residuals**, representing how much each true data point deviates from the predicted line.
    

#### 2. Why "Generalized"?

Classical linear regression assumes that errors follow a **normal (Gaussian) distribution** and that predicted values can be any real number. However, real-world data often violates these assumptions. The brilliance of GLMs lies in their **flexibility**, allowing them to handle non-linear and non-normal data by introducing different **Distribution Families** and **Link Functions**:

- **Gaussian/Normal Distribution**: Suited for traditional continuous variables, such as height or exam scores.
    
- **Poisson Distribution**: Suited for "count data" (e.g., the number of dogs in a park). Its default link function (Log) ensures that predicted values approach zero but never become negative.
    
- **Binomial Distribution**: Suited for data with only two possible outcomes (e.g., "winning/losing" or "positive/negative pregnancy test"), producing an S-shaped prediction curve.
    

### II. Why is GLM Closely Related to fMRI?

While the video uses everyday examples like band tour revenues and counting dogs to explain GLMs, in the fields of **neuroscience and fMRI (functional Magnetic Resonance Imaging) data analysis**, the GLM is the **most fundamental, golden-standard algorithm** (the core of almost all fMRI analysis software like SPM, FSL, and AFNI is built upon GLMs).

Here is why they are inextricably linked:

#### 1. The Nature of fMRI Data: "Time-Varying Continuous Signals"

During an fMRI experiment, the scanner captures images of the whole brain every 1 to 2 seconds (TR). For each tiny unit in the brain—known as a **voxel** (a 3D pixel)—we obtain a **BOLD (Blood Oxygen Level-Dependent) signal time series** that fluctuates over the course of the experiment.

- In the GLM framework: This voxel's **BOLD signal time series acts as the dependent variable ($y$)**.
    

#### 2. Experimental Design Acts as the Independent Variable ($x$)

Suppose you are running an fMRI experiment where a participant looks at a flashing light (visual stimulus) for 10 seconds, rests for 10 seconds, and repeats this cycle.

- We can convert this experimental condition into a time series (1 when the stimulus is present, 0 during rest).
    
- Since blood flow in the brain lags behind neural activity by about 5 to 6 seconds, we convolve this stimulus sequence with a **Hemodynamic Response Function (HRF)** to generate a smooth "expected BOLD signal curve."
    
- In the GLM framework: This expected curve serves as the **independent/explanatory variable ($x$)** (also called a predictor or regressor).
    

#### 3. $\beta$ Weights Represent "Brain Activation Strength"

The GLM equation in fMRI runs independently for each individual voxel (a Mass Univariate Approach):

$$\text{Voxel BOLD Signal } (y) = \beta_1 \times \text{Expected Visual Stimulus } (x) + \beta_0 + \text{Error } (\epsilon)$$

Through matrix operations, the software calculates the **$\beta_1$ weight** for every single voxel:

- If a voxel is located in the **visual cortex**, its actual BOLD signal ($y$) will highly correlate with your visual stimulus prediction curve ($x$), resulting in a **very large** calculated $\beta_1$ value.
    
- If a voxel is in an area unrelated to vision (like the auditory cortex), its $\beta_1$ value will be close to 0.
    

#### 4. Statistical Testing and Statistical Parametric Mapping (SPM)

Once the $\beta$ values and residuals are calculated, a $t$-test or $F$-test is performed to determine if $\beta_1$ is significantly greater than 0.

- Ultimately, the statistical scores ($t$-values or $z$-values) for every voxel in the brain are color-coded and overlaid onto a structural brain image. This yields the **vibrant brain activation maps (Statistical Parametric Mapping)** commonly seen in neuroscience papers.
    

#### 5. Eliminating Artifacts (Controlling for Confounding Variables)

fMRI signals contain massive amounts of noise, such as microscopic **head motion** from the participant inside the scanner, as well as low-frequency drift caused by breathing and heartbeats.

- GLMs allow us to input these head motion parameters (displacement and rotation across the X, Y, and Z axes) into the equation as **covariates (additional independent variables: $x_2, x_3, \dots$)**.
    
- By doing this, the GLM can "regress out" these noises, allowing researchers to isolate and extract the true brain activation triggered by the experimental task.
    

### Summary

In short, **the GLM acts like a ruler. It takes your pre-designed, expected experimental curve ($x$) and matches it against the actual blood oxygen signals ($y$) of tens of thousands of brain locations one by one.** Whichever location matches the best (yielding a large and statistically significant $\beta$) reveals exactly which brain region was actively involved in that cognitive task. This is why GLM serves as the cornerstone of fMRI data analysis.