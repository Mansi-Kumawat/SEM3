# ML Unit 3 — Practice Questions
## Supervised Learning (Week 3 + Week 4)

---

## Part A: Multiple Choice (1 Mark)

**Q1.** Linear Regression predicts: (A) Category (B) Continuous value (C) Probability (D) Class label
**Answer: (B)**

**Q2.** Sigmoid function output range: (A) -1 to 1 (B) 0 to ∞ (C) 0 to 1 (D) -∞ to ∞
**Answer: (C)**

**Q3.** Which loss does Logistic Regression use? (A) MSE (B) MAE (C) Cross-Entropy (D) Hinge
**Answer: (C)**

**Q4.** SGD uses how many samples per update? (A) All (B) Half (C) One (D) Batch of 32
**Answer: (C)**

**Q5.** Pre-pruning is also called: (A) Post-training (B) Early Stopping (C) Cost Complexity (D) Reduced Error
**Answer: (B)**

**Q6.** Naive Bayes assumes: (A) Features dependent (B) Features independent given class (C) No features (D) All features equal
**Answer: (B)**

**Q7.** R² value range: (A) -1 to 1 (B) 0 to 1 (C) 0 to ∞ (D) -∞ to ∞
**Answer: (B)**

**Q8.** MLE is used in: (A) Linear Regression (B) Logistic Regression (C) Decision Tree (D) K-Means
**Answer: (B)**

**Q9.** Which is NOT an LR assumption? (A) Linearity (B) Independence (C) Normality of X (D) No multicollinearity
**Answer: (C)** — Normality of RESIDUALS, not X

**Q10.** Gaussian NB is used for: (A) Binary features (B) Count data (C) Continuous features (D) Text data
**Answer: (C)**

---

## Part B: Short Answer (2 Marks)

**Q1.** Differentiate Linear Regression and Logistic Regression.
**Answer:** LR predicts continuous values using MSE loss and Least Squares. LogR predicts probabilities (0-1) using sigmoid, Cross-Entropy loss, and MLE.

**Q2.** List the 4 steps of Gradient Descent.
**Answer:** 1. Define Loss Function. 2. Compute Gradient. 3. Update: θ = θ - α×∇J(θ). 4. Repeat until convergence.

**Q3.** What is pruning? Why is it needed?
**Answer:** Pruning reduces decision tree complexity to prevent overfitting and improve generalisation. Without pruning, trees grow too deep and memorise training data.

**Q4.** Write Bayes' Theorem and explain each term.
**Answer:** P(C|X) = P(X|C)×P(C)/P(X). Prior P(C), Likelihood P(X|C), Evidence P(X), Posterior P(C|X).

---

## Part C: Descriptive (5 Marks)

**Q1.** Explain Gradient Descent with its variants and the role of learning rate.

**Answer Structure:**
**Definition:** Optimisation algorithm minimising loss by moving in negative gradient direction.
**Formula:** θ = θ - α × ∇J(θ)
**Steps:** Define loss → Compute gradient → Update → Repeat
**Variants:** Batch GD (full data, stable, slow), SGD (1 sample, fast, noisy), Mini-Batch (balanced)
**Learning Rate:** Too large → overshoot, too small → slow, just right → smooth convergence
**Advantages:** Simple, scalable, works with many models
**Disadvantages:** May get stuck in local minima, sensitive to α
**Challenges:** Choosing α, handling non-convex functions, convergence criteria

**Q2.** Explain Naive Bayes Classifier with Bayes' Theorem and its types.

**Answer Structure:**
**Definition:** Probability-based classification using Bayes' Theorem with feature independence assumption.
**Formula:** P(C|X) = P(X|C)×P(C)/P(X)
**Components:** Prior, Likelihood, Evidence, Posterior
**Types:** Gaussian NB (continuous), Multinomial NB (text/count), Bernoulli NB (binary)
**Advantages:** Fast, works with high dimensions, good for text
**Disadvantages:** Independence assumption often violated, zero probability problem
**Challenges:** Handling continuous features, smoothing for zero probabilities

---

*Practice makes perfect!* 🎯
