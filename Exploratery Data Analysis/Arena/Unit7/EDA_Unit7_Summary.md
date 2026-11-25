# EDA Unit 7 — Quick Summary (Last-Minute Revision)
## Module 7: Dimensionality Reduction

---

## 🔑 Key Definitions

1. **Dimensionality Reduction:** "Reducing features while preserving information — Feature Selection or Feature Extraction."

2. **Feature Selection:** "Choose subset of relevant original features."

3. **Feature Extraction:** "Create new features from original ones (PCA, LDA)."

4. **Relief:** "Attribute quality estimation based on nearest hit and miss — binary classification."

5. **PCA:** "Transforms data into orthogonal principal components capturing maximum variance."

---

## 📊 Key Tables

### Feature Selection Methods
| Method | Approach | Advantage | Disadvantage |
|--------|----------|-----------|-------------|
| **Filter** | Statistical measures | Fast | Misses interactions |
| **Wrapper** | Model-based | Accurate | Expensive |
| **Embedded** | During training | Balanced | Algorithm-specific |

### Relief Family
| Algorithm | Problem | Classes |
|-----------|---------|---------|
| **Relief** | Classification | Binary |
| **ReliefF** | Classification | Multiclass |
| **RReliefF** | Regression | Continuous |

### Extraction Methods
| Method | Type | Key Feature |
|--------|------|-------------|
| **PCA** | Unsupervised | Max variance |
| **LDA** | Supervised | Between-class variance |
| **t-SNE** | Non-linear | Local structure |
| **FA** | Latent factors | Hidden variables |

---

## 🧠 Memory Tricks

| Topic | Trick |
|-------|-------|
| Selection Methods | **"F-W-E"** → "Fast Wrapper Embeds!" |
| Relief Family | **"R-RF-RRF"** → 3 R's! |
| GA Operators | **"S-R-E-R"** → "Select, Reproduce, Evaluate, Replace!" |
| PCA Steps | **"S-C-E-S-S-T"** → Standardize, Covariance, Eigen, Sort, Select, Transform |

---

## 💻 Key R Code

```r
# Relief (using FCBF or CORElearn)
library(CORElearn)
relief <- attrEval(class ~ ., data=dataset, est="Relief")

# K-Means
km <- kmeans(data, centers=3)
plot(data, col=km$cluster)

# PCA
pca <- prcomp(data, scale=TRUE)
summary(pca)
plot(pca)

# LDA
library(MASS)
lda_result <- lda(class ~ ., data=dataset)
```

---

## 🎯 Exam Framework (5 Marks)

**Q: "Explain dimensionality reduction techniques."**
1. Definition (1) → Selection vs Extraction (1) → Methods (2) → Examples (1)

---

*Quick Revision — Unit 7 | EDA (OLMCA616) | VIT MCA*
