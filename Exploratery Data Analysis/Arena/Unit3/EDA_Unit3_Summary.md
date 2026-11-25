# EDA Unit 3 — Quick Summary (Last-Minute Revision)
## Module 3: Data Pre-processing

---

## 🔑 Key Definitions (RAT LO)

1. **Data Pre-processing:** "Cleaning and transforming raw data into analysis-ready format."

2. **Data Cleaning:** "Identifying and rectifying errors, inconsistencies, and inaccuracies in a dataset."

3. **Data Integration:** "Combining data from multiple heterogeneous sources into a single dataset."

4. **Data Reduction:** "Reducing volume of data preserving quality — PCA, feature selection."

5. **Data Transformation:** "Transforming structure — categorical ↔ numerical, normalization."

6. **Missing Data (MCAR):** "Missingness completely random, unrelated to any variable."

7. **Missing Data (MAR):** "Missingness related to observed variables, not missing values."

8. **Missing Data (MNAR):** "Missingness related to the missing values themselves."

---

## 📊 Key Tables

### Data Pre-processing Pipeline
| Step | Purpose | R Functions |
|------|---------|-------------|
| **Cleaning** | Fix errors, missing, outliers | is.na(), summary(), unique() |
| **Integration** | Combine sources | merge() |
| **Reduction** | Reduce volume, dimensions | PCA, cor(), subset() |
| **Transformation** | Change structure, scale | scale(), cut(), smooth() |

### Missing Data Types
| Type | Missingness | Ignorable? | Example |
|------|-------------|-----------|---------|
| **MCAR** | Random, unrelated | Yes | Coin flip |
| **MAR** | Related to observed | Yes | Men skip survey |
| **MNAR** | Related to missing values | No | Drug users skip survey |

### Normalization Formulas
| Type | Formula | Range |
|------|---------|-------|
| **Min-Max** | (v-min)/(max-min) | 0 to 1 |
| **Z-Score** | (v-mean)/std_dev | Mean=0, SD=1 |
| **Decimal** | Move decimal j places | Scaled |

### Dimensionality Reduction
| Technique | What it does | Advantage |
|-----------|-------------|-----------|
| **Feature Selection** | Pick important features | Simple |
| **Feature Extraction** | Create new features | Keeps structure |
| **PCA** | Principal components | Most popular |

---

## 🧠 Memory Tricks

| Topic | Trick |
|-------|-------|
| Pre-processing Steps | **"C-I-R-T"** → "Clean It Right, Totally!" |
| Missing Types | **"MCAR-MAR-MNAR"** → C=Complete, A=At, N=Not |
| Normalization | **"M-Z-D"** → Min-Max, Z-Score, Decimal |
| Multiple Imputation | **"I-A-P"** → "Impute, Analyze, Pool!" |
| Transformation Methods | **"S-A-D-N"** → "Simply Analyze Data Now!" |

---

## 💻 Key Code Snippets

```r
# Missing values
is.na(data)              # Check missing
mean(x, na.rm = TRUE)    # Ignore NA in mean
summary(data)            # Overview with missing counts

# Data cleaning
unique(data)             # Remove duplicates
complete.cases(data)     # Rows without missing

# Data integration
merged <- merge(df1, df2, by = "ID")

# Data transformation
scale(data)              # Z-score normalization
cut(age, breaks=3, labels=c("Low","Med","High"))  # Discretize

# Missing data handling
library(mice)
imputed <- mice(data, m=5)    # Multiple imputation
pooled <- pool(with(imputed, lm(y~x)))
```

---

## 🎯 Exam Answer Framework (5 Marks)

**Q: "Explain types of missing data and handling methods."**

**Structure:**
1. **Definition** (1) — Missing data = absence of values
2. **Three types** (2) — MCAR, MAR, MNAR with examples
3. **Traditional methods** (1) — Deletion + Imputation
4. **Multiple imputation** (1) — I-A-P steps, advantages

---

## ⚠️ Common Mistakes

- ❌ `mean(x)` with NA → ✅ `mean(x, na.rm=TRUE)`
- ❌ Always listwise deletion → ✅ Consider imputation
- ❌ MCAR = MAR → ✅ Different mechanisms!
- ❌ Single imputation for complex data → ✅ Multiple imputation
- ❌ Merge without renaming → ✅ Fix column names first
- ❌ Forgetting to document → ✅ Always document handling

---

*Quick Revision — Unit 3 | EDA (OLMCA616) | VIT MCA*
