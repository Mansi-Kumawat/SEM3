# ML Unit 6 — Quick Summary Notes
## Ensemble Learning | One-Page Revision

---

### 🔑 Key Definitions

| Term | Definition |
|------|-----------|
| **Bias-Variance** | Total Error = Bias² + Variance + Irreducible |
| **Ensemble** | Multiple weak learners → One strong learner |
| **Random Forest** | Bagging: bootstrap + random features + voting |
| **AdaBoost** | Sequential boosting, weights hard examples |
| **XGBoost** | Gradient boosting, corrects residuals |
| **Confusion Matrix** | TP, FP, FN, TN → Precision, Recall, F1 |
| **ROC-AUC** | TPR vs FPR, higher = better |

---

### 📊 Bias vs Variance
| High Bias (Underfit) | High Variance (Overfit) | Sweet Spot |
|---|---|---|
| Too simple | Too complex | Balanced |
| High train + test error | Low train, high test error | Both low |

---

### 📐 Critical Formulas (RAT LO!)
```
AdaBoost α:    0.5 × ln((1-ε)/ε)
Weight update: w × e^α (misclassified)
Precision:     TP/(TP+FP)
Recall:        TP/(TP+FN)
F1:            2×P×R/(P+R)
```

---

### 📊 Bagging vs Boosting
| Bagging (Parallel, Variance, RF) | Boosting (Sequential, Bias, AdaBoost/XGBoost) |

---

### ⚡ Last-Minute Recap
1. Bias² + Variance + Irreducible = Total Error
2. Ensemble: weak → strong
3. RF: Bootstrap + random features + vote
4. AdaBoost: α formula, weight update
5. XGBoost: Residuals, Gain, pruning
6. Confusion Matrix: TP/FP/FN/TN → P/R/F1
7. ROC-AUC: Higher = better

---

*Quick revision complete!* 🎯
