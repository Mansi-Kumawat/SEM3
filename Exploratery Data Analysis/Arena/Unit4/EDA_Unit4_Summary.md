# EDA Unit 4 — Quick Summary (Last-Minute Revision)
## Module 4: Data Analysis

---

## 🔑 Key Definitions

1. **Data Analysis:** "Process of inspecting, cleaning, transforming, modeling data to discover useful information and support decisions."

2. **Mean:** "Average of all values = Σx / n"

3. **Median:** "Middle value when data is sorted — robust to outliers"

4. **Mode:** "Most frequently occurring value"

5. **Variance:** "Average squared deviation from mean = Σ(xi - mean)² / n"

6. **Standard Deviation:** "Square root of variance — same units as data"

7. **Z-Score:** "Number of SDs from mean = (x - mean) / SD"

8. **Skewness:** "Measure of asymmetry — positive (right), negative (left), zero (symmetric)"

9. **Kurtosis:** "Measure of tailedness — Leptokurtic (>3), Mesokurtic (=3), Platykurtic (<3)"

---

## 📊 Key Tables

### Central Tendency
| Measure | Formula | Best For | Outlier Effect |
|---------|---------|----------|---------------|
| **Mean** | Σx/n | Symmetric, numeric | Affected |
| **Median** | Middle value | Skewed data | Robust |
| **Mode** | Most frequent | Categorical | N/A |

### Dispersion Measures
| Measure | Formula | Purpose |
|---------|---------|---------|
| **Range** | Max - Min | Simple spread |
| **Variance** | Σ(xi-x̄)²/(n-1) | Squared spread |
| **SD** | √Variance | Interpretable spread |
| **IQR** | Q3 - Q1 | Robust spread |

### Skewness Types
| Type | Tail | Mean vs Median | Example |
|------|------|---------------|---------|
| **Positive** | Right | Mean > Median > Mode | Income |
| **Negative** | Left | Mean < Median < Mode | Exam scores |
| **Zero** | Symmetric | Mean ≈ Median | Normal dist |

### Analysis Dimensions
| Dimension | Variables | Name | Purpose |
|-----------|-----------|------|---------|
| **1-D** | 1 | Univariate | Describe one variable |
| **2-D** | 2 | Bivariate | Relationship between 2 |
| **n-D** | 3+ | Multivariate | Complex relationships |

---

## 🧠 Memory Tricks

| Topic | Trick |
|-------|-------|
| Analytics Types | **"D-P-P-D"** → "Data Predicts, People Decide!" |
| Central Tendency | **"M-M-M"** → "My Mathematical Mind!" |
| Dispersion | **"R-V-S-I"** → "Really Very Simple Ideas!" |
| Skewness | **"Pos-Right, Neg-Left"** → Positive = Right tail → |
| Kurtosis | **"L-M-P"** → Lepto(>3), Meso(=3), Platy(<3) |
| Dimensions | **"1-2-n"** → Uni-Bi-Multi |

---

## 💻 Key Formulas

```
Mean = Σx / n
Variance = Σ(xi - x̄)² / (n-1)
SD = √Variance
Z-Score = (x - mean) / SD
Skewness = 3(Mean - Median) / SD
IQR = Q3 - Q1
Outlier: < Q1 - 1.5*IQR  OR  > Q3 + 1.5*IQR
Correlation: -1 to +1
Regression: y = mx + c
```

---

## 🎯 Exam Framework (5 Marks)

**Q: "Explain measures of central tendency."**
1. Definition (1) → Mean + formula + example (1) → Median + method (1) → Mode + example (1) → When to use which (1)

**Q: "Explain types of data analytics."**
1. Definition (1) → Descriptive (1) → Predictive (1) → Prescriptive (1) → Diagnostic (1)

---

*Quick Revision — Unit 4 | EDA (OLMCA616) | VIT MCA*
