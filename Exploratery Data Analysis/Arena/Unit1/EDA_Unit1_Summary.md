# EDA Unit 1 — Quick Summary (Last-Minute Revision)
## Module 1: Introduction to R Programming

---

## 🔑 Key Definitions (RAT LO)

1. **R:** "Programming language and software environment for statistical analysis, graphical representation, and reporting."

2. **Vector:** "Sequence of elements of SAME type — basic data structure."

3. **List:** "Ordered collection that CAN contain DIFFERENT types."

4. **Matrix:** "2-dimensional structure with same type elements."

5. **Factor:** "Data structure for categorical variables with fixed set of levels."

6. **Data Frame:** "Table-like structure where columns CAN be DIFFERENT types."

---

## 📊 Key Tables

### Data Types (4)
| Type | Example | Note |
|------|---------|------|
| Numeric | 3.14, 2.5 | Decimal |
| Integer | 5L, 10L | L suffix required |
| Character | "hello" | Quotes required |
| Logical | TRUE, FALSE | Boolean |

### R Objects Comparison
| Object | Dimensions | Types | Use Case |
|--------|-----------|-------|----------|
| Vector | 1D | Same | Simple sequences |
| List | 1D | Mixed | Heterogeneous data |
| Matrix | 2D | Same | Linear algebra |
| Array | nD | Same | Multi-dimensional |
| Factor | 1D | Categorical | Categories |
| Data Frame | 2D | Mixed | Real datasets |

### Operators (4 types)
| Type | Examples | Purpose |
|------|----------|---------|
| Arithmetic | +, -, *, /, ^, %% | Math operations |
| Relational | <, >, ==, != | Comparisons |
| Logical | &, |, ! | Boolean logic |
| Assignment | <-, =, -> | Assign values |

### Visualization Packages (3)
| Package | Complexity | Best For |
|---------|-----------|----------|
| Base R | Simple | Quick plots |
| Lattice | Medium | Multi-panel |
| GGPLOT2 | Complex | Publication-quality |

---

## 🧠 Memory Tricks

| Topic | Trick |
|-------|-------|
| Data Types | **"N-I-C-L"** → "Nice Information Clear Learning" |
| Operators | **"A-R-L-A"** → "All R coders Love Algorithms" |
| R Objects | **"V-L-M-A-F-D"** → "Very Large Maps Aid Finding Directions" |
| Packages | **"B-L-G"** → "Big Languages Grow" |

---

## 💻 Key Code Snippets

```r
# Data types
x <- 5.5      # numeric
y <- 10L      # integer
z <- "R"      # character
flag <- TRUE  # logical

# Vector
vec <- c(1, 2, 3, 4, 5)
vec[1]        # Access first element
sum(vec)      # Sum all elements

# List
my_list <- list(name="John", age=25, scores=c(85,90))
my_list$name  # Access by name

# Matrix
mat <- matrix(1:6, nrow=2, ncol=3)
mat[1,2]      # Row 1, Column 2

# Data Frame
df <- data.frame(Name=c("John","Jane"), Age=c(25,30))
df$Name       # Access column

# Import/Export
df <- read.csv("data.csv")
write.csv(df, "output.csv")

# GGPLOT2
library(ggplot2)
ggplot(df, aes(x=Name, y=Age)) + geom_bar()
```

---

## 🎯 Exam Answer Framework (5 Marks)

**Definition → Types/Components → Examples → Applications → Comparison**

---

## ⚠️ Common Mistakes

- ❌ `x = 5L` → ✅ `x <- 5L` (use `<-`)
- ❌ Integer without L → ✅ Use `5L` not `5`
- ❌ Character without quotes → ✅ `"hello"` not `hello`
- ❌ Mixing types in vector → ✅ Use list for mixed types
- ❌ `vec[0]` → ✅ R is 1-indexed: `vec[1]`
- ❌ Single bracket for list element → ✅ `list[[1]]`
- ❌ Matrix with mixed types → ✅ Use data frame
- ❌ Not loading package after install → ✅ `library(pkg)`

---

*Quick Revision — Unit 1 | Exploratory Data Analysis (OLMCA616) | VIT MCA*
