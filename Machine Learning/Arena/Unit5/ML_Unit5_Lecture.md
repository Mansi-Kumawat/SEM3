# ML Unit 5 — Unsupervised Learning
## Complete Lecture Notes (Hinglish) | OLMCA602 | Week 7 + Week 8

---

## 1. Clustering Kya Hai?

**Definition:**
> Clustering groups similar data points together without predefined labels — finding hidden structures in unlabelled data.

**Simple matlab:** Koi teacher nahi batata ki kaunsa point kahan jaaye. Algorithm khud se similar points ko ek saath group karta hai. Classification se farq: Classification mein labels hote hain (teacher batata hai), clustering mein nahi — khud dhundhna padta hai.

**💡 Real Example:** Ek mall ke customers ka data hai — age, income, spending score. Koi nahi batata kaun "premium customer" hai aur kaun "budget customer." Clustering algorithm khud se groups bana deta hai!

### Six Families of Clustering

| Family | Algorithm Example | Use Case |
|--------|------------------|----------|
| **Partitioning** | K-Means | Customer segmentation |
| **Hierarchical** | Agglomerative | Taxonomy, biology |
| **Density-based** | DBSCAN | Anomaly detection |
| **Grid-based** | STING | Spatial data |
| **Model-based** | GMM | Soft clustering |
| **Spectral** | Spectral Clustering | Image segmentation |

---

## 2. K-Means Clustering — Sabse Popular!

**Definition:**
> Partitions n data points into K clusters by minimizing within-cluster variance (sum of squared distances to centroids).

### 4 Steps — Ye RAT LO!

| Step | Action | Simple Matlab |
|------|--------|---------------|
| **1** | Initialize K centroids randomly | K random points choose karo |
| **2** | Assign each point to nearest centroid | Euclidean distance se paas wala group |
| **3** | Recalculate centroids | Har cluster ka mean (average) nikalo |
| **4** | Repeat steps 2-3 | Jab tak centroids move karna band na karein |

**💡 Convergence:** Jab centroids change karna band ho jaayein — algorithm converge ho gaya!

### Objective Function
```
Minimize: Σ Σ ||xᵢ - μⱼ||²   (sum of squared distances to cluster centroids)
```

### Numerical Example (6 points, K=2)

Points: A(1,1), B(1,2), C(2,1), D(6,5), E(6,6), F(7,5)

**Iteration 1:**
- Initial centroids: M₁=A(1,1), M₂=D(6,5)
- Assign: Cluster 1={A,B,C}, Cluster 2={D,E,F}
- New centroids: M₁=(1.33, 1.33), M₂=(6.33, 5.33)

**Iteration 2:**
- Same assignments — no change!
- **Converged!** ✅ Final: {A,B,C} and {D,E,F}

**💡 Exam tip:** Numerical problem aaye toh iteration-by-iteration likhna — centroids, assignments, new centroids.

---

## 3. Choosing K — Kitne Clusters?

### Elbow Method
SSE (Sum of Squared Errors) ko K ke against plot karo. Jahan graph **elbow** banaye — sharp drop ke baad flatten ho — wo optimal K hai.

**💡 Trick:** "Elbow = best K" — jaise haath ka elbow bend hota hai, wahan K lo.

### Silhouette Score
Measure karta hai ki ek point apne cluster se kitna similar hai aur dusre clusters se kitna different.
- Range: **-1 to 1**
- Higher = better clustering
- Near 0 = overlapping clusters

### Gap Statistic
SSE ko random uniform distribution se compare karta hai. Jahan gap maximum ho — wo best K.

---

## 4. Hierarchical Clustering

**Definition:** Tree-based clustering — dendrogram banata hai showing merge/split hierarchy.

### Two Types

| Type | Approach | Process |
|------|----------|---------|
| **Agglomerative** (Bottom-Up) | Start small, merge | Har point = apna cluster → closest pairs merge → dendrogram bottom-up |
| **Divisive** (Top-Down) | Start big, split | Sab ek cluster → recursively split → dendrogram top-down |

### Linkage Methods (Agglomerative mein)

| Method | Distance Between Clusters |
|--------|--------------------------|
| **Single** | Nearest points (minimum distance) |
| **Complete** | Farthest points (maximum distance) |
| **Average** | Average of all pairwise distances |
| **Ward** | Minimizes variance increase |

**💡 Dendrogram:** Tree diagram showing how clusters merge/split. Height = distance at which merge happens. Cut at desired level to get desired number of clusters.

---

## 5. Spectral Clustering — Non-Convex Shapes

**Problem:** K-Means sirf spherical (gol) clusters handle kar sakta hai. Agar data concentric circles ya moon shapes mein ho — K-Means fail!

**Solution:** Spectral Clustering — eigenvalues use karta hai.

### Steps
1. **Build Similarity Matrix** — har pair of points ki similarity
2. **Compute Degree Matrix** D
3. **Compute Graph Laplacian** L = D - W
4. **Find eigenvalues & eigenvectors** of L
5. **Use Fiedler vector** (2nd smallest eigenvector) for clustering

**💡 Fiedler vector:** 2nd smallest eigenvalue ka eigenvector — ye data ko 2 groups mein divide karta hai.

---

## 6. K-Modes Algorithm — Categorical Data

**Problem:** K-Means numbers ke liye hai. Categories (jaise "Red", "Blue", "Small", "Large") ke liye mean calculate nahi kar sakte!

**Solution:** K-Modes — modes use karta hai, matching dissimilarity use karta hai.

### How it Works
1. Initialize K modes (most frequent categories per feature)
2. Assign each point to nearest mode using **matching dissimilarity**
3. Update modes as most frequent category in each cluster
4. Repeat until convergence

**💡 Matching Dissimilarity:** 2 points compare karo — jitne features match karein utni similarity. Jitne different utni dissimilarity.

### Applications
- Survey responses clustering
- Product category grouping
- Text data clustering

---

## 7. KNN — K-Nearest Neighbours

**Definition:**
> A lazy, instance-based learner that classifies a new point based on majority vote of its K nearest neighbours.

**"Lazy" kyun?** Kyunki iska koi training phase nahi! Saara training data yaad rakhta hai aur jab naya point aaye tab distance compute karta hai.

### 4 Steps
1. Store all training data
2. New point ke liye sabse distance compute karo (Euclidean/Manhattan)
3. K nearest neighbours select karo
4. **Classification:** Majority vote | **Regression:** Average

### Worked Example
Training: P1(1,1)→Red, P2(2,1)→Red, P3(2,2)→Red, P4(5,5)→Blue, P5(6,5)→Blue
New point: X(3,3), K=3

Distances: d(X,P3)=1.00, d(X,P2)=2.24, d(X,P1)=2.83, d(X,P4)=2.83, d(X,P5)=3.61
Top 3: P3(Red), P2(Red), P1(Red) → **3 Red, 0 Blue → X = RED** ✅

---

## 8. KNN ke 2 Critical Factors

### Choice of K

| K Value | Effect |
|---------|--------|
| **K=1** | Very sensitive to noise — overfitting |
| **K too large** | Boundary too smooth — underfitting |
| **Optimal K** | Cross-validation se find karo |

### Feature Scaling — MUST DO!

KNN distance-based hai. Agar ek feature 0-1 mein aur dusra 0-1000 mein — bada feature dominate karega!

**Solution:** StandardScaler ya MinMaxScaler use karo — sab features ko same scale pe lao.

### Distance Metrics

| Metric | Formula | Use |
|--------|---------|-----|
| **Euclidean** | √Σ(xᵢ-yᵢ)² | Most common |
| **Manhattan** | Σ\|xᵢ-yᵢ\| | Grid-like paths |
| **Minkowski** | (Σ\|xᵢ-yᵢ\|^p)^(1/p) | General form |

---

## 9. All Methods — Quick Comparison

| Method | Type | Needs K? | Best For | Speed |
|--------|------|----------|----------|-------|
| **K-Means** | Partitioning | Yes | Spherical clusters | Fast |
| **Hierarchical** | Tree | No | Any shape, small data | Slow |
| **Spectral** | Graph | Yes | Non-convex shapes | Moderate |
| **K-Modes** | Partitioning | Yes | Categorical data | Fast |
| **DBSCAN** | Density | No | Arbitrary shapes + noise | Moderate |

---

## 10. Exam-Ready Recap

### Must-Remember
```
K-Means: 4 steps — Init → Assign → Update → Repeat
Elbow: SSE vs K plot, elbow point = optimal K
Hierarchical: Agglomerative (bottom-up), Divisive (top-down)
KNN: Lazy learner, majority vote, K critical, scaling must!
```

### 5-Mark Answer Structure
**Definition → Types → Features → Advantages → Disadvantages → Challenges**

### Common Exam Questions
- K-Means algorithm + numerical example
- Choosing K — Elbow vs Silhouette vs Gap
- Hierarchical: Agglomerative vs Divisive
- Why Spectral clustering? (non-convex shapes)
- K-Modes vs K-Means (categorical vs numerical)
- KNN working + K choice + feature scaling

---

*End of Unit 5 — Unsupervised Learning* 🎯
