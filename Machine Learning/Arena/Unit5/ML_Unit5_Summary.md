# ML Unit 5 — Quick Summary Notes
## Unsupervised Learning | One-Page Revision

---

### 🔑 Key Definitions

| Term | Definition |
|------|-----------|
| **Clustering** | Groups similar data without labels |
| **K-Means** | Partitions data into K clusters by minimizing variance |
| **Elbow Method** | SSE vs K plot — elbow point = optimal K |
| **Hierarchical** | Tree-based clustering (dendrogram) |
| **Spectral** | Eigenvalue-based, handles non-convex shapes |
| **K-Modes** | K-Means for categorical data (modes not means) |
| **KNN** | Lazy learner — majority vote of K nearest neighbours |

---

### 📊 K-Means: 4 Steps (RAT LO!)
1. Initialize K centroids
2. Assign points to nearest centroid
3. Recalculate centroids (mean)
4. Repeat until convergence

---

### 📊 Choosing K
| Elbow (SSE plot) | Silhouette (-1 to 1, higher=better) | Gap Statistic |

---

### 📊 Hierarchical
Agglomerative (bottom-up) | Divisive (top-down) | Dendrogram

---

### 📊 KNN Critical Factors
- **K choice:** Small=noisy, Large=smooth, Optimal=cross-validation
- **Feature Scaling:** MUST — otherwise large features dominate!
- **Distance:** Euclidean, Manhattan, Minkowski

---

### 📐 Quick Compare
| K-Means (spherical, fast) | Hierarchical (any shape, slow) | Spectral (non-convex) | K-Modes (categorical) | KNN (lazy, distance) |

---

### ⚡ Last-Minute Recap
1. Clustering: No labels, find hidden groups
2. K-Means: 4 steps, minimize variance
3. Elbow method for choosing K
4. Hierarchical: dendrogram, agglomerative/divisive
5. Spectral: eigenvalues, non-convex shapes
6. K-Modes: categorical, modes not means
7. KNN: lazy, majority vote, K + scaling critical

---

*Quick revision complete!* 🎯
