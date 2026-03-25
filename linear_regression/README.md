# Linear Regression from Scratch

## Model

y = Xw + b

- X: Input features
- w: Weights
- b: Bias

---

## Loss Function (MSE)

L = (1/n) * Σ (y - ŷ)^2

Goal: Minimize error between prediction and actual value.

---

## Gradient

dL/dw = (-2/n) Xᵀ (y - ŷ)

dL/db = (-2/n) Σ (y - ŷ)

---

## Algorithm

1. Initialize weights and bias
2. Predict output
3. Compute loss
4. Compute gradients
5. Update weights
6. Repeat

---

## Observations

- Loss decreases over time
- Learning rate affects convergence
- Model fits linear data well
