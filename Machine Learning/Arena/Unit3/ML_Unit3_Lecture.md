# ML Unit 3 — Supervised Learning
## Complete Lecture Notes (Hinglish) | OLMCA602 | Week 3 + Week 4

---

## 1. Linear Regression Kya Hai?

**Definition:**
> Linear Regression is a supervised learning technique that predicts a continuous target y from one or more predictors x₁, x₂, …, xₙ using a linear equation.

**Simple matlab:** Jab tumhe koi **number predict karna ho** — jaise house price, exam score, temperature — toh Linear Regression use hota hai. Ye data mein ek straight line (ya plane) fit karta hai jo best predictions deta hai.

### Do Types Hote Hain

| Type | Formula | Matlab | Example |
|------|---------|--------|---------|
| **Simple** | y = mx + c | Sirf ek predictor x | Hours studied → Exam score |
| **Multiple** | y = β₀ + β₁x₁ + β₂x₂ + … + βₙxₙ | Do ya zyada predictors | Area + Location + Rooms → House price |

**💡 Learning Trick:** Simple = 1 x, Multiple = 2+ x. Formula mein jitne x utne β (coefficients).

### 5 Assumptions — Exam Mein Zaroor Aata Hai!

Yeh 5 assumptions yaad rakhna — direct 5-mark question aa sakta hai:

| # | Assumption | Simple Matlab |
|---|-----------|---------------|
| 1 | **Linearity** | X aur y ke beech straight-line relationship hona chahiye |
| 2 | **Independence** | Ek observation dusre se independent honi chahiye |
| 3 | **Homoscedasticity** | Residuals (errors) ka variance constant hona chahiye |
| 4 | **Normality** | Residuals normally distributed hone chahiye (bell curve) |
| 5 | **No multicollinearity** | Predictors aapas mein highly correlated nahi hone chahiye |

**💡 Yaad rakhne ka trick:** "**L**azy **I**ndians **H**ate **N**on-veg **M**ondays" — L-I-H-N-M = Linearity, Independence, Homoscedasticity, Normality, Multicollinearity (no).

### Evaluation Metrics — Model Kitna Achha Hai?

| Metric | Formula Concept | Kab Use Karein |
|--------|----------------|----------------|
| **MSE** (Mean Squared Error) | Errors ka square ka average | Large errors ko zyada penalise karna ho |
| **RMSE** (Root Mean Squared Error) | MSE ka square root | Original units mein error dekhna ho |
| **MAE** (Mean Absolute Error) | Absolute errors ka average | Outliers se affect nahi hona ho |
| **R²** (R-squared) | Kitna variance model explain karta hai | Overall fit check karna ho (0 se 1) |

**💡 R² trick:** R² = 0.85 matlab model 85% variance explain kar raha hai — achha model! R² = 0.3 matlab sirf 30% — kachra model.

---

## 2. Logistic Regression — Classification Ka Raja

**Definition:**
> Logistic Regression is a classification algorithm that estimates the probability of a categorical outcome using the sigmoid function.

**Linear Regression se farq:** Linear Regression number predict karta tha (jaise 900000 rupees), Logistic Regression **probability** predict karta hai (jaise 0.85 = 85% chance spam hai).

### Sigmoid Function — Formula RAT LO!

```
σ(z) = 1 / (1 + e^(-z))
```

**Matlab:** Koi bhi number lo — positive ya negative — sigmoid usko **0 se 1 ke beech** compress kar deta hai. Ye probability ban jata hai.

**Decision boundary:** 0.5
- σ(z) > 0.5 → Positive class (Spam, Disease Yes)
- σ(z) < 0.5 → Negative class (Not Spam, Disease No)

### Key Points

| Aspect | Detail |
|--------|--------|
| **Loss Function** | Cross-Entropy Loss (NOT MSE!) |
| **Parameter Estimation** | MLE — Maximum Likelihood Estimation |
| **Output** | Probability (0 to 1) |
| **Decision** | Threshold (usually 0.5) |

**💡 Exam tip:** "Logistic Regression mein MSE use nahi hota" — ye commonly pucha jata hai. MSE use hota hai Linear Regression mein, Logistic mein Cross-Entropy.

### Example: Spam Detection
- Email features: word frequency, sender, links
- Model computes σ(z) = 0.85
- 0.85 > 0.5 → **Classified as SPAM** ✅

---

## 3. Gradient Descent — Model Kaise Seekhta Hai?

**Definition:**
> Gradient Descent is an optimisation algorithm that minimises a loss function by iteratively moving in the direction of steepest descent — the negative gradient.

**Real-life example:** Socho pahad pe ho, thick fog mein, aur neeche valley mein jaana hai. Aankhon se dikhta nahi lekin pairon se slope feel hota hai. Har step mein sabse zyada neeche jaane wali direction mein chalo. Jab ground flat lage — valley floor pe pahunch gaye, minimum mil gaya! Yahi Gradient Descent karta hai.

### Update Rule — Ye Formula Yaad Rakho!

```
θ = θ - α × ∇J(θ)
```

- θ = parameter (weight)
- α = learning rate (step size)
- ∇J(θ) = gradient (slope/direction)

### 4 Steps

| Step | Action | Simple Matlab |
|------|--------|---------------|
| 1 | Define Loss Function | Error kaise measure karenge |
| 2 | Compute Gradient | Har parameter ka slope nikalo |
| 3 | Update Parameters | θ = θ - α × gradient |
| 4 | Repeat | Jab tak minimum na mil jaaye |

### Learning Rate (α) — Bahut Important!

| α Value | Kya Hoga |
|---------|----------|
| **Too large** | Overshoot karega — valley se bahar nikal jayega, diverge |
| **Too small** | Bahut slow — local minimum mein stuck ho jayega |
| **Just right** | Smooth convergence — seedha minimum pe pahunchega |

**💡 Trick:** α ko "Goldilocks parameter" bolo — na zyada bada, na zyada chota, bilkul sahi!

---

## 4. Gradient Descent ke 3 Variants

| Variant | Data Per Update | Speed | Stability | Kab Use Karein |
|---------|----------------|-------|-----------|----------------|
| **Batch GD** | Poora dataset | Slow ⚠️ | Very stable ✅ | Chota dataset |
| **SGD** | Sirf 1 sample | Fast 🚀 | Noisy ⚠️ | Bahut bada dataset |
| **Mini-Batch GD** | Chota batch (32-64) | Medium ⚡ | Balanced ✅ | **Most practical!** |

**💡 Exam comparison:** SGD noisy hai kyunki ek sample se direction galat ho sakti hai. Mini-batch best balance hai — fast bhi aur stable bhi.

---

## 5. Decision Tree Pruning — Overfitting Se Bacho!

**Problem:** Decision Tree bahut deep grow ho sakta hai — training data ko perfect yaad kar leta hai, lekin naye data pe fail ho jata hai. Isse **overfitting** kehte hain.

**Solution: Pruning** — tree ko chota karna taaki wo generalise kar sake.

### Do Types

| Type | Kab | Kaise | Methods |
|------|-----|-------|---------|
| **Pre-pruning** (Early Stopping) | Tree grow karte time | Splitting se pehle rok do | Max depth, min samples, max features, info gain threshold |
| **Post-pruning** | Tree pura grow hone ke baad | Branches remove karo | Cost Complexity Pruning, Reduced Error Pruning |

**💡 Analogy:** Pre-pruning = garden mein plant ko pehle se chota rakhna. Post-pruning = bada tree grow hone ke baad branches kaatna.

### Pre-pruning Criteria
- **Max depth:** Tree ki maximum depth set karo (jaise depth = 5)
- **Min samples:** Node mein minimum samples chahiye split ke liye
- **Info gain threshold:** Split tabhi karo jab information gain threshold se zyada ho

### Post-pruning Methods
- **Cost Complexity:** Complexity penalty lagao — simple tree prefer karo
- **Reduced Error:** Validation set pe check karo — branch hatao toh error kam hota hai ya nahi?

---

## 6. Naive Bayes Classifier — Probability Se Classification

**Definition:**
> Naive Bayes is a probability-based classification algorithm using Bayes' Theorem, assuming features are conditionally independent given the class.

**Simple matlab:** Bayes' Theorem use karke classify karta hai — "Given ye features hain, kis class mein hone ki probability zyada hai?"

### Bayes' Theorem — RAT LO!

```
P(C|X) = P(X|C) × P(C) / P(X)
```

| Term | Name | Matlab |
|------|------|--------|
| P(C) | **Prior** | Class ki pehle se probability (bina data dekhe) |
| P(X|C) | **Likelihood** | Class ke given features ki probability |
| P(X) | **Evidence** | Features ki overall probability |
| P(C|X) | **Posterior** | Final probability — yahi classify karega |

### "Naive" Kyun?
Kyunki ye **assume karta hai ki sab features independent hain** given the class. Real world mein ye mostly galat hota hai — lekin phir bhi Naive Bayes achha kaam karta hai! Isliye "naive" (bhola) kehte hain.

### 3 Types

| Type | Features | Example |
|------|----------|---------|
| **Gaussian NB** | Continuous (normal distribution) | Height, weight, temperature |
| **Multinomial NB** | Count/frequency data | **Text classification, spam detection** (most famous!) |
| **Bernoulli NB** | Binary (present/absent) | Word hai ya nahi document mein |

### Worked Example: Spam Detection
Training data: 5 emails with features (Free, Buy) and labels (Spam/Not)

**Step 1:** Priors — P(Spam) = 3/5 = 0.6, P(Not) = 2/5 = 0.4

**Step 2:** Likelihoods — P(Free|Spam), P(Buy|Spam), P(Free|Not), P(Buy|Not)

**Step 3:** New email "Free Buy" → calculate:
- P(Spam|Free,Buy) = P(Free|Spam) × P(Buy|Spam) × P(Spam) / P(Free,Buy)
- P(Not|Free,Buy) = P(Free|Not) × P(Buy|Not) × P(Not) / P(Free,Buy)

**Step 4:** Jo posterior bada ho → wo prediction!

**💡 Exam tip:** Numerical problem aaye toh step-by-step likhna — priors → likelihoods → posteriors → compare.

---

## 7. Quick Comparison — 4 Algorithms

| | Linear Reg | Logistic Reg | Decision Tree | Naive Bayes |
|--|-----------|-------------|---------------|-------------|
| **Task** | Continuous value | Probability (0-1) | Both | Classification |
| **Formula** | y = mx+c | σ(z) | Tree splits | Bayes Theorem |
| **Loss** | MSE | Cross-Entropy | Gini/Entropy | N/A |
| **Key Feature** | 5 assumptions | MLE, sigmoid | Pruning needed | Independence |
| **Best For** | Price, score prediction | Spam, disease | Interpretable rules | Text, fast classification |

---

## 8. Exam-Ready Recap

### Formulas (RAT LO!)
```
Linear:    y = mx + c
Logistic:  σ(z) = 1 / (1 + e^(-z))
GD:        θ = θ - α × ∇J(θ)
Bayes:     P(C|X) = P(X|C) × P(C) / P(X)
```

### 5-Mark Answer Structure
**Definition → Types → Features → Advantages → Disadvantages → Challenges**

### Common Exam Questions
- LR assumptions (5) — definition + explanation
- Logistic vs Linear Regression — comparison table
- Gradient Descent steps + learning rate effect
- SGD vs Batch vs Mini-Batch — comparison
- Pre vs Post pruning — difference with examples
- Naive Bayes numerical — Bayes theorem apply karo

---

*End of Unit 3 — Supervised Learning* 🎯
