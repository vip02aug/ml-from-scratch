# Linear Regression: Closed Form vs Gradient Descent

## Introduction

This project implements Linear Regression from scratch using two approaches:

1. Closed-form solution (Normal Equation)
2. Gradient Descent (iterative optimization)

The goal is to understand:
- Mathematical formulation
- Optimization process
- Performance differences
- Scalability behavior

---

## Mathematical Model

For a single feature:

$$ \hat{y} = mx + b $$

For multiple features (vector form):

$$ \hat{y} = Xw + b $$

Where:
- \( X \) = input features  
- \( w \) = weights  
- \( b \) = bias  
- \( \hat{y} \) = predicted output  

---

## Loss Function (Mean Squared Error)

$$ L = \frac{1}{n} \sum (y - \hat{y})^2 $$

Goal: minimize the error between predicted and actual values.

---

## Closed-Form Solution (Normal Equation)

$$ w = (X^T X)^{-1} X^T y $$

### Characteristics
- Direct analytical solution
- No iterations required
- Computationally expensive for large datasets
- Requires matrix inversion

---

## Gradient Descent Solution

### Update Rule

$$ w = w - \alpha \frac{\partial L}{\partial w} $$  
$$ b = b - \alpha \frac{\partial L}{\partial b} $$  

Where:
- \( \alpha \) = learning rate  

### Characteristics
- Iterative optimization method
- Scalable to large datasets
- Approximate solution
- Requires tuning (learning rate, epochs)

---

## Implementation

Notebook: [Linear Regression Code](Linear_Regression.ipynb)

---

## Results

### Regression Fit
![Regression Plot](regression_plot.png)

### Loss Curve (Gradient Descent)
![Loss Curve](loss_curve.png)

---

## Comparison: Closed Form vs Gradient Descent

| Method            | Type        | Speed (Small Data) | Scalability | Accuracy        |
|------------------|------------|--------------------|-------------|-----------------|
| Closed Form      | Analytical | Fast               | Poor        | Exact solution  |
| Gradient Descent | Iterative  | Slower             | Good        | Approximate     |

---

## Time Complexity Analysis

Closed Form:
- Complexity: $$( O(d^3)$$
- Dominated by matrix inversion

Gradient Descent:
- Complexity: $$O(n \cdot d \cdot \text{epochs})$$

### Observation

- Closed form is efficient for small datasets
- Performance degrades with increasing dataset size
- Gradient descent scales better for large data

---

## Experiments with Dataset Size

We tested both methods with increasing data sizes.

### Observations

- Closed-form computation time increases significantly
- Gradient descent remains stable with larger datasets
- Both methods produce similar MSE values

---

## Learning Rate Experiment

- Small learning rate → slow convergence  
- Optimal learning rate → stable and fast convergence  
- Large learning rate → unstable behaviour  

---

## Insights

- Closed-form solution provides exact parameters but is not scalable
- Gradient descent is preferred in real-world machine learning
- Optimisation plays a crucial role in ML algorithms
- A trade-off exists between accuracy and computational efficiency

---

## Connection to Control Systems

Linear regression is closely related to **system identification**, where system parameters are estimated from observed data.

---

## Conclusion

This project demonstrates:
- Mathematical understanding of linear regression
- Practical implementation from scratch
- Comparison of analytical and iterative methods
- Performance and scalability analysis

---

## Author

Vipul Verma
