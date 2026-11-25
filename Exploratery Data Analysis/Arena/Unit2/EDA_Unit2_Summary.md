# EDA Unit 2 — Quick Summary (Last-Minute Revision)
## Module 2: Data Evolution

---

## 🔑 Key Definitions (RAT LO)

1. **Data:** "Characteristics of objects/events in coded form — numbers, letters, symbols."

2. **Qualitative Data:** "Describes objects using finite discrete classes — cannot be counted/measured."

3. **Quantitative Data:** "Data that can be counted or measured — expressed in numerical values."

4. **High Dimensional Data:** "Data with many variables/features (dimensions)."

5. **Time Series:** "Sequence of data points at regular time intervals."

6. **Transactional Data:** "Records of business transactions with unique IDs."

7. **Spatial Data:** "Data with geographical/location component — coordinates, boundaries."

8. **Social Network Data:** "Relationships between entities — nodes and edges."

---

## 📊 Key Tables

### Data Types Comparison
| Type | Nature | Example | Operations |
|------|--------|---------|------------|
| **Numeric** | Decimal | 3.14 | All math |
| **Integer** | Whole (L) | 5L | All math |
| **Character** | Text | "hello" | Concatenate |
| **Logical** | Boolean | TRUE/FALSE | AND, OR, NOT |
| **Complex** | Complex# | 3+2i | Complex math |

### Types of Data
| Type | Sub-types | Examples | Analysis |
|------|-----------|----------|----------|
| **Numeric** | Discrete, Continuous | Students, Height | Mean, SD |
| **Categorical** | Nominal, Ordinal | Gender, Rating | Frequency |
| **Graphical** | Images, Charts | PNG, CSV | Pattern |
| **High Dimensional** | Many features | Genes, Text | PCA/MDS |

### Data Sources Summary
| Source | Key Feature | Examples | Tools |
|--------|-------------|----------|-------|
| **Time Series** | Temporal | Stock, Weather | forecast, ts |
| **Transactional** | Business records | Orders, Payments | SQL |
| **Biological** | Life science | DNA, Medical | Bioconductor |
| **Spatial** | Geographic | Maps, GPS | sf, sp |
| **Social Network** | Relationships | Friends, Links | igraph |

### Time Series Components (TSCI)
| Component | Description | Pattern |
|-----------|-------------|---------|
| **Trend** | Long-term direction | Up/Down |
| **Seasonality** | Fixed interval repeats | Monthly, Yearly |
| **Cyclical** | Longer fluctuations | Economic cycles |
| **Irregular** | Random noise | Unpredictable |

---

## 🧠 Memory Tricks

| Topic | Trick |
|-------|-------|
| Data Types | **"N-C-G-H"** → "Never Cheat Good Humans" |
| Data Sources | **"T-T-B-S-S"** → "Two Tigers Beat Seven Snakes" |
| Time Series | **"T-S-C-I"** → "The Sun Comes In" |
| Qualitative | **"N-O"** → Nominal (No order), Ordinal (Has order) |
| Quantitative | **"D-C"** → Discrete (Count), Continuous (Can-be-any) |
| Big Data | **"V-V-V"** → Volume, Velocity, Variety → "Very Very Vast!" |

---

## 💻 Key Code Snippets

```r
# Data types
x <- 3.14      # numeric
y <- 5L        # integer (L required!)
z <- "hello"   # character
flag <- TRUE   # logical
c <- 3 + 2i    # complex

# Reading data
df <- read.csv("data.csv")
df <- read.delim("data.txt")

# Writing data
write.csv(df, "output.csv", row.names=FALSE)

# Check working directory
getwd()
setwd("path/to/folder")

# Time series
ts_data <- ts(data, frequency=12, start=c(2020,1))
decomposed <- decompose(ts_data)
```

---

## 🎯 Exam Answer Framework (5 Marks)

**Q: "Explain types of data with examples."**

**Structure:**
1. **Definition** (1 mark) — Data types classification
2. **Numeric** (1 mark) — Discrete + Continuous with examples
3. **Categorical** (1 mark) — Nominal + Ordinal with examples
4. **Graphical/High-D** (1 mark) — Visual + many features
5. **Sources** (1 mark) — Time Series, Transactional, Biological, Spatial, Social

---

## ⚠️ Common Mistakes

- ❌ Averaging categorical data → ✅ Use frequency, mode
- ❌ Forgetting L for integer → ✅ Always use `5L` not `5`
- ❌ Confusing discrete/continuous → ✅ Discrete=countable, Continuous=measurable
- ❌ Treating nominal same as ordinal → ✅ Nominal=no order, Ordinal=has order
- ❌ Ignoring time series seasonality → ✅ Always decompose first
- ❌ Not handling high dimensions → ✅ Apply PCA/dimensionality reduction
- ❌ Confusing spatial vs network → ✅ Spatial=geographic, Network=relationships

---

## 📈 Key Formulas/Concepts

| Concept | Formula/Definition |
|---------|-------------------|
| **Stationarity** | Mean, variance constant over time |
| **Curse of Dimensionality** | Distance becomes meaningless as dimensions increase |
| **3 V's** | Volume, Velocity, Variety |
| **Topological Relations** | Adjacency, Connectivity, Containment |
| **Network Components** | Nodes (actors), Edges (relationships) |

---

*Quick Revision — Unit 2 | Exploratory Data Analysis (OLMCA616) | VIT MCA*
