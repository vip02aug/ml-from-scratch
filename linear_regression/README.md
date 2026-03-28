# Linear Regression: Closed Form vs Gradient Descent (Full Analysis)

## Introduction

This project implements Linear Regression from scratch using:

- Closed-form solution (Normal Equation)
- Gradient Descent (iterative optimization)

The focus is on **practical comparison**, including:
- Dataset size scaling
- Feature dimension scaling
- Learning rate effects
- Time and convergence behavior

Implementation is fully from scratch in Python. :contentReference[oaicite:0]{index=0}

---

## Experiment 1: Dataset Size Comparison (d = 1)

| Size  | CF Time | GD Time | CF MSE | GD MSE |
|-------|--------|--------|--------|--------|
| 100   | ~0.0003 | ~0.03  | low    | low    |
| 500   | ~0.0002 | ~0.03  | low    | low    |
| 1000  | ~0.0002 | ~0.037 | low    | low    |
| 5000  | ~0.0003 | ~0.077 | low    | low    |
| 10000 | ~0.0005 | ~0.12  | low    | low    |

### Observation

- Closed-form remains extremely fast
- Gradient descent time increases with dataset size

### Key Insight

Closed-form does **not depend on n strongly when d = 1**,  
because matrix inversion is trivial.

---

## Experiment 2: Feature Dimension Comparison (n = 1000)

### Observation

- Closed-form time increases significantly with feature dimension
- Gradient descent scales more smoothly

### Key Insight

- Closed-form complexity dominated by \( d^3 \)
- Gradient descent depends on \( n \cdot d \cdot T \)

👉 Closed-form becomes impractical for high-dimensional data.

---

## Experiment 3: Learning Rate Comparison

| LR     | Time (s) | Epochs | Final MSE | Converged |
|--------|----------|--------|-----------|----------|
| 0.0001 | High     | High   | Low       | Yes      |
| 0.001  | Medium   | Medium | Low       | Yes      |
| 0.01   | Low      | Low    | Low       | Yes      |
| 0.1    | Very Low | Very Low | Low     | Yes      |
| 0.5    | Unstable | High / Oscillation | High | No / Poor |

### Observation

- Small learning rate → slow convergence (many epochs)
- Moderate learning rate → fastest convergence
- Large learning rate → instability

### Key Insight

Learning rate affects:

Learning Rate → Epochs → Time → Final MSE

---

## Experiment 4: Full Comparison

| Method | LR | Time | Epochs | MSE |
|--------|----|------|--------|-----|
| Closed Form | - | Very Low | 1 | Optimal |
| GD | varies | Depends | Depends | Approx |

### Observation

- Closed-form is fastest for low-dimensional data
- Gradient descent performance depends on learning rate
- GD requires multiple iterations, CF does not

---

## Time Complexity

Closed Form:
O(n d² + d³)

Gradient Descent:
O(n d T)

Where:
- n = number of samples
- d = number of features
- T = number of epochs

---

## Key Insights

1. Closed-form is efficient only when feature dimension is small  
2. Gradient descent scales better for large datasets  
3. Learning rate controls convergence speed  
4. Increasing dataset size mainly affects gradient descent  
5. Increasing feature dimension mainly affects closed-form  
6. Learning rate indirectly affects runtime via epochs  

---

## Visualization

Generated plots include:
- Time vs Dataset Size
- Time vs Feature Dimension
- Loss curves for different learning rates
- Epochs vs Learning Rate
- MSE vs Learning Rate
- Time vs Learning Rate

---

## Conclusion

This project demonstrates:

- Analytical vs iterative optimization
- Scalability limitations of closed-form solution
- Importance of learning rate in optimization
- Practical performance trade-offs in ML systems

---

## Author

Vipul Verma
