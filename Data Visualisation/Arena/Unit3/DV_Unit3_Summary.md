# DV Unit 3 — Quick Summary (Last-Minute Revision)
## Module 3: Multivariate Visualization and Relation Representation

---

## 🔑 Key Definitions (RAT LO)

1. **Parallel Sets:** "Displays relationships between multiple categorical variables using vertical axes and flow ribbons — ribbon width = frequency."

2. **Scatter Plot:** "Each observation becomes a point — X and Y position reveals relationship between two numeric variables."

3. **Correlation Coefficient (r):** "Measures linear relationship strength from -1 to +1. +1 = perfect positive, -1 = perfect negative, 0 = no correlation."

4. **Correlogram:** "Visual representation of correlation matrix — correlation coefficients as color-coded cells."

5. **Dimension Reduction:** "Simplifying high-dimensional data while preserving important structure — PCA, t-SNE, UMAP."

6. **Paired Data:** "Two related measurements on same subject — pairing carries meaning that must be preserved."

7. **Time Series:** "Data recorded sequentially over time — order is the whole point. Components: Trend, Seasonality, Noise."

8. **Dose-Response:** "Relationship between dose/concentration (X) and response/effect (Y) — shows how system responds to changing input."

---

## 📊 Key Comparison Tables

### Parallel Sets vs Coordinates
| Feature | Parallel Sets | Parallel Coordinates |
|---------|---------------|---------------------|
| Data type | Categorical | Numeric |
| Display | Ribbons | Lines |

### Dimension Reduction Methods
| Method | Type | Speed | Structure |
|--------|------|-------|-----------|
| PCA | Linear | Fast | Global |
| t-SNE | Non-linear | Slow | Local |
| UMAP | Non-linear | Medium | Both |

### Correlation Interpretation
| r Value | Strength |
|---------|----------|
| 0.0-0.3 | Weak |
| 0.3-0.7 | Moderate |
| 0.7-1.0 | Strong |

### Time Series Comparison Techniques
| Technique | Best For |
|-----------|----------|
| Overlaid lines | Few series, similar scales |
| Indexing | Different starting scales |
| Small multiples | Many series, clear comparison |

---

## 🧠 Memory Tricks

| Topic | Trick |
|-------|-------|
| Parallel Sets vs Coords | **"Sets = Categorical, Coords = Continuous"** |
| Correlation Types | **"P-N-N"** → Positive, Negative, None |
| Dimension Reduction | **"P-t-U"** → PCA, t-SNE, UMAP |
| Time Series Components | **"TSN"** → Trend, Seasonality, Noise |
| Paired Data Methods | **"S-B"** → Slope, Bland-Altman |

---

## 🎯 Exam Answer Framework (5 Marks)

**Definition → Methods/Types → Structure → Advantages → Applications**

---

## ⚠️ Common Mistakes

- ❌ Parallel Coordinates for categorical → ✅ Parallel Sets
- ❌ Ignoring ± sign in correlation → ✅ Always note direction
- ❌ PCA for non-linear data → ✅ t-SNE or UMAP
- ❌ Treating paired as independent → ✅ Preserve pairing
- ❌ Overlapping time series → ✅ Small multiples/indexing
- ❌ Correlation = Causation → ✅ Correlation ≠ Causation!

---

*Quick Revision — Unit 3 | Data Visualization (OLMCA618) | VIT MCA*
