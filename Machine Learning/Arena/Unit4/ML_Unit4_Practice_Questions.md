# ML Unit 4 — Practice Questions
## Advanced Supervised Learning (Week 5 + Week 6)

---

## Part A: Multiple Choice (1 Mark)

**Q1.** Which activation function is most popular for hidden layers?
- (A) Sigmoid (B) Tanh (C) ReLU (D) Softmax
**Answer: (C)**

**Q2.** Backpropagation uses which mathematical rule?
- (A) Product rule (B) Chain rule (C) Power rule (D) Sum rule
**Answer: (B)**

**Q3.** In SVM, the nearest data points to the hyperplane are called:
- (A) Outliers (B) Margins (C) Support Vectors (D) Centroids
**Answer: (C)**

**Q4.** Which kernel is most popular for SVM?
- (A) Linear (B) Polynomial (C) RBF (D) Sigmoid
**Answer: (C)**

**Q5.** One-Class SVM is used for:
- (A) Classification (B) Regression (C) Anomaly Detection (D) Clustering
**Answer: (C)**

**Q6.** In a feedforward network, data flows:
- (A) In loops (B) Backward first (C) One direction only (D) Randomly
**Answer: (C)**

**Q7.** SVM optimization minimizes:
- (A) ||w|| (B) ||w||²/2 (C) Learning rate (D) Margin
**Answer: (B)**

**Q8.** Softmax activation is used for:
- (A) Binary output (B) Hidden layers (C) Multi-class output (D) Regression
**Answer: (C)**

**Q9.** ReLU function is:
- (A) 1/(1+e^-z) (B) max(0,z) (C) tanh(z) (D) e^z/Σe^z
**Answer: (B)**

**Q10.** Hard margin SVM requires:
- (A) Noisy data (B) Non-linear data (C) Linearly separable data (D) Large data
**Answer: (C)**

---

## Part B: Short Answer (2 Marks)

**Q1.** What is backpropagation? List its 4 steps.
**Answer:** Algorithm computing gradients by propagating error backward. Steps: Forward Pass → Compute Loss → Backward Pass (Chain Rule) → Update Weights.

**Q2.** Differentiate Hard Margin and Soft Margin SVM.
**Answer:** Hard Margin: No misclassification allowed, needs linearly separable data. Soft Margin: Allows some errors using slack variables, handles real-world noise better.

**Q3.** What is the kernel trick? Why is it needed?
**Answer:** Maps data to higher dimension where it becomes separable — without explicitly computing the transformation. Needed when data is not linearly separable in original space.

**Q4.** List 4 activation functions and their use cases.
**Answer:** Sigmoid (0-1, binary output), Tanh (-1 to 1, zero-centered), ReLU (hidden layers, most popular), Softmax (multi-class probability distribution).

---

## Part C: Descriptive (5 Marks — Professor's Format)

**Q1.** Explain Neural Networks with components and activation functions.

**Answer Structure:**
**Definition:** Brain-inspired ML algorithms with layers of interconnected neurons.
**Components:** Neurons (compute weighted sum + activation), Weights (learnable parameters), Layers (input, hidden, output), Activation Functions (non-linearity).
**Types of Activation:** Sigmoid (binary), Tanh (zero-centered), ReLU (most popular, hidden layers), Softmax (multi-class).
**Advantages:** Learns complex patterns, handles unstructured data, improves with more data.
**Disadvantages:** Needs lots of data, computationally expensive, black box (hard to interpret).
**Challenges:** Vanishing/exploding gradients, overfitting, choosing architecture.

**Q2.** Explain SVM with its optimization problem and kernel functions.

**Answer Structure:**
**Definition:** Finds optimal hyperplane with maximum margin between classes.
**Key Concepts:** Hyperplane (boundary), Margin (width), Support Vectors (nearest points).
**Optimization:** Minimize ||w||²/2 subject to yᵢ(w·xᵢ+b) ≥ 1.
**Kernel Trick:** Maps to higher dimension without explicit transform — K(xᵢ,xⱼ) = φ(xᵢ)·φ(xⱼ).
**Kernel Types:** Linear, Polynomial, RBF (most popular), Sigmoid.
**Advantages:** Effective in high dimensions, works with less data, versatile with kernels.
**Disadvantages:** Slow for large datasets, hard to interpret, sensitive to parameters.
**Challenges:** Choosing right kernel, tuning C and γ, scaling issues.

---

*Practice makes perfect!* 🎯
