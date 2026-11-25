# ML Unit 3 — Quick Summary Notes
## Supervised Learning | One-Page Revision

---

### 🔑 Key Definitions

| Term | Definition |
|------|-----------|
| **Linear Regression** | Predicts continuous value using linear equation |
| **Logistic Regression** | Predicts probability (0-1) using sigmoid, for classification |
| **Gradient Descent** | Minimises loss by moving in negative gradient direction |
| **SGD** | GD variant using 1 sample per update (fast, noisy) |
| **Pruning** | Reduces tree complexity to prevent overfitting |
| **Naive Bayes** | Probability-based classification using Bayes' Theorem |

---

### 📊 LR: 5 Assumptions
**L**azy **I**ndians **H**ate **N**on-veg **M**ondays
1. **L**inearity
2. **I**ndependence
3. **H**omoscedasticity
4. **N**ormality of residuals
5. No **M**ulticollinearity

---

### 📊 Metrics
| MSE | RMSE | MAE | R² |
|-----|------|-----|----|
| Squared avg | √MSE | Absolute avg | Variance explained |

---

### 📊 GD Variants
| Batch (full, slow, stable) | SGD (1 sample, fast, noisy) | Mini-Batch (32-64, balanced) |

---

### 📊 Pruning
| Pre-pruning (early stop) | Post-pruning (remove branches) |
| Max depth, min samples | Cost Complexity, Reduced Error |

---

### 📐 Formulas (RAT LO!)
```
Linear:    y = mx + c
Logistic:  σ(z) = 1/(1+e^-z)
GD:        θ = θ - α × ∇J(θ)
Bayes:     P(C|X) = P(X|C) × P(C) / P(X)
```

---

### 📊 NB Types
| Gaussian (continuous) | Multinomial (text/count) | Bernoulli (binary) |

---

### ⚡ Last-Minute Recap
1. LR: 5 assumptions, MSE/RMSE/MAE/R² metrics
2. LogR: sigmoid, Cross-Entropy loss (NOT MSE!), MLE
3. GD: 4 steps, α critical — too big = overshoot, too small = slow
4. SGD variants: Batch/SGD/Mini-Batch
5. Pruning: Pre (during growth) & Post (after growth)
6. NB: Bayes Theorem, "naive" = feature independence assumption

---

*Quick revision complete!* 🎯
