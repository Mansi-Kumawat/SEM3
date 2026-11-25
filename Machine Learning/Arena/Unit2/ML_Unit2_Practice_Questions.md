# ML Unit 2 — Practice Questions
## Data Pre-processing

---

## Part A: Multiple Choice (1 Mark Each)

**Q1.** Feature selection aims to:
- (A) Add more features to the dataset
- (B) Identify the most relevant features
- (C) Increase computational complexity
- (D) Remove all numerical features

**Answer: (B)**

---

**Q2.** Which feature selection method is fastest?
- (A) Wrapper
- (B) Embedded
- (C) Filter
- (D) All are equal

**Answer: (C)**

---

**Q3.** PCA is which type of technique?
- (A) Supervised
- (B) Unsupervised
- (C) Reinforcement
- (D) Semi-supervised

**Answer: (B)**

---

**Q4.** LDA maximises:
- (A) Variance
- (B) Class separability
- (C) Feature count
- (D) Training time

**Answer: (B)**

---

**Q5.** LASSO uses which regularization?
- (A) L2
- (B) L1
- (C) No regularization
- (D) Both L1 and L2

**Answer: (B)**

---

**Q6.** The first principal component captures:
- (A) Minimum variance
- (B) Maximum variance
- (C) Mean of data
- (D) Zero variance

**Answer: (B)**

---

**Q7.** RFE stands for:
- (A) Random Feature Extraction
- (B) Recursive Feature Elimination
- (C) Rapid Feature Evaluation
- (D) Reduced Feature Encoding

**Answer: (B)**

---

**Q8.** Which technique uses random matrices for dimensionality reduction?
- (A) PCA
- (B) LDA
- (C) Random Projections
- (D) t-SNE

**Answer: (C)**

---

**Q9.** Compressed Sensing works best when the signal is:
- (A) Dense
- (B) Sparse
- (C) Noisy
- (D) Continuous

**Answer: (B)**

---

**Q10.** Which is NOT a filter method?
- (A) Correlation Coefficient
- (B) Chi-Square Test
- (C) Forward Selection
- (D) Mutual Information

**Answer: (C)** — Forward Selection is a Wrapper method

---

## Part B: Short Answer (2 Marks Each)

**Q1.** Differentiate between Filter and Wrapper feature selection methods.

**Answer:**
| Feature | Filter | Wrapper |
|---------|--------|---------|
| Evaluation | Statistical, independent of model | Model-based subset scoring |
| Speed | Fast | Slow |
| Accuracy | Moderate | High |
| Feature interactions | Ignored | Considered |
| Overfitting risk | Low | High |

---

**Q2.** List the 6 steps of PCA.

**Answer:**
1. Standardise the data (mean=0, variance=1)
2. Compute the Covariance Matrix
3. Calculate Eigenvalues and Eigenvectors
4. Sort Eigenvalues in descending order
5. Form Projection Matrix using top k eigenvectors
6. Project the data onto new axes

---

**Q3.** What is the difference between PCA and LDA?

**Answer:**
PCA is unsupervised — maximises variance, no labels needed. LDA is supervised — maximises class separability using labels. PCA outputs Principal Components, LDA outputs Linear Discriminants. PCA is for general dimensionality reduction, LDA is best for classification tasks.

---

**Q4.** What is Compressed Sensing? When is it used?

**Answer:**
Compressed Sensing recovers sparse signals from fewer samples than traditional methods require. It works when the signal is sparse (few non-zero components). Used in medical imaging (MRI), signal processing, and data compression. Requires signal sparsity and incoherent measurement matrix.

---

**Q5.** Explain Forward Selection and Backward Elimination.

**Answer:**
Forward Selection: Start with empty feature set. Add the most useful feature one by one based on model performance. Stop when no improvement.
Backward Elimination: Start with all features. Remove the least important feature one by one. Stop when removal decreases performance.
Both are Wrapper methods — computationally expensive but consider feature interactions.

---

## Part C: Descriptive (5 Marks — Professor's Format)

**Q1.** Explain Feature Selection and its three types with advantages and disadvantages.

**Answer Structure:**

**Definition:** Feature selection identifies the most relevant features that contribute significantly to the target — for classification, regression, or clustering.

**Three Types:**

1. **Filter Methods** — Statistical evaluation independent of model
   - Techniques: Correlation, Chi-Square, MI, Variance Threshold
   - Advantages: Fast, scalable, reduces overfitting
   - Disadvantages: Ignores feature interactions, misses non-linear

2. **Wrapper Methods** — Model-based subset evaluation
   - Techniques: Forward Selection, Backward Elimination, RFE
   - Advantages: Considers interactions, high accuracy
   - Disadvantages: Computationally expensive, overfitting risk

3. **Embedded Methods** — Selection during training
   - Examples: LASSO, Ridge, Tree-based
   - Advantages: Balanced speed and accuracy
   - Disadvantages: Tied to specific model type

**Features:** Reduces dimensionality, improves speed, prevents overfitting

**Challenges:** Choosing right method, handling correlated features, computational cost for large datasets

---

**Q2.** Explain PCA with its steps and a worked example.

**Answer Structure:**

**Definition:** PCA is a variance-preserving dimensionality reduction technique that transforms data into orthogonal principal components.

**Steps:**
1. Standardise the data
2. Compute Covariance Matrix
3. Calculate Eigenvalues & Eigenvectors
4. Sort by Eigenvalues (descending)
5. Form Projection Matrix (top k eigenvectors)
6. Project data onto new axes

**Key Points:**
- First PC captures maximum variance
- Eigenvalues = variance captured
- Components are orthogonal (uncorrelated)

**Advantages:** Reduces dimensionality, removes noise, speeds up training

**Disadvantages:** Linear method only, less interpretable, may lose information

**Challenges:** Choosing number of components, handling non-linear data, scaling issues

---

*Practice makes perfect!* 🎯
