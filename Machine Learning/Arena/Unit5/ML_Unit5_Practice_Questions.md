# ML Unit 5 — Practice Questions
## Unsupervised Learning (Week 7 + Week 8)

---

## Part A: Multiple Choice (1 Mark)

**Q1.** K-Means minimizes: (A) Between-cluster variance (B) Within-cluster variance (C) Total data variance (D) Number of clusters
**Answer: (B)**

**Q2.** Elbow method is used to find: (A) Optimal K (B) Learning rate (C) Distance metric (D) Convergence point
**Answer: (A)**

**Q3.** Agglomerative clustering is: (A) Top-down (B) Bottom-up (C) Random (D) Grid-based
**Answer: (B)**

**Q4.** Spectral clustering handles: (A) Only spherical clusters (B) Non-convex shapes (C) Only categorical data (D) Only 2D data
**Answer: (B)**

**Q5.** K-Modes is used for: (A) Numerical data (B) Categorical data (C) Time series (D) Images
**Answer: (B)**

**Q6.** KNN is called "lazy" because: (A) It's slow (B) No training phase (C) Uses lazy evaluation (D) Needs less data
**Answer: (B)**

**Q7.** Silhouette score range: (A) 0 to 1 (B) -1 to 1 (C) -∞ to ∞ (D) 0 to ∞
**Answer: (B)**

**Q8.** In KNN, if K=1, the model is prone to: (A) Underfitting (B) Overfitting (C) Convergence (D) Divergence
**Answer: (B)**

**Q9.** Which linkage uses farthest points? (A) Single (B) Complete (C) Average (D) Ward
**Answer: (B)**

**Q10.** Fiedler vector is used in: (A) K-Means (B) KNN (C) Spectral Clustering (D) DBSCAN
**Answer: (C)**

---

## Part B: Short Answer (2 Marks)

**Q1.** List 4 steps of K-Means algorithm.
**Answer:** 1. Initialize K centroids randomly. 2. Assign points to nearest centroid. 3. Recalculate centroids as cluster means. 4. Repeat until convergence.

**Q2.** Differentiate Agglomerative and Divisive clustering.
**Answer:** Agglomerative: Bottom-up, start with individual points, merge closest pairs. Divisive: Top-down, start with one cluster, recursively split.

**Q3.** Why is feature scaling important for KNN?
**Answer:** KNN uses distance metrics. Without scaling, features with larger ranges dominate the distance calculation, giving them unfair weight. Scaling ensures all features contribute equally.

**Q4.** What is the elbow method?
**Answer:** Plot SSE vs K. Look for the "elbow" point where SSE drops sharply then flattens. That K is optimal — adding more clusters doesn't significantly reduce error.

---

## Part C: Descriptive (5 Marks)

**Q1.** Explain K-Means clustering with a numerical example.

**Answer Structure:**
**Definition:** Partitions n points into K clusters minimizing within-cluster variance.
**Steps:** Init K centroids → Assign to nearest → Recalculate centroids → Repeat until convergence.
**Objective:** Minimize Σ||xᵢ-μⱼ||².
**Numerical:** 6 points, K=2. Iteration 1: centroids, assignments, new centroids. Iteration 2: converged.
**Advantages:** Simple, fast, scalable.
**Disadvantages:** Needs K predefined, spherical clusters only, sensitive to initial centroids.
**Challenges:** Choosing K, handling non-spherical shapes, outlier sensitivity.

**Q2.** Explain KNN algorithm with factors affecting its performance.

**Answer Structure:**
**Definition:** Lazy instance-based learner — majority vote of K nearest neighbours.
**Steps:** Store data → Compute distances → Select K nearest → Majority vote/Average.
**K Choice:** Small K=noisy/overfit, Large K=smooth/underfit, Optimal=cross-validation.
**Feature Scaling:** Must scale features — otherwise large-range features dominate distance.
**Distance Metrics:** Euclidean, Manhattan, Minkowski.
**Advantages:** Simple, no training, works for classification and regression.
**Disadvantages:** Slow prediction (compute all distances), memory intensive, sensitive to K and scaling.
**Challenges:** Choosing K, curse of dimensionality, irrelevant features.

---

*Practice makes perfect!* 🎯
