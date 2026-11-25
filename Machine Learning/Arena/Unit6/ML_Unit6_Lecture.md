# ML Unit 6 — Ensemble Learning
## Complete Lecture Notes (Hinglish) | OLMCA602 | Week 9 + Week 10

---

## 1. Bias-Variance Tradeoff

**Definition:**
> Total Error = Bias² + Variance + Irreducible Error

**Matlab:** Har ML model mein do types ki galtiyan hoti hain — Bias aur Variance. Dono ko balance karna padta hai.

### Bias (Underfitting)
- Model **bahut simple** hai — complex patterns nahi seekh paata
- Training error **high**, Test error bhi **high**
- Example: Linear model use karna non-linear data pe
- **💡 Trick:** "Bias = Boring model — kuch seekha hi nahi!"

### Variance (Overfitting)
- Model **bahut complex** hai — training data ko yaad kar leta hai
- Training error **low**, lekin Test error **high**
- Example: Deep decision tree bina pruning ke
- **💡 Trick:** "Variance = Versatile on training, Vulnerable on test!"

### Sweet Spot
Balanced model — na underfit, na overfit. Generalise achha karta hai.

---

## 2. Ensemble Learning — Kyun?

**Definition:**
> Combining multiple weak learners to create a strong learner — a group of weak models can beat a single strong model!

**💡 Analogy:** Ek student se achha — poora class milkar decision le!

### Four Methods

| Method | Approach | Reduces | Example |
|--------|----------|---------|---------|
| **Bagging** | Parallel, bootstrap samples | Variance | Random Forest |
| **Boosting** | Sequential, weights hard examples | Bias | AdaBoost, XGBoost |
| **Stacking** | Multiple models + meta-learner | Both | Stacked ensemble |
| **Voting** | Multiple models vote | Both | Hard/Soft voting |

---

## 3. Random Forest — Bagging Ka Raja

**Definition:**
> Ensemble of decision trees using bootstrap samples and random feature subsets — predictions combined via majority voting.

### Process (4 Steps)
1. **Bootstrap samples** generate karo — random sampling WITH replacement
2. Har sample pe **decision tree** train karo
3. Splitting stages mein **random features** consider karo
4. **Combine:** Majority voting (classification) / Averaging (regression)

### Key Concepts
- **Bootstrap coverage:** ≈ 63.2% unique samples per bootstrap
- **Out-of-Bag (OOB):** Jo samples miss hue — validation ke liye free!
- **Random features:** Har split pe sirf √n features consider — diversity badhati hai
- **No pruning needed:** Individual trees overfit kar sakti hain, lekin forest average kar leta hai

### Worked Example
5 data points, K=3 trees:
- Bootstrap 1: {A,B,B,C,D} → Tree 1 votes "Yes"
- Bootstrap 2: {A,C,D,D,E} → Tree 2 votes "Yes"
- Bootstrap 3: {B,C,E,E,A} → Tree 3 votes "No"
- **Final: 2 Yes + 1 No → Majority = "Yes"** ✅

---

## 4. AdaBoost — Adaptive Boosting

**Definition:**
> Sequential ensemble that focuses on hardest examples — misclassified points get higher weights in each round.

**💡 Cricket Coach Analogy:** Coach batter ki weak deliveries pe focus karta hai har session mein. Har session ek weak learner hai — combined training sab weaknesses cover karti hai!

### Algorithm Steps
1. Initialize equal weights: wᵢ = 1/n for all samples
2. Train weak learner (decision stump)
3. Calculate error rate: ε = Σ(wᵢ × misclassified)
4. Calculate learner weight: **α = 0.5 × ln((1-ε)/ε)**
5. Update sample weights: w_new = w × e^α (misclassified), w × e^(-α) (correct)
6. Normalize weights
7. Repeat steps 2-6
8. **Final:** H(x) = sign(Σ αₜ × hₜ(x))

### Weight Update Formula — RAT LO!
```
Misclassified:  w_new = w × e^α
Correct:        w_new = w × e^(-α)
```

---

## 5. XGBoost — Extreme Gradient Boosting

**Definition:**
> Advanced gradient boosting that builds trees sequentially — each tree corrects the residuals (errors) of previous trees.

### Key Concepts

| Term | Matlab | Formula |
|------|--------|---------|
| **Residuals** | Actual minus Predicted | rᵢ = yᵢ - ŷᵢ |
| **Similarity Score** | How good a leaf is | (Σresiduals)² / count |
| **Gain** | Improvement from splitting | Left_score + Right_score - Parent_score |
| **Pruning** | Remove weak branches | If gain < threshold, prune |

### Process
1. Initial prediction = mean of all targets
2. Compute residuals (actual - predicted)
3. Build tree to predict residuals
4. Calculate gain for each possible split
5. Best split choose karo
6. New prediction = old + learning_rate × tree_output
7. Repeat

**💡 XGBoost vs AdaBoost:** AdaBoost sample weights change karta hai. XGBoost residuals (errors) directly predict karta hai — zyada efficient!

---

## 6. Evaluation Metrics — Confusion Matrix

### Confusion Matrix

| | Predicted Positive | Predicted Negative |
|--|-------------------|-------------------|
| **Actual Positive** | TP (True Positive) | FN (False Negative) |
| **Actual Negative** | FP (False Positive) | TN (True Negative) |

### Metrics — Formulas RAT LO!

| Metric | Formula | Kab Use Karein |
|--------|---------|----------------|
| **Accuracy** | (TP+TN) / Total | Balanced classes |
| **Precision** | TP / (TP+FP) | False positives costly (spam) |
| **Recall** | TP / (TP+FN) | False negatives costly (disease) |
| **F1-Score** | 2×P×R / (P+R) | Need balance between P and R |

### Numerical Example (Exam Important!)
100 patients, disease detection:
- TP=40, FP=10, FN=5, TN=45

| Metric | Calculation | Result |
|--------|------------|--------|
| Accuracy | (40+45)/100 | **85%** |
| Precision | 40/(40+10) | **80%** |
| Recall | 40/(40+5) | **88.9%** |
| F1 | 2×0.80×0.889/(0.80+0.889) | **84.2%** |

---

## 7. ROC Curve & AUC

**ROC Curve:** Plots TPR (Recall) vs FPR at various classification thresholds.

**AUC (Area Under Curve):**
- 0.5 = Random guessing 🎲
- 0.7-0.8 = Acceptable
- 0.8-0.9 = Excellent
- 1.0 = Perfect classifier 🎯

**Higher AUC = Better model!**

### Other Metrics

| Metric | Use |
|--------|-----|
| **Log Loss** | Measures prediction confidence — lower is better |
| **MSE/RMSE** | Regression error |
| **MAE** | Absolute regression error |
| **R²** | Regression variance explained |

---

## 8. Bagging vs Boosting — Quick Compare

| Aspect | Bagging | Boosting |
|--------|---------|----------|
| **Training** | Parallel (simultaneous) | Sequential (one by one) |
| **Samples** | Bootstrap (with replacement) | Weighted samples |
| **Reduces** | Variance (overfitting) | Bias (underfitting) |
| **Models** | Independent | Dependent |
| **Example** | Random Forest | AdaBoost, XGBoost |
| **Weight** | Equal for all models | Weighted by performance |

---

## 9. Exam-Ready Recap

### Must-Remember Formulas
```
Total Error:  Bias² + Variance + Irreducible
AdaBoost α:   0.5 × ln((1-ε)/ε)
Weight update: w × e^α (wrong), w × e^-α (correct)
Precision:    TP/(TP+FP)
Recall:       TP/(TP+FN)
F1:           2×P×R/(P+R)
```

### 5-Mark Answer Structure
**Definition → Types → Features → Advantages → Disadvantages → Challenges**

### Common Exam Questions
- Bias-Variance tradeoff explain karo
- Random Forest working + numerical example
- AdaBoost algorithm with weight update
- XGBoost vs AdaBoost comparison
- Confusion matrix se metrics calculate karo
- ROC-AUC explain karo
- Bagging vs Boosting comparison table

---

*End of Unit 6 — Ensemble Learning* 🎯
