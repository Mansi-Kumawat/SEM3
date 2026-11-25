# ML Unit 2 — Quick Summary Notes
## Data Pre-processing | One-Page Revision

---

### 🔑 Key Definitions

| Term | Definition |
|------|-----------|
| **Data Preprocessing** | Transform raw data into clean, ML-ready format |
| **Feature Selection** | Identify most relevant features, drop noisy/redundant |
| **Filter Method** | Statistical evaluation independent of model (fast) |
| **Wrapper Method** | Model-based subset evaluation (accurate, costly) |
| **Embedded Method** | Selection during training (balanced) |
| **PCA** | Variance-preserving dimensionality reduction |
| **LDA** | Class-separability maximising dimensionality reduction |

---

### 📊 Feature Selection — 3 Methods

| Aspect | Filter | Wrapper | Embedded |
|--------|--------|---------|----------|
| Speed | Fast | Slow | Medium |
| Accuracy | Moderate | High | High |
| Cost | Low | High | Medium |
| Feature Interactions | ❌ No | ✅ Yes | ⚠️ Partial |

**Filter:** Correlation, Chi-Square, MI, Variance Threshold
**Wrapper:** Forward Selection, Backward Elimination, RFE
**Embedded:** LASSO, Ridge, Tree-based

---

### 📐 PCA — 6 Steps (RAT LO!)
1. Standardise Data
2. Compute Covariance Matrix
3. Calculate Eigenvalues & Eigenvectors
4. Sort by Eigenvalues (descending)
5. Form Projection Matrix (top k)
6. Project Data

---

### 📐 LDA vs PCA

| | PCA | LDA |
|---|-----|-----|
| Goal | Maximise variance | Maximise class separability |
| Labels | Not needed | Required |
| Output | Principal Components | Linear Discriminants |

**LDA Optimisation:** Maximise S_B / S_W (Between-class / Within-class scatter)

---

### 🎯 Other Techniques
- **Random Projections:** Fast via random matrices (J-L Lemma)
- **Compressed Sensing:** Sparse signal recovery from few samples
- **t-SNE:** Visualisation of high-dim data
- **Autoencoders:** Neural network based compression

---

### ⚡ Last-Minute Recap
1. Preprocessing: Raw → Clean data
2. Feature Selection: Keep relevant, drop noise
3. 3 Methods: Filter/Wrapper/Embedded
4. PCA: 6 steps, variance maximisation
5. LDA: Class separation, S_B/S_W ratio
6. Random Projection + Compressed Sensing

---

*Quick revision complete!* 🎯
