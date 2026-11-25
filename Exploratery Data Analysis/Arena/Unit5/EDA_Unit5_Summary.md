# EDA Unit 5 — Quick Summary (Last-Minute Revision)
## Module 5: Data Visualization

---

## 🔑 Key Definitions

1. **Data Visualization:** "Process of converting data into visual environment (plots, graphs, images) for easy understanding."

2. **Histogram:** "Distribution of continuous data with adjacent bars (no gaps)."

3. **Pie Chart:** "Circular chart divided into sectors showing proportions."

4. **Box Plot:** "Visualizes five-number summary: Min, Q1, Median, Q3, Max."

5. **Scatter Plot:** "Relationship between two quantitative variables on X-Y axes."

6. **Stem-and-Leaf:** "Distribution display preserving actual data values."

7. **Heat Map:** "2D visualization using color for matrix data."

8. **Voronoi Diagram:** "Spatial partition based on distance to seed points."

---

## 📊 Key Comparison Tables

### All Charts at a Glance
| Chart | Data Type | Key Feature | R Function |
|-------|-----------|-------------|------------|
| **Histogram** | Continuous | Adjacent bars | hist() |
| **Pie** | Categorical | Proportions | pie() |
| **Box Plot** | Any | Outliers | boxplot() |
| **Scatter** | 2 numeric | Correlation | plot() |
| **Stem-Leaf** | Numeric | Preserves values | stem() |
| **Heat Map** | Matrix | Color-coded | heatmap() |
| **Pareto** | Categorical | 80/20 rule | pareto.chart() |
| **Andrew** | Multivariate | Curves | andrews() |
| **Multi-vari** | Multiple | Patterns | matplot() |
| **Run** | Time | Trends | plot(type="l") |
| **Voronoi** | Spatial | Partition | deldir() |

### Histogram vs Bar Chart
| Feature | Histogram | Bar Chart |
|---------|-----------|-----------|
| Data | Continuous | Categorical |
| Bars | Adjacent | Separated |
| Order | No order | Any order |

### Box Plot Components
| Component | Meaning |
|-----------|---------|
| Box | IQR (Q1 to Q3) |
| Line | Median |
| Whiskers | Min/Max (1.5×IQR) |
| Dots | Outliers |
| Notch | Confidence interval |

---

## 🧠 Memory Tricks

| Topic | Trick |
|-------|-------|
| Charts | **"H-P-B-M-R-A-P-S-S-H-V"** → "Happy Pandas..." |
| Distribution | **"H-S-B"** → Histogram, Stem, Box |
| Relationships | **"S-M-A"** → Scatter, Multi, Andrew |
| Box Plot | **"M-Q-M-Q-M"** → Min, Q1, Med, Q3, Max |

---

## 💻 Key R Code

```r
# Histogram
hist(data, breaks=10, col="blue")

# Pie Chart
pie(values, labels=names, col=colors)

# Box Plot
boxplot(data, notch=TRUE)

# Scatter Plot
plot(x, y, pch=20, col="red")
abline(lm(y~x), col="blue")  # trend line

# Stem-and-Leaf
stem(data)

# Heat Map
heatmap(matrix_data)

# Multi-vari
matplot(x, y_matrix, type="l")

# Run Chart
plot(data, type="l")
```

---

## ⚠️ Common Mistakes

- ❌ Pie for 20 categories → ✅ Bar chart
- ❌ Histogram = Bar chart → ✅ Different data types!
- ❌ Ignoring distribution shape → ✅ Check skewness first
- ❌ 3D charts → ✅ 2D is clearer
- ❌ Overcrowded charts → ✅ Keep simple

---

*Quick Revision — Unit 5 | EDA (OLMCA616) | VIT MCA*
