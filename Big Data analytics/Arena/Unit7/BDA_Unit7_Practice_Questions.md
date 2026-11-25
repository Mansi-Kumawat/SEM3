# BDA Unit 7 — Practice Questions
## Machine Learning for Big Data

---

## 📝 Part A: Multiple Choice Questions (1 Mark Each)

**Q1.** Machine Learning is a branch of:
- (A) Database Management
- (B) Artificial Intelligence
- (C) Operating Systems
- (D) Computer Networks

**Answer: (B) Artificial Intelligence**

---

**Q2.** Which type of learning uses labeled data?
- (A) Unsupervised Learning
- (B) Semi-Supervised Learning
- (C) Supervised Learning
- (D) Reinforcement Learning

**Answer: (C) Supervised Learning**

---

**Q3.** Which of the following is a clustering algorithm?
- (A) Linear Regression
- (B) Decision Tree
- (C) K-Means
- (D) Logistic Regression

**Answer: (C) K-Means**

---

**Q4.** The formula y = β₀ + β₁x + ε belongs to:
- (A) Logistic Regression
- (B) Linear Regression
- (C) Polynomial Regression
- (D) Decision Tree

**Answer: (B) Linear Regression**

---

**Q5.** In Reinforcement Learning, the feedback given to the agent is called:
- (A) Label
- (B) Cluster
- (C) Reward
- (D) Feature

**Answer: (C) Reward**

---

**Q6.** Which algorithm combines multiple decision trees?
- (A) SVM
- (B) k-NN
- (C) Random Forest
- (D) Naive Bayes

**Answer: (C) Random Forest**

---

**Q7.** Logistic Regression is used for:
- (A) Predicting numerical values
- (B) Predicting probability of categorical outcome
- (C) Clustering data
- (D) Dimensionality reduction

**Answer: (B) Predicting probability of categorical outcome**

---

**Q8.** Which is NOT a step in ML Workflow?
- (A) Define the problem
- (B) Collect data
- (C) Write SQL queries
- (D) Train the model

**Answer: (C) Write SQL queries**

---

**Q9.** Semi-Supervised Learning combines:
- (A) Only labeled data
- (B) Only unlabeled data
- (C) Small labeled + large unlabeled data
- (D) No data at all

**Answer: (C) Small labeled + large unlabeled data**

---

**Q10.** The logistic function formula is:
- (A) y = mx + c
- (B) σ(z) = 1 / (1 + e^(-z))
- (C) y = β₀ + β₁x
- (D) y = ax² + bx + c

**Answer: (B) σ(z) = 1 / (1 + e^(-z))**

---

## 📝 Part B: Short Answer Questions (2 Marks Each)

**Q1.** What is Machine Learning? How is it different from traditional programming?

**Answer:** Machine Learning is a branch of AI that enables computers to learn patterns from data without explicitly programming every decision rule. Unlike traditional programming where rules are manually defined, ML algorithms construct models from training data and use them to make predictions on new data.

---

**Q2.** Differentiate between Supervised and Unsupervised Learning.

**Answer:**
| Feature | Supervised Learning | Unsupervised Learning |
|---------|-------------------|---------------------|
| Data | Labeled (input + target) | Unlabeled (only input) |
| Goal | Predict target/outcome | Find hidden patterns |
| Tasks | Classification, Regression | Clustering, Dimensionality Reduction |
| Example | Spam detection (spam/not spam) | Customer segmentation (groups) |

---

**Q3.** What is Reinforcement Learning? Name its key components.

**Answer:** Reinforcement Learning trains an agent to select actions through interaction with an environment to maximize cumulative reward. Key components: (1) Agent — the learner, (2) Environment — the system, (3) State — current situation, (4) Action — agent's decision, (5) Reward — feedback, (6) Policy — strategy for action selection.

---

**Q4.** Write the Linear Regression formula and explain each term.

**Answer:** Formula: y = β₀ + β₁x + ε
- y = Target value (dependent variable)
- x = Input feature (independent variable)
- β₀ = Intercept (value of y when x = 0)
- β₁ = Regression coefficient (slope of the line)
- ε = Error term (difference between actual and predicted value)

---

**Q5.** What is Random Forest? How does it work for classification?

**Answer:** Random Forest combines multiple decision trees into an ensemble. Working: (1) Generate bootstrap samples from training data, (2) Train a decision tree on each sample, (3) Consider randomly selected features at splitting stages, (4) For classification — use majority voting from all trees to determine final class. It provides strong predictive performance and reduces overfitting compared to single decision tree.

---

## 📝 Part C: Long Answer Questions (5 Marks Each)

**Q1.** Explain the Machine Learning Workflow with an example.

**Answer:**
The ML Workflow has 10 steps:

1. **Define the problem:** Clearly state what needs to be predicted or classified.
2. **Collect relevant data:** Gather data from databases, APIs, files, etc.
3. **Clean and preprocess data:** Handle missing values, remove outliers, normalize data.
4. **Select useful features:** Choose the most relevant features (feature engineering).
5. **Split data:** Divide into training set (model learns), validation set (tune hyperparameters), test set (evaluate final model).
6. **Select algorithm:** Choose based on problem type — classification, regression, clustering.
7. **Train the model:** Feed training data to algorithm, it learns patterns.
8. **Evaluate performance:** Test on unseen data using metrics like accuracy, precision, RMSE.
9. **Deploy the model:** Integrate model into production system.
10. **Monitor and update:** Continuously track performance, retrain with new data.

**Example — House Price Prediction:**
- Problem: Predict house prices
- Features: Area, Location, Rooms, Age
- Algorithm: Linear Regression → Price = 500,000 + 4,000 × Area
- If Area = 100 sq.m → Predicted Price = 900,000

---

**Q2.** Explain Classification and Regression with algorithms and examples.

**Answer:**

**Classification** (predicts a discrete category):
- Uses labeled training data to learn decision boundaries
- Algorithms: Logistic Regression, Decision Tree, Random Forest, Naive Bayes, SVM, k-NN, Neural Networks
- Example: Loan classification — Input features: income, debt, credit history, employment duration → Output: Low-risk or High-risk
- Applications: Spam detection, Disease screening, Fraud detection, Sentiment analysis

**Regression** (predicts a continuous numerical value):
- Models relationship between input features and continuous target
- Algorithms: Linear Regression (y=β₀+β₁x+ε), Polynomial Regression, Decision Tree Regression, Random Forest Regression, Gradient Boosting
- Example: Electricity demand forecasting — Input: historical consumption, temperature, time of day, day of week → Output: Predicted demand in megawatts

**Key Difference:** Classification = category (discrete), Regression = number (continuous)

---

**Q3.** What are the different types of Machine Learning? Explain each with examples.

**Answer:**

**1. Supervised Learning:**
- Learns from labeled data (input features + known targets)
- Tasks: Classification (predict category), Regression (predict number)
- Example: Student performance prediction — attendance, marks → pass/fail or score

**2. Unsupervised Learning:**
- Uses unlabeled data, finds hidden structure/patterns
- Techniques: Clustering (K-Means, DBSCAN), Dimensionality Reduction (PCA), Association Rule Mining, Anomaly Detection
- Example: Customer segmentation — groups customers by purchasing behavior

**3. Semi-Supervised Learning:**
- Combines small labeled data with large unlabeled data
- Useful when labeling is expensive or needs expert knowledge
- Example: Medical image classification — 1000 labeled + 50000 unlabeled images

**4. Reinforcement Learning:**
- Agent learns actions through environment interaction
- Components: Agent, Environment, State, Action, Reward, Policy
- Example: Warehouse robot — learns optimal path by receiving rewards for reaching destination

---

**Q4.** Explain Decision Tree and Random Forest with their advantages and limitations.

**Answer:**

**Decision Tree:**
- Tree-like structure: Root Node → Internal Decision Nodes → Branches → Leaf Nodes
- Predicts outcome through sequence of feature-based decisions (like a flowchart)
- Each internal node tests a feature, each branch represents decision, each leaf represents outcome
- Used for both classification and regression

**Random Forest:**
- Ensemble method combining multiple decision trees
- Working Process:
  1. Generate bootstrap samples from training data
  2. Train a decision tree on each sample
  3. Consider randomly selected features at splitting stages
  4. Combine predictions — majority voting (classification) or averaging (regression)

**Advantages:**
- Strong predictive performance
- Captures nonlinear relationships
- Reduces overfitting (less dependence on single tree)
- Handles large datasets well

**Limitations:**
- Requires more computation than a single tree
- Combined model is less interpretable than single decision tree
- Slower prediction time for large forests

---

**Q5.** Discuss Machine Learning applications across different industries.

**Answer:**

| Industry | Application | Description |
|----------|-----------|-------------|
| **Healthcare** | Risk Prediction | Estimating patient readmission risk, disease diagnosis from medical images |
| **Banking** | Fraud Detection | Identifying suspicious transactions using classification algorithms |
| **Retail** | Customer Segmentation | Grouping customers by purchasing behavior using clustering |
| **Education** | Student Analytics | Identifying students needing academic support |
| **Agriculture** | Crop Yield Prediction | Predicting harvest based on weather and soil data |
| **Manufacturing** | Equipment Failure | Predicting maintenance needs using sensor data |

**Other Applications:**
- **Spam Detection:** Classification — email features → spam/not spam
- **Disease Screening:** Classification — medical tests → disease/no disease
- **Sentiment Analysis:** Classification — text → positive/negative/neutral
- **Recommendation Systems:** Clustering + Association — product recommendations

ML is now used in virtually every industry to automate decision-making, discover patterns, and improve efficiency with big data.

---

*Practice makes perfect — All the best for your exam!*
