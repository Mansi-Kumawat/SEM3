# ML Unit 6 — Practice Questions
## Ensemble Learning (Week 9 + Week 10)

---

## Part A: Multiple Choice (1 Mark)

**Q1.** Total Error equals: (A) Bias+Variance (B) Bias²+Variance+Irreducible (C) Bias×Variance (D) Only Bias
**Answer: (B)**

**Q2.** Random Forest uses which technique? (A) Boosting (B) Bagging (C) Stacking (D) Voting
**Answer: (B)**

**Q3.** AdaBoost α formula: (A) 0.5×ln((1-ε)/ε) (B) ln(ε) (C) ε² (D) 1/ε
**Answer: (A)**

**Q4.** XGBoost corrects: (A) Weights (B) Residuals (C) Features (D) Labels
**Answer: (B)**

**Q5.** Precision = TP/(TP+FP). When is it important? (A) FN costly (B) FP costly (C) Both equal (D) Neither
**Answer: (B)**

**Q6.** AUC = 0.5 means: (A) Perfect (B) Random (C) Bad (D) Excellent
**Answer: (B)**

**Q7.** Bootstrap coverage is approximately: (A) 50% (B) 63.2% (C) 75% (D) 100%
**Answer: (B)**

**Q8.** F1-Score = 2×P×R/(P+R). If P=0.8, R=0.8: (A) 0.64 (B) 0.80 (C) 1.60 (D) 0.40
**Answer: (B)**

**Q9.** Which reduces variance? (A) Boosting (B) Bagging (C) Both (D) Neither
**Answer: (B)**

**Q10.** In confusion matrix, FN means: (A) Correctly positive (B) Wrongly positive (C) Wrongly negative (D) Correctly negative
**Answer: (C)**

---

## Part B: Short Answer (2 Marks)

**Q1.** Differentiate Bagging and Boosting.
**Answer:** Bagging: parallel, bootstrap samples, reduces variance, Random Forest. Boosting: sequential, weights hard examples, reduces bias, AdaBoost/XGBoost.

**Q2.** Write AdaBoost α formula and explain.
**Answer:** α = 0.5 × ln((1-ε)/ε). Where ε = weighted error rate. Higher accuracy → higher α → more weight in final vote. If ε=0.5 (random), α=0.

**Q3.** Calculate Recall: TP=80, FN=20.
**Answer:** Recall = TP/(TP+FN) = 80/(80+20) = 80/100 = 0.80 or 80%.

**Q4.** What is bootstrap sampling?
**Answer:** Random sampling WITH replacement from training data. Each bootstrap sample has ~63.2% unique samples. Remaining 36.8% are OOB (Out-of-Bag) — used for validation.

---

## Part C: Descriptive (5 Marks)

**Q1.** Explain Random Forest with working and advantages.

**Answer Structure:**
**Definition:** Ensemble of decision trees using bootstrap samples and random features.
**Working:** Generate bootstrap samples → Train tree on each → Random features at splits → Majority voting/averaging.
**Key:** Bootstrap coverage ~63.2%, OOB for validation, no pruning needed.
**Advantages:** Handles overfitting, works with high dimensions, feature importance, robust.
**Disadvantages:** Less interpretable, slower prediction, memory intensive.
**Challenges:** Choosing number of trees, feature subset size, correlation between trees.

**Q2.** Explain Confusion Matrix with metrics and a numerical example.

**Answer Structure:**
**Definition:** Table showing TP, FP, FN, TN for classification evaluation.
**Matrix layout:** Actual vs Predicted, 4 cells.
**Metrics:** Accuracy=(TP+TN)/Total, Precision=TP/(TP+FP), Recall=TP/(TP+FN), F1=2PR/(P+R).
**Numerical:** 100 patients: TP=40, FP=10, FN=5, TN=45. Accuracy=85%, Precision=80%, Recall=88.9%, F1=84.2%.
**When to use:** Precision for costly FP, Recall for costly FN, F1 for balance.
**Advantages:** Complete picture, multiple metrics, threshold-independent.
**Challenges:** Imbalanced classes, choosing right metric, threshold selection.

---

*Practice makes perfect!* 🎯
