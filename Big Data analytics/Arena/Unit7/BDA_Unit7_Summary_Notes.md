# BDA Unit 7 — Quick Summary Notes
## Machine Learning for Big Data

---

### 🔑 Key Definitions
- **Machine Learning:** AI ka branch jo computers ko data se patterns seekhne mein enable karta hai — without explicit programming
- **AI ⊃ ML ⊃ Deep Learning**, Big Data Analytics = complementary field

---

### 📋 ML Workflow (10 Steps)
Define Problem → Collect Data → Clean Data → Feature Selection → Split Data → Select Algorithm → Train Model → Evaluate → Deploy → Monitor

---

### 📊 4 Types of Machine Learning

| Type | Data | Goal | Example |
|------|------|------|---------|
| **Supervised** | Labeled | Predict target | Spam detection |
| **Unsupervised** | Unlabeled | Find patterns | Customer segmentation |
| **Semi-Supervised** | Mixed (small labeled + large unlabeled) | Improve accuracy | Medical image analysis |
| **Reinforcement** | Interaction with environment | Maximize reward | Robot navigation |

---

### 🧮 Important Formulas

**Linear Regression:**
```
y = β₀ + β₁x + ε
```
Example: Price = 500,000 + 4,000 × Area

**Logistic Regression:**
```
σ(z) = 1 / (1 + e^(-z))
```
Output: Probability (0 to 1), threshold se classify karo

---

### 🔤 Classification Algorithms (Supervised)
1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Naive Bayes
5. SVM (Support Vector Machine)
6. k-NN (k-Nearest Neighbors)
7. Neural Networks

### 🔢 Regression Algorithms (Supervised)
1. Linear Regression
2. Polynomial Regression
3. Decision Tree Regression
4. Random Forest Regression
5. Gradient Boosting Regression

### 📦 Clustering Algorithms (Unsupervised)
1. K-Means
2. Hierarchical Clustering
3. DBSCAN
4. Gaussian Mixture Models
5. Bisecting K-Means

---

### 🏗️ Decision Tree Structure
- **Root Node** → **Internal Decision Nodes** → **Branches** → **Leaf Nodes**
- Sequence of feature-based decisions

### 🌲 Random Forest
- Multiple decision trees combine karta hai
- Classification → Majority voting
- Regression → Averaging predictions
- Advantage: Strong performance, captures nonlinear patterns
- Limitation: Computation heavy, less interpretable

---

### 🏭 Industry Applications

| Industry | Application |
|----------|------------|
| Healthcare | Patient readmission risk prediction |
| Banking | Fraud/suspicious transaction detection |
| Retail | Customer segmentation |
| Education | Student academic support identification |
| Agriculture | Crop yield prediction |
| Manufacturing | Equipment failure prediction |

---

### ⚡ Reinforcement Learning Components
- **Agent** → Learner/Decision-maker
- **Environment** → System it interacts with
- **State** → Current situation
- **Action** → Agent's decision
- **Reward** → Feedback
- **Policy** → Strategy for selecting actions

---

### ✅ ML Characteristics
Data-driven | Adaptive | Predictive | Pattern-oriented | Automated | Evaluatable | Scalable

---

*Quick revision ready — Exam mein yahi aata hai!*
