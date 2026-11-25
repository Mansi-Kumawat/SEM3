# ML Unit 2 — Data Pre-processing
## Complete Lecture Notes | OLMCA602 | Week 2

---

## 🎯 Learning Objectives
1. Explain why data pre-processing is necessary
2. Describe three types of feature selection methods
3. Understand PCA, LDA, and other dimensionality reduction techniques
4. Apply feature selection to real scenarios

---

## 1. Why Data Preprocessing?

**Definition:**
> Data preprocessing transforms raw data into a clean, consistent format suitable for ML algorithms.

**Matlab simple bhasha mein:** Real-world data kabhi bhi seedha ML model mein daalne ke layak nahi hota. Data mein noise hota hai, missing values hote hain, inconsistent formats hote hain. Preprocessing ka kaam hai is raw data ko clean, consistent, aur ML-ready banana.

### Why Needed?
| Problem | Impact |
|---------|--------|
| Noisy data | Model learns wrong patterns |
| Missing values | Algorithms may fail |
| Inconsistent formats | Comparison impossible |
| High dimensionality | Curse of dimensionality |

### Goals
- Improve model accuracy
- Reduce computation time
- Handle missing values
- Remove irrelevant features

---

## 2. Feature Selection

**Definition:**
> Feature selection identifies the most relevant features (variables, predictors, attributes) that contribute significantly to the target — for classification, regression, or clustering.

**Goal:** Fewer, better features → simpler, faster, more accurate models

### Why Feature Selection Matters

| Benefit | Description |
|---------|-------------|
| **Improves Performance** | Reduces noise; boosts accuracy and generalisability |
| **Reduces Overfitting** | Fewer irrelevant patterns learned from training data |
| **Simplifies Models** | Easier to interpret relationships between variables |
| **Speeds Up Computation** | Fewer features → faster training and prediction |
| **Tackles Dimensionality** | Counters the curse of high-dimensional data |

---

## 3. Three Types of Feature Selection Methods

### 3.1 Filter Methods

**How it works:**
1. Apply a statistical measure to each feature
2. Rank features by relevance/contribution
3. Select top-k or those above a threshold

**Common Techniques:**

| Technique | What it does |
|-----------|-------------|
| **Correlation Coefficient** | Measures linear relationship between feature and target |
| **Chi-Square Test** | Tests independence between categorical feature and target |
| **Mutual Information** | Measures shared information between feature and target |
| **Variance Threshold** | Removes features with low variance (little information) |

**Advantages:**
- Fast and computationally efficient
- Suitable for high-dimensional data
- Reduces risk of overfitting

**Disadvantages:**
- Ignores feature interactions
- May miss non-linear relationships

---

### 3.2 Wrapper Methods

**How it works:**
1. Select a subset of features
2. Train a model and score the subset
3. Iterate to find best-performing combination

**Techniques:**

| Method | Process |
|--------|---------|
| **Forward Selection** | Start empty → add most useful feature one by one |
| **Backward Elimination** | Start with all → remove least important one by one |
| **Recursive Feature Elimination (RFE)** | Train model → drop weakest by importance → repeat |

**Trade-off:**
- ✅ Considers feature interactions (more accurate)
- ❌ Computationally expensive; can overfit

---

### 3.3 Embedded Methods

**Definition:** Feature selection is built into the model during training.

**Examples:**
- **LASSO (L1 Regularization):** Shrinks coefficients to zero — automatically drops irrelevant features
- **Ridge (L2 Regularization):** Keeps all features but shrinks coefficients
- **Tree-based:** Feature importance from split decisions

---

### 3.4 Comparison: Filter vs Wrapper vs Embedded

| Aspect | Filter | Wrapper | Embedded |
|--------|--------|---------|----------|
| **Speed** | Fast | Slow | Medium |
| **Accuracy** | Moderate | High | High |
| **Cost** | Low | High | Medium |
| **Feature Interactions** | No | Yes | Partial |
| **Overfitting Risk** | Low | High | Medium |
| **Best For** | High-dimensional data | Small datasets | Balanced approach |

---

## 4. Dimensionality Reduction — Overview

**Definition:**
> Techniques to reduce the number of features while preserving meaningful information — combating the curse of dimensionality.

### Survey of Techniques

| Technique | Type | Purpose |
|-----------|------|---------|
| **PCA** | Linear, unsupervised | Variance-preserving projection |
| **LDA** | Linear, supervised | Maximising class separability |
| **t-SNE** | Non-linear | Visualisation of high-dim data |
| **Autoencoders** | Neural network | Learned compression |
| **ICA** | Linear | Finding independent components |
| **Isomap** | Non-linear | Manifold learning |
| **MDS** | Linear/Non-linear | Distance-preserving |
| **UMAP** | Non-linear | Fast manifold approximation |
| **NMF** | Linear | Non-negative factorisation |
| **Random Projection** | Linear | Fast reduction via random matrices |
| **Feature Selection** | — | Selecting subset of features |

---

## 5. Principal Component Analysis (PCA)

**Definition:**
> PCA is a variance-preserving dimensionality reduction technique that transforms data into orthogonal principal components.

### 6 Steps of PCA (Exam Important!)

| Step | Action | Description |
|------|--------|-------------|
| **1** | **Standardise the Data** | Mean = 0, Variance = 1 (optional but common) |
| **2** | **Compute Covariance Matrix** | Shows how features vary together |
| **3** | **Calculate Eigenvalues & Eigenvectors** | Eigenvectors = directions, Eigenvalues = variance |
| **4** | **Sort by Eigenvalues** | Descending order — highest variance first |
| **5** | **Form Projection Matrix** | Select top k eigenvectors |
| **6** | **Project Data** | Transform original data onto new axes |

**Key Concepts:**
- First Principal Component captures **maximum variance**
- Eigenvalues = amount of variance captured by each component
- Components are **orthogonal** (uncorrelated)

---

## 6. Linear Discriminant Analysis (LDA)

**Definition:**
> LDA maximises class separability by projecting data onto a lower-dimensional space where classes are well separated.

### Key Concept
**Maximise between-class variance while minimising within-class variance**

### Scatter Matrices

| Matrix | Symbol | Meaning |
|--------|--------|---------|
| **Within-Class Scatter** | S_W | Spread of data within each class |
| **Between-Class Scatter** | S_B | Spread between class means |

### Optimisation Criterion
```
Maximise: J = S_B / S_W
```

### Steps
1. Compute scatter matrices (S_W and S_B)
2. Solve eigenvalue problem for S_W^(-1) × S_B
3. Select top eigenvectors
4. Project data onto new space

### PCA vs LDA

| Aspect | PCA | LDA |
|--------|-----|-----|
| **Goal** | Maximise variance | Maximise class separability |
| **Supervision** | Unsupervised (no labels) | Supervised (uses labels) |
| **Output** | Principal Components | Linear Discriminants |
| **Max dimensions** | min(n_features, n_samples) | min(n_classes - 1, n_features) |
| **Best for** | General dim. reduction | Classification tasks |

---

## 7. Random Projections

**Definition:** Fast dimensionality reduction using random matrices.

**Johnson-Lindenstrauss Lemma:** Distances between points are approximately preserved when projected to lower dimensions using random matrices.

**Steps:**
1. Generate random projection matrix R
2. Multiply data X by R
3. Output: Lower-dimensional representation

**Advantages:**
- Very fast — no training needed
- Works for large datasets
- Simple to implement

**Limitations:**
- Less interpretable than PCA
- May lose important structure

---

## 8. Compressed Sensing

**Definition:** Recovers sparse signals from fewer samples than traditional methods require.

**Key Idea:** If a signal is sparse (few non-zero components), fewer measurements are sufficient to reconstruct it.

**Steps:**
1. Acquire compressed measurements
2. Solve optimisation problem
3. Reconstruct original signal

**Requirements:**
- Signal must be **sparse**
- Measurement matrix must be **incoherent**

**Applications:** Medical imaging (MRI), signal processing, data compression

---

## 9. Feature Selection — Real Examples

### Example 1: House Price Prediction
| Feature | Relevant? | Reason |
|---------|-----------|--------|
| Area | ✅ Yes | Directly affects price |
| Location | ✅ Yes | Major price factor |
| Rooms | ✅ Yes | Contributes to value |
| Age | ✅ Yes | Depreciation factor |
| Color | ❌ No | Irrelevant noise |
| Owner name | ❌ No | No relation to price |

### Example 2: Spam Email Detection
- **Selected:** Word frequency, sender reputation, link count
- **Dropped:** Email formatting details (irrelevant)

### Example 3: Medical Diagnosis
- **Filter:** Correlation selects top features
- **Wrapper:** RFE finds optimal subset for classifier
- **Embedded:** LASSO shrinks irrelevant feature coefficients to zero

---

## 10. Exam-Ready Recap

### Must-Remember Definitions
1. **Feature Selection:** Identifying most relevant features for the target
2. **Filter Method:** Statistical evaluation independent of model
3. **Wrapper Method:** Model-based feature subset evaluation
4. **Embedded Method:** Selection during model training
5. **PCA:** Variance-preserving dimensionality reduction
6. **LDA:** Class-separability maximising dimensionality reduction

### PCA Steps (RAT LO!):
Standardise → Covariance → Eigenvalues/Eigenvectors → Sort → Projection Matrix → Project Data

### 5-Mark Answer Structure:
Definition → Types → Features → Advantages → Disadvantages → Challenges

---

*End of Unit 2 — Data Pre-processing*
