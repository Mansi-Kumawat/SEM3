# ML Unit 1 — Introduction to Machine Learning
## Complete Lecture Notes | OLMCA602 | Week 1

---

## 🎯 Learning Objectives
By the end of this unit, you should be able to:
1. Define Machine Learning and explain its three pillars
2. Differentiate supervised, unsupervised, reinforcement, and emerging learning types
3. Outline the 12 stages of ML model development
4. Describe the formal model: instance space, hypothesis space, target, loss
5. Interpret PAC learning, sample complexity, and VC dimension

---

## 1. What is Machine Learning?

**Definition:**
> Machine Learning is a branch of Artificial Intelligence (AI) that focuses on enabling systems to learn and make decisions or predictions without being explicitly programmed. It involves the development of algorithms and statistical models that allow computers to identify patterns in data.

**Matlab simple bhasha mein:** Pehle ke zamane mein computer ko har kaam ke liye rules manually likhne padte the. Lekin ML mein, hum computer ko data dete hain, answers dete hain, aur computer khud se rules seekh leta hai.

### Traditional Programming vs Machine Learning

| Aspect | Traditional Programming | Machine Learning |
|--------|------------------------|-----------------|
| **Input** | Rules + Data | Data + Answers |
| **Output** | Answers | Rules |
| **Process** | Programmer writes logic | Algorithm discovers logic |
| **Example** | If-else spam filter | Learns spam patterns from examples |

**Core idea:** Learn patterns from data rather than following handwritten rules.

---

## 2. The Three Pillars of ML

### 📊 Data (Foundational Element)
- Structured: Tables, databases, spreadsheets
- Unstructured: Images, text, videos, audio
- The raw material that ML works with

### 🔢 Algorithms (Mathematical Methods)
- Process data and learn patterns
- Examples: Linear Regression, Decision Trees, Neural Networks
- The "engine" that transforms data into knowledge

### 🤖 Model (The Result)
- Output of applying algorithms to data
- Used to make predictions or decisions on new data
- Example: A spam detection model that classifies emails

**Flow:** Data → Algorithm → Model → Predictions

---

## 3. ML Applications Across Domains

| Domain | Application |
|--------|------------|
| **Healthcare** | Diagnosis, medical imaging, risk prediction |
| **Finance** | Fraud detection, forecasting, credit scoring |
| **Marketing** | Segmentation, recommendation, targeting |
| **Robotics** | Perception, control, autonomous navigation |
| **NLP** | Translation, chatbots, sentiment analysis |
| **Computer Vision** | Object detection, image classification |

---

## 4. Types of Machine Learning

### 4.1 Supervised Learning

**Definition:**
> The model is trained on a labelled dataset where both the input (features) and output (labels/targets) are known. The goal is to learn a mapping function from inputs to outputs and use it to predict on new, unseen data.

**Simple matlab:** Jaise teacher student ko questions aur answers dono deta hai — student seekh jata hai.

**Formula:** y = f(x)
- x = input features (known)
- y = output label (known in training)
- f = the function the model learns

**Two Task Types:**

| Type | Predicts | Examples |
|------|----------|---------|
| **Regression** | Continuous value | House price, stock forecasting, temperature |
| **Classification** | Discrete categories | Spam detection, disease diagnosis, cat/dog |

**Common Algorithms:**
- Linear Regression
- Logistic Regression
- Support Vector Machines (SVM)
- Decision Trees
- Random Forests
- Neural Networks

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| Input (Features) | Variables used for predictions | House size, bedrooms, location |
| Output (Labels) | Known target values | House price |
| Training Data | Collection of input-output pairs | Historical houses with prices |
| Model | Function mapping inputs to outputs | y = f(x) |
| Loss Function | Measures prediction error | MSE (regression), Cross-Entropy (classification) |
| Optimisation | Adjusts parameters to minimize loss | Gradient Descent |

---

### 4.2 Unsupervised Learning

**Definition:**
> Unsupervised learning deals with unlabelled data, where the system tries to learn patterns and structures from the input data without predefined labels or target outputs.

**Simple matlab:** Bina teacher ke padhai — student khud se patterns dhundhta hai data mein.

**Key Features:**
- Does NOT require labelled data
- Focuses on discovering hidden patterns, structures, or relationships
- Commonly used for clustering, dimensionality reduction, and association rule mining

**Techniques:**

| Technique | What it does | Algorithm Examples |
|-----------|-------------|-------------------|
| **Clustering** | Groups similar data points | K-Means, Hierarchical, DBSCAN |
| **Dimensionality Reduction** | Fewer features, same meaning | PCA, t-SNE, Autoencoders |
| **Anomaly Detection** | Flags unusual data points | Isolation Forest, GMM |

**Key Components:**

| Component | Description |
|-----------|-------------|
| Input Data (Features) | Unlabelled variables (age, income, spending) |
| Output (Patterns/Structures) | Clusters, anomalies, reduced dimensions |
| Objective Function | Evaluates how well model identifies patterns |
| Distance/Similarity Metrics | Euclidean Distance, Cosine Similarity |

---

### 4.3 Reinforcement Learning

**Definition:**
> An agent learns by trial and error, maximising a reward from its environment.

**Simple matlab:** Jaise bachha girke seekhta hai — galat kiya toh gira (negative reward), sahi kiya toh aage badha (positive reward).

**Components:**

| Component | Description |
|-----------|-------------|
| **Agent** | The learner/decision-maker |
| **Environment** | System it interacts with |
| **State** | Current situation |
| **Action** | Decision taken by agent |
| **Reward** | Feedback signal |
| **Policy** | Strategy for selecting actions |

**Examples:** Game playing (Chess, Go), Robot navigation, Self-driving cars

---

### 4.4 Emerging Types of Learning

| Type | Description | Example |
|------|-------------|---------|
| **Self-Supervised Learning** | Creates supervisory signals from unlabelled data itself | Predicting missing words in text |
| **Transfer Learning** | Knowledge from one task transferred to another | Pre-trained image models → new task |
| **Semi-Supervised Learning** | Combines small labelled + large unlabelled data | Medical image classification |
| **Online Learning** | Model updates continuously with new data | Stock market prediction |

---

## 5. ML Model Development — 12-Step Pipeline

**Yeh bahut important hai exam ke liye — sequence mein yaad rakhna!**

| Step | Activity | Description |
|------|----------|-------------|
| **1** | Problem Definition | Clearly define what needs to be solved |
| **2** | Data Collection | Gather relevant data from sources |
| **3** | Data Preprocessing | Clean data, handle missing values, outliers |
| **4** | EDA (Exploratory Data Analysis) | Visually understand the data |
| **5** | Feature Engineering | Select and create important features |
| **6** | Model Selection | Choose appropriate algorithm |
| **7** | Model Training | Fit model on training data |
| **8** | Model Evaluation | Test on unseen data using metrics |
| **9** | Hyperparameter Tuning | Optimise model parameters |
| **10** | Model Deployment | Integrate into production system |
| **11** | Monitoring & Maintenance | Continuously track performance |
| **12** | Documentation & Communication | Record process, share with stakeholders |

---

## 6. Supervised vs Unsupervised Learning — Detailed Comparison

| Aspect | Supervised Learning | Unsupervised Learning |
|--------|-------------------|---------------------|
| **Data Requirement** | Labelled data (costly, time-consuming) | Unlabelled data (flexible, scalable) |
| **Objective** | Predict output for new inputs | Discover hidden patterns |
| **Learning Process** | Minimises error using labels as feedback | Finds patterns, no explicit feedback |
| **Output** | Labelled predictions (category/value) | Clusters or reduced features |
| **Algorithms** | Linear Regression, SVM, Neural Networks | K-Means, PCA, Autoencoders |
| **Applications** | Fraud detection, medical diagnosis, stock prediction | Market segmentation, anomaly detection |
| **Evaluation** | Easier to validate (ground truth available) | Harder to interpret and validate |
| **Complexity** | Simpler to train (labels guide learning) | Harder — no ground truth to guide |

---

## 7. Formal Model in Machine Learning

**Definition:**
> A formal model provides a mathematical framework to define and analyse machine learning processes. It specifies the structure, assumptions, and properties of the learning problem and algorithm.

### Key Components

| Component | Symbol | Description | Example |
|-----------|--------|-------------|---------|
| **Instance Space** | X | Set of all possible inputs | All possible pixel arrays for images |
| **Label Space** | Y | Set of all possible outputs | Y={0,1} binary, Y=ℝ regression |
| **Hypothesis Space** | H | All functions the algorithm may consider | Linear classifiers, trees, nets |
| **Target Function** | f | Unknown true mapping f: X→Y | The "real" rule we want to find |
| **Training Data** | S | Finite labelled sample | S={(x₁,y₁),…,(xₘ,yₘ)} |
| **Learning Algorithm** | A | Procedure selecting h∈H from data | Gradient Descent, Tree construction |
| **Loss Function** | L(h(x),y) | Error between prediction and truth | MSE, Cross-Entropy |
| **Generalisation** | — | Performing well on unseen data | The REAL goal of learning |

---

## 8. PAC Learning (Probably Approximately Correct)

**Definition:**
> PAC Learning is a theoretical framework introduced by Leslie Valiant in 1984 to study the feasibility of learning in the presence of uncertainty.

### Core Concepts

| Concept | Description |
|---------|-------------|
| **Instance Space (X)** | Finite or infinite set of all possible inputs |
| **Target Concept (c)** | True function to be learned, c ∈ C (concept class) |
| **Hypothesis Class (H)** | Functions used to approximate c |
| **Distribution (D)** | Probability distribution over X — how data is sampled |
| **Training Sample (S)** | Labelled examples drawn i.i.d. from D |
| **Error** | err_D(h) = P[h(x) ≠ c(x)] on a random instance |

### The PAC Criterion

**Formula (exam mein zaroor likhna):**

```
P(err_D(h) ≤ ε) ≥ 1 − δ
```

- **Approximately:** err_D(h) ≤ ε — hypothesis is within ε of correct
- **Probably:** Holds with probability ≥ 1 − δ — high confidence
- **Sample size m:** Grows polynomially in 1/ε, 1/δ, and complexity of H

### Key Elements

**1. Sample Complexity:**
- Number of training examples needed to meet PAC criterion
- Depends on: error tolerance (ε), confidence (1−δ), size of hypothesis class |H|
- Formula: m grows polynomially in 1/ε, 1/δ, |H|

**2. VC Dimension (Vapnik-Chervonenkis Dimension):**
- Measures capacity/complexity of hypothesis class H
- Higher VC dimension = more expressive class
- But requires more data to achieve PAC learning

**3. Efficient Learnability:**
- Concept class C is efficiently PAC-learnable if polynomial-time algorithm satisfies PAC criterion

### Advantages of PAC Learning
- Provides rigorous mathematical foundation for ML
- Quantifies trade-off: training data size vs model complexity vs generalisation error
- Defines when learning is theoretically possible

### Limitations of PAC Learning
- Assumes i.i.d. data — may not hold in real-world settings
- Relies on hypothesis h∈H close to true concept c — may not exist

---

## 9. Formal Model vs PAC Learning Comparison

| Aspect | Formal Model | PAC Learning |
|--------|-------------|-------------|
| **Scope** | General framework for learning tasks | Feasibility of learning under uncertainty |
| **Goal** | Define components of a learning system | Quantify conditions for successful learning |
| **Data Requirements** | Depends on problem and algorithm | Requires i.i.d. samples from distribution |
| **Complexity Measure** | Loss function, hypothesis-space complexity | VC dimension, sample complexity |

---

## 10. Exam-Ready Recap

### Must-Remember Definitions (English)
1. **Machine Learning:** Branch of AI enabling systems to learn without explicit programming
2. **Supervised Learning:** Learns from labelled data (inputs + known outputs)
3. **Unsupervised Learning:** Finds hidden structure in unlabelled data
4. **Reinforcement Learning:** Agent learns by trial and error, maximising reward
5. **Formal Model:** Mathematical framework defining ML structure and assumptions
6. **PAC Learning:** Framework studying feasibility of learning under uncertainty

### Must-Remember Formulas
- **Supervised Learning:** y = f(x)
- **PAC Criterion:** P(err_D(h) ≤ ε) ≥ 1 − δ

### 5-Mark Answer Structure
**Definition → Types → Features → Advantages → Disadvantages → Challenges**

---

*End of Unit 1 — Introduction to Machine Learning*
