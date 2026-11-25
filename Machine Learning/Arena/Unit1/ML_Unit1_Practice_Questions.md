# ML Unit 1 — Practice Questions
## Introduction to Machine Learning

---

## Part A: Multiple Choice (1 Mark Each)

**Q1.** Which of the following best defines Machine Learning?
- (A) Explicit programming of rules
- (B) Learning patterns from data without explicit programming
- (C) Storing large amounts of data
- (D) Data visualisation

**Answer: (B)**

---

**Q2.** Supervised learning differs from unsupervised learning mainly because supervised learning:
- (A) Uses clustering techniques
- (B) Uses unlabelled data
- (C) Uses labelled training data
- (D) Does not use training data

**Answer: (C)**

---

**Q3.** The three pillars of Machine Learning are:
- (A) Data, Hardware, Model
- (B) Data, Algorithm, Model
- (C) Input, Process, Output
- (D) Training, Testing, Validation

**Answer: (B)**

---

**Q4.** Which type of learning uses reward and punishment to train models?
- (A) Supervised learning
- (B) Unsupervised learning
- (C) Reinforcement learning
- (D) Semi-supervised learning

**Answer: (C)**

---

**Q5.** In PAC Learning, the criterion P(err_D(h) ≤ ε) ≥ 1 − δ means:
- (A) Error is exactly zero
- (B) With high probability, error is at most ε
- (C) The model is 100% accurate
- (D) Training data is infinite

**Answer: (B)**

---

**Q6.** Which metric is used to measure the capacity of hypothesis class H?
- (A) Sample Complexity
- (B) VC Dimension
- (C) Loss Function
- (D) Learning Rate

**Answer: (B)**

---

**Q7.** In traditional programming, the flow is:
- (A) Data + Answers → Rules
- (B) Rules + Data → Answers
- (C) Model + Data → Answers
- (D) Algorithm + Rules → Data

**Answer: (B)**

---

**Q8.** Which is NOT a step in the ML Model Development pipeline?
- (A) Problem Definition
- (B) Data Collection
- (C) Writing SQL queries
- (D) Model Deployment

**Answer: (C)**

---

**Q9.** PAC Learning assumes data is:
- (A) Sequentially dependent
- (B) i.i.d. (independent and identically distributed)
- (C) Always labelled
- (D) From a single source

**Answer: (B)**

---

**Q10.** Which emerging type of learning transfers knowledge from one task to another?
- (A) Self-Supervised Learning
- (B) Online Learning
- (C) Transfer Learning
- (D) Semi-Supervised Learning

**Answer: (C)**

---

## Part B: Short Answer (2 Marks Each)

**Q1.** Differentiate between Supervised and Unsupervised Learning.

**Answer:**
| Feature | Supervised | Unsupervised |
|---------|-----------|-------------|
| Data | Labelled (input + output known) | Unlabelled (only input) |
| Goal | Predict output | Find hidden patterns |
| Tasks | Classification, Regression | Clustering, Dimensionality Reduction |
| Evaluation | Easier (ground truth available) | Harder (no ground truth) |

---

**Q2.** What is the formal model in Machine Learning? List its key components.

**Answer:**
The formal model provides a mathematical framework to define and analyse ML processes. Key components:
1. Instance Space (X) — all possible inputs
2. Label Space (Y) — all possible outputs
3. Hypothesis Space (H) — functions algorithm considers
4. Target Function (f: X→Y) — unknown true mapping
5. Training Data (S) — finite labelled samples
6. Learning Algorithm (A) — selects hypothesis from H
7. Loss Function — measures prediction error
8. Generalisation — performing well on unseen data

---

**Q3.** Explain the PAC Learning criterion with its formula.

**Answer:**
PAC (Probably Approximately Correct) criterion: P(err_D(h) ≤ ε) ≥ 1 − δ

- "Approximately": err_D(h) ≤ ε — hypothesis is within ε error tolerance
- "Probably": Probability ≥ 1−δ — high confidence level
- Sample size m grows polynomially in 1/ε, 1/δ, and complexity of H

---

**Q4.** List the 12 steps of ML Model Development pipeline.

**Answer:**
1. Problem Definition
2. Data Collection
3. Data Preprocessing
4. EDA (Exploratory Data Analysis)
5. Feature Engineering
6. Model Selection
7. Model Training
8. Model Evaluation
9. Hyperparameter Tuning
10. Model Deployment
11. Monitoring & Maintenance
12. Documentation & Communication

---

**Q5.** What is the VC Dimension? Why is it important?

**Answer:**
VC Dimension (Vapnik-Chervonenkis Dimension) measures the capacity/complexity of hypothesis class H. Higher VC dimension means more expressive hypothesis class, but it requires more training data to achieve PAC learning. It's important because it quantifies how complex a model can be relative to available data — directly impacting generalisation ability.

---

## Part C: Descriptive (5 Marks Each — Professor's Format)

**Q1.** Define Machine Learning. Explain the types of Machine Learning with examples.

**Answer Structure:**

**Definition:**
Machine Learning is a branch of Artificial Intelligence that focuses on enabling systems to learn and make decisions or predictions without being explicitly programmed.

**Types:**

1. **Supervised Learning** — Learns from labelled data
   - Regression: House price prediction
   - Classification: Spam detection

2. **Unsupervised Learning** — Finds patterns in unlabelled data
   - Clustering: Customer segmentation
   - Dimensionality Reduction: PCA

3. **Reinforcement Learning** — Agent learns by trial and error
   - Game playing, robot navigation

4. **Emerging Types:**
   - Self-Supervised, Transfer, Semi-Supervised, Online Learning

**Features:** Data-driven, adaptive, predictive, pattern-oriented

**Advantages:** Automates decision-making, handles large data, discovers hidden patterns

**Disadvantages:** Requires large data, computationally expensive, can be biased

**Challenges:** Data quality, overfitting, interpretability, ethical concerns

---

**Q2.** Explain the Formal Model in Machine Learning with its key components.

**Answer Structure:**

**Definition:**
A formal model provides a mathematical framework to define and analyse machine learning processes, specifying the structure, assumptions, and properties of the learning problem.

**Key Components:**
1. Instance Space (X): Set of all possible inputs
2. Label Space (Y): Set of all possible outputs
3. Hypothesis Space (H): Set of all functions algorithm may consider
4. Target Function (f): Unknown true mapping f: X→Y
5. Training Data (S): Finite labelled sample
6. Learning Algorithm (A): Procedure selecting h∈H
7. Loss Function L(h(x),y): Error measure
8. Generalisation: Performing well on unseen data

**Features:** Mathematical rigor, abstraction, general applicability

**Advantages:** Provides theoretical foundation, enables analysis, guides algorithm design

**Disadvantages:** May be too abstract for practical use, assumes ideal conditions

**Challenges:** Bridging theory and practice, choosing appropriate formalisation

---

**Q3.** What is PAC Learning? Explain its core concepts, advantages, and limitations.

**Answer Structure:**

**Definition:**
PAC (Probably Approximately Correct) Learning is a theoretical framework introduced by Leslie Valiant in 1984 to study the feasibility of learning in the presence of uncertainty.

**Core Concepts:**
- Instance Space (X), Target Concept (c∈C), Hypothesis Class (H)
- Distribution (D), Training Sample (S) — i.i.d. from D
- Error: err_D(h) = P[h(x) ≠ c(x)]
- PAC Criterion: P(err_D(h) ≤ ε) ≥ 1 − δ

**Key Elements:**
1. Sample Complexity — training examples needed (depends on ε, 1-δ, |H|)
2. VC Dimension — measures H complexity
3. Efficient Learnability — polynomial-time algorithm

**Advantages:**
- Rigorous mathematical foundation
- Quantifies trade-offs
- Defines learnability conditions

**Limitations:**
- Assumes i.i.d. data (not always realistic)
- Requires hypothesis close to true concept (may not exist)

**Challenges:**
- Real-world data rarely i.i.d.
- Concept class may not contain true function
- Computational complexity may be impractical

---

*Practice makes perfect! Attempt all questions before checking answers.* 🎯
