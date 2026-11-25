# Exploratory Data Analysis — Unit 1 Comprehensive Lecture Notes
## Module 1: Introduction to R Programming (Week 1)
### Subject: OLMCA616 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Explain** what R is and its features in data science
2. **Install** R and RStudio with proper configuration
3. **Navigate** RStudio interface and execute commands
4. **Identify** 4 basic data types in R
5. **Apply** arithmetic, relational, logical, and assignment operators
6. **Create** and manipulate vectors, lists, matrices, arrays, factors, and data frames
7. **Import/Export** data in various file formats
8. **Create** basic visualizations using Base R, Lattice, and GGPLOT2
9. **Answer** exam questions using 5-mark framework

---

## 1. Introduction to R

### Hook 🎯
Data science ki duniya mein R ek superstar hai! Statistics, visualization, machine learning — sab ke liye R use hota hai. Free hai, open-source hai, aur powerful bhi!

### Definition 🌟
> **"R is a programming language and software environment widely used for statistical analysis, graphical representation, and reporting."**

### Key Information 🌟
- **Developed by:** Ross Ihaka and Robert Gentleman
- **Where:** University of Auckland, New Zealand
- **When:** Implementation of S programming language
- **Status:** Open-source and free

### Features of R 🌟

| Feature | Description |
|---------|-------------|
| **Statistical Analysis** | Extensive tools for various statistical analyses |
| **Graphics** | Powerful graphics capabilities for data visualization |
| **Packages** | CRAN hosts thousands of packages for diverse needs |
| **Platform Independent** | Available on Windows, Mac, and Linux |
| **Programming Language** | Allows users to write custom functions, models, methods |
| **Community Support** | Strong and active community for learning and problem-solving |

### R in Data Science 🌟

| Application | Description |
|-------------|-------------|
| **Data Cleaning** | Transforming raw data into analysis-ready form |
| **Statistical Analysis** | Robust environment for statistical techniques |
| **Data Visualization** | Basic plots to intricate interactive visualizations |
| **Machine Learning** | Packages for predictive analytics |

### R vs Other Tools 🌟
- **vs Python:** R better for statistical analysis, Python more general-purpose
- **vs MATLAB:** R free, MATLAB commercial
- **vs SAS:** R open-source, SAS expensive
- **Choice depends on:** Project requirements, user familiarity, analysis type

---

## 2. Installation and Setup

### Installing R 🌟

**Step-by-Step Process:**
1. **Visit CRAN:** https://cran.r-project.org/
2. **Select OS:** Windows, Mac, or Linux
3. **Download:** Latest version (keep updated!)
4. **Install:** Follow instructions, accept default settings

### Setting Up RStudio 🌟

**Why RStudio?**
- Integrated Development Environment (IDE) for R
- User-friendly experience
- Organized workspace with various panes

**Installation Steps:**
1. Download from: https://www.rstudio.com/
2. Install AFTER installing R
3. RStudio detects R automatically

### RStudio Interface — 4 Main Panes 🌟

| Pane | Purpose |
|------|---------|
| **Console Pane** | Execute commands, display results |
| **Script Editor** | Write, edit, save R scripts |
| **Environment/History Pane** | Track variables, command history |
| **Files/Plots/Packages/Help Pane** | Navigate files, visualize plots, manage packages, access documentation |

### Basic Configuration 🌟

```r
# Set working directory
setwd("path/to/directory")

# Update packages
update.packages()

# Test installation
print("Hello, R!")
```

---

## 3. Data Types in R

### Hook 🎯
Har programming language mein data types hote hain — R mein bhi 4 basic types hain. Inhe samajhna zaroori hai — warna operations galat honge!

### Four Basic Data Types 🌟

| Type | Description | Example | Suffix |
|------|-------------|---------|--------|
| **Numeric** | Decimal values | 3.14, 2.5, 10.7 | None |
| **Integer** | Whole numbers | 5L, 10L, 100L | L (required) |
| **Character** | Text strings | "hello", 'world', "R programming" | Quotes required |
| **Logical** | Boolean values | TRUE, FALSE | None |

### Checking Data Type 🌟

```r
# Using class() function
x <- 5.5
class(x)  # Returns "numeric"

# Using typeof() function
typeof(x)  # Returns "double"
```

### Type Conversion 🌟

| Function | Converts To |
|----------|-------------|
| `as.numeric()` | Numeric |
| `as.character()` | Character |
| `as.logical()` | Logical |
| `as.integer()` | Integer |

### Examples 🌟

```r
x <- 5.5          # numeric
y <- 10L          # integer (L suffix required)
z <- "R programming"  # character
flag <- TRUE      # logical
```

### Important Note 🌟
**R is dynamically typed** — variable type determined by value assigned, no need to declare type explicitly.

---

## 4. Basic Operators in R

### Hook 🎯
Operators programming ki building blocks hain — calculations, comparisons, logical operations — sab operators se hota hai!

### Four Types of Operators 🌟

#### 4.1 Arithmetic Operators 🌟

| Operator | Operation | Example | Result |
|----------|-----------|---------|--------|
| `+` | Addition | `5 + 3` | 8 |
| `-` | Subtraction | `10 - 4` | 6 |
| `*` | Multiplication | `3 * 4` | 12 |
| `/` | Division | `15 / 3` | 5 |
| `^` | Exponentiation | `2^3` | 8 |
| `%%` | Modulus (remainder) | `10 %% 3` | 1 |
| `%/%` | Integer division | `10 %/% 3` | 3 |

#### 4.2 Relational Operators 🌟

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `<` | Less than | `5 < 3` | FALSE |
| `>` | Greater than | `5 > 3` | TRUE |
| `==` | Equal to | `5 == 5` | TRUE |
| `!=` | Not equal to | `5 != 3` | TRUE |
| `<=` | Less than or equal | `5 <= 5` | TRUE |
| `>=` | Greater than or equal | `5 >= 3` | TRUE |

**Returns:** TRUE or FALSE (logical values)

#### 4.3 Logical Operators 🌟

| Operator | Meaning | Example |
|----------|---------|---------|
| `&` | AND (element-wise) | `TRUE & FALSE` → FALSE |
| `|` | OR (element-wise) | `TRUE | FALSE` → TRUE |
| `!` | NOT | `!TRUE` → FALSE |
| `&&` | AND (short-circuit) | `TRUE && FALSE` → FALSE |
| `||` | OR (short-circuit) | `TRUE || FALSE` → TRUE |

**Short-circuit vs Element-wise:**
- `&&` and `||` — faster, evaluate only first element
- `&` and `|` — work on vectors element by element

#### 4.4 Assignment Operators 🌟

| Operator | Direction | Example |
|----------|-----------|---------|
| `<-` | Left assignment (most common) | `x <- 10` |
| `->` | Right assignment | `10 -> x` |
| `=` | Assignment (also works) | `x = 10` |

**Best Practice:** Use `<-` for assignment (standard R convention)

---

## 5. Vectors in R

### Hook 🎯
Vector R ka most basic data structure hai — ek hi type ke elements ka sequence. Simple hai par bahut powerful!

### Definition 🌟
> **"Vector is a sequence of elements of the SAME type."**

### Creating Vectors 🌟

```r
# Using c() function (combine/concatenate)
num_vec <- c(1, 2, 3, 4, 5)
char_vec <- c("a", "b", "c")
log_vec <- c(TRUE, FALSE, TRUE)
```

### Types of Vectors 🌟

| Type | Example | Elements |
|------|---------|----------|
| **Numeric** | `c(1.5, 2.7, 3.9)` | Decimal numbers |
| **Character** | `c("a", "b", "c")` | Text strings |
| **Logical** | `c(TRUE, FALSE, TRUE)` | Boolean values |

### Accessing Vector Elements 🌟

```r
vec <- c(10, 20, 30, 40, 50)

# By index
vec[1]        # First element: 10
vec[2:4]      # Range: 20, 30, 40
vec[c(1,3)]   # Specific indices: 10, 30

# By name
names(vec) <- c("a", "b", "c", "d", "e")
vec["a"]      # Returns 10
```

### Vector Operations 🌟

```r
vec <- c(1, 2, 3, 4, 5)

# Vectorized operations (apply to all elements)
vec * 2       # 2, 4, 6, 8, 10
vec + 10      # 11, 12, 13, 14, 15

# Functions
sum(vec)      # 15
mean(vec)     # 3
length(vec)   # 5
max(vec)      # 5
min(vec)      # 1
```

### Important Rule 🌟
**All elements must be same type!** If you mix types, R coerces (converts) them to one type.

```r
mixed <- c(1, "a", TRUE)
# Result: All become character -> "1", "a", "TRUE"
```

---

## 6. Lists in R

### Hook 🎯
Vectors mein sirf same type ke elements — par lists mein mixed types daal sakte ho! Flexible hain lists!

### Definition 🌟
> **"List is an ordered collection of objects that CAN contain DIFFERENT types."**

### Creating Lists 🌟

```r
my_list <- list(
  name = "John",
  age = 25,
  scores = c(85, 90, 92),
  adult = TRUE
)
```

**Contains:** Character, numeric, vector, logical — all in one list!

### Accessing List Elements 🌟

```r
# By index (double bracket for element)
my_list[[1]]           # "John"
my_list[["name"]]      # "John"

# By name
my_list$name           # "John"
my_list["name"]        # Returns sublist with "John"

# Single bracket [] returns sublist
# Double bracket [[]] returns actual element
```

### Important Difference 🌟

| Bracket | Returns |
|---------|---------|
| `my_list[1]` | Sublist containing element |
| `my_list[[1]]` | Actual element |

### Modifying Lists 🌟

```r
# Modify existing element
my_list$age <- 26

# Add new element
my_list$city <- "Mumbai"

# Remove element
my_list$adult <- NULL
```

### Use Cases 🌟
- Store heterogeneous data
- Function outputs (many functions return lists)
- Complex data structures
- Group related but different data

### Lists vs Vectors 🌟

| Feature | Vector | List |
|---------|--------|------|
| **Element types** | Same type only | Mixed types |
| **Flexibility** | Less flexible | More flexible |
| **Use case** | Simple data | Complex structures |

---

## 7. Matrix and Array in R

### Hook 🎯
2D data hai? Matrix use karo! 3D ya n-dimensional? Array use karo! Dono same type ke elements store karte hain.

### Matrix 🌟

**Definition:** 2-dimensional structure with same type elements

**Creating Matrix:**
```r
# matrix(data, nrow, ncol, byrow)
mat <- matrix(1:6, nrow=2, ncol=3)
#      [,1] [,2] [,3]
# [1,]    1    3    5
# [2,]    2    4    6

# With byrow=TRUE
mat2 <- matrix(1:6, nrow=2, ncol=3, byrow=TRUE)
#      [,1] [,2] [,3]
# [1,]    1    2    3
# [2,]    4    5    6
```

**Accessing Elements:**
```r
mat[1,2]    # Row 1, Column 2: 3
mat[2,]     # Entire row 2: 2, 4, 6
mat[,3]     # Entire column 3: 5, 6
```

**Matrix Operations:**
```r
# Matrix multiplication
mat1 %*% mat2

# Transpose
t(mat)

# Determinant
det(mat)
```

**Use Cases:**
- Linear algebra
- Mathematical operations
- 2D data representation

### Array 🌟

**Definition:** Multi-dimensional structure (2D, 3D, or n-dimensional) with same type elements

**Creating Array:**
```r
# array(data, dim=c(rows, cols, tables))
arr <- array(1:24, dim=c(2, 3, 4))
# 2 rows, 3 columns, 4 tables (3D array)
```

**Accessing Elements:**
```r
arr[1,2,3]    # Row 1, Column 2, Table 3
arr[1,,]      # All columns and tables for row 1
```

**Use Cases:**
- Multi-dimensional data
- Image processing (3D arrays for RGB)
- Complex data structures

### Matrix vs Array 🌟

| Feature | Matrix | Array |
|---------|--------|-------|
| **Dimensions** | Always 2D | 2D, 3D, or n-dimensional |
| **Complexity** | Simpler | More complex |
| **Use case** | 2D data | Multi-dimensional data |

### Limitation 🌟
**Both require all elements to be same type** — mixed types nahi chalenge!

---

## 8. Factors in R

### Hook 🎯
Categorical data hai? Survey responses hain? Factors use karo! Memory bhi save hoga, statistical analysis bhi sahi hoga!

### Definition 🌟
> **"Factor is a data structure for categorical variables that stores data with a fixed set of values called levels."**

### Creating Factors 🌟

```r
# Basic factor
gender <- factor(c("Male", "Female", "Male", "Female"))

# Check levels
levels(gender)
# Returns: "Female" "Male"
```

### Ordered Factors 🌟

```r
# When order matters
rating <- factor(
  c("Low", "Medium", "High", "Medium"),
  ordered = TRUE,
  levels = c("Low", "Medium", "High")
)
```

### Uses of Factors 🌟

| Use Case | Description |
|----------|-------------|
| **Statistical Modeling** | ANOVA, regression require categorical variables as factors |
| **Categorical Data** | Survey data, demographic data |
| **Correct Treatment** | R knows it's categorical, not numeric |

### Factor Operations 🌟

```r
# Frequency count
table(gender)

# Summary
summary(gender)

# Convert to numeric codes
as.numeric(gender)
```

### Advantages 🌟

| Advantage | Description |
|-----------|-------------|
| **Memory Efficient** | Store repeated values efficiently |
| **Statistical Analysis** | Enable proper categorical analysis |
| **Data Integrity** | Fixed set of values ensure consistency |

### Important Note 🌟
Factors categorical data ke liye zaroori hain — R ko batate hain ki ye categories hain, numbers nahi!

---

## 9. Data Frame in R

### Hook 🎯
Data frame R ka most important data structure hai! Excel spreadsheet jaisa samjho — rows aur columns, par columns mein different types ho sakte hain!

### Definition 🌟
> **"Data frame is a table-like structure with rows and columns where columns CAN be of DIFFERENT types."**

### Creating Data Frame 🌟

```r
df <- data.frame(
  Name = c("John", "Jane", "Bob"),
  Age = c(25, 30, 28),
  Score = c(85, 92, 88),
  Passed = c(TRUE, TRUE, TRUE)
)
```

**Structure:**
- Rows = observations
- Columns = variables
- Different columns can have different types

### Accessing Data Frame Elements 🌟

```r
# By column
df$Name           # Returns Name column
df[,"Age"]        # Returns Age column

# By row
df[1,]            # First row
df[df$Age>25,]    # Filtered rows

# By cell
df[1,2]           # Row 1, Column 2
```

### Data Frame Operations 🌟

```r
# Dimensions
nrow(df)          # Number of rows
ncol(df)          # Number of columns
dim(df)           # Both dimensions

# Preview
head(df)          # First 6 rows
tail(df)          # Last 6 rows

# Summary
summary(df)       # Statistical summary
str(df)           # Structure information
```

### Data Frame vs Matrix 🌟

| Feature | Data Frame | Matrix |
|---------|-----------|--------|
| **Column types** | Can be different | Must be same |
| **Flexibility** | More flexible | Less flexible |
| **Use case** | Real-world data | Mathematical operations |

### Most Used Data Structure 🌟
- Data analysis
- Statistics
- Machine learning
- Every data science project

**Think of it as:** Excel spreadsheet — data frame!

---

## 10. File Formats and Import/Export

### Hook 🎯
Data kahan se aata hai? CSV, Excel, databases — various formats! R mein import/export kaise karein? Seekhte hain!

### R File Formats 🌟

| Format | Extension | Description | Use Case |
|--------|-----------|-------------|----------|
| **.RData** | .RData | R workspace (multiple objects) | Save/load entire workspace |
| **.rds** | .rds | Single R object | Save/load one object |
| **.csv** | .csv | Comma-separated values | Most common data format |
| **.txt** | .txt | Tab/space delimited | Text data |
| **.xlsx** | .xlsx | Excel files | Excel spreadsheets |

### Importing Data 🌟

```r
# CSV files
df <- read.csv("data.csv")                    # Base R
df <- read_csv("data.csv")                    # readr package (faster)

# Excel files
library(readxl)
df <- read_excel("data.xlsx")

# SPSS files
library(haven)
df <- read_spss("data.sav")

# R workspace
load("workspace.RData")

# Single R object
df <- readRDS("object.rds")
```

### Exporting Data 🌟

```r
# CSV
write.csv(df, "output.csv", row.names=FALSE)

# R workspace
save(df, file="data.RData")

# Single R object
saveRDS(df, "data.rds")

# Excel (needs writexl package)
library(writexl)
write_xlsx(df, "output.xlsx")
```

### Best Practices 🌟

| Practice | Why |
|----------|-----|
| **Use relative paths** | Portable across systems |
| **Check headers** | `header=TRUE/FALSE` |
| **Handle missing values** | `na.strings=c("NA","")` |
| **Specify encoding** | `fileEncoding="UTF-8"` |

---

## 11. Data Visualization in R

### Hook 🎯
R visualization ka powerhouse hai! Base R se lekar GGPLOT2 tak — har type ka chart bana sakte ho!

### Three Main Approaches 🌟

#### 11.1 Base R Graphics 🌟

**Built-in functions:**
```r
# Scatter plot
plot(x, y)

# Bar chart
barplot(height)

# Histogram
hist(data)

# Box plot
boxplot(data)

# Line plot
plot(x, y, type="l")
```

**Advantages:**
- No packages needed
- Quick and simple
- Good for basic plots

#### 11.2 Lattice Package 🌟

**Advanced trellis graphics:**
```r
library(lattice)

# XY plot
xyplot(y ~ x)

# Box-whisker plot
bwplot(y ~ x)

# Histogram
histogram(~ x)
```

**Features:**
- Multi-panel displays
- Conditioning plots
- Publication-quality graphics

#### 11.3 GGPLOT2 Package 🌟

**Most powerful visualization package** — "grammar of graphics"

**Basic Structure:**
```r
library(ggplot2)

# Initialize plot
ggplot(data, aes(x=variable1, y=variable2))

# Add geometric objects
geom_point()      # Scatter plot
geom_bar()        # Bar chart
geom_line()       # Line plot
geom_histogram()  # Histogram
geom_boxplot()    # Box plot

# Customize
labs(title="Title", x="X Label", y="Y Label")
theme_minimal()   # Theme
```

**Example:**
```r
ggplot(mtcars, aes(x=wt, y=mpg)) +
  geom_point() +
  labs(title="Weight vs MPG", x="Weight", y="Miles Per Gallon") +
  theme_minimal()
```

**Advantages:**
- Highly customizable
- Publication-quality
- Consistent grammar
- Most popular in R community

### Comparison 🌟

| Package | Complexity | Flexibility | Use Case |
|---------|-----------|-------------|----------|
| **Base R** | Simple | Limited | Quick plots |
| **Lattice** | Medium | High | Multi-panel |
| **GGPLOT2** | Complex | Very High | Publication-quality |

---

## 12. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Data Types (4)
**"N-I-C-L"** → Numeric, Integer, Character, Logical
→ *"Nice Information Clear Learning"*

### Trick 2: Operator Types (4)
**"A-R-L-A"** → Arithmetic, Relational, Logical, Assignment
→ *"All R coders Love Algorithms"*

### Trick 3: R Objects (6)
**"V-L-M-A-F-D"** → Vector, List, Matrix, Array, Factor, Data frame
→ *"Very Large Maps Aid Finding Directions"*

### Trick 4: Visualization Packages (3)
**"B-L-G"** → Base, Lattice, GGPLOT2
→ *"Big Languages Grow"*

### Trick 5: Assignment Operator
**"Always use <-"** → Left arrow for assignment
→ *"Left Arrow, Right Answer"*

---

## 13. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| `x = 5L` for integer | `x <- 5L` (use `<-` for assignment) |
| Integer without L: `x <- 5` | Integer with L: `x <- 5L` |
| Character without quotes: `x <- hello` | Character with quotes: `x <- "hello"` |
| Mixing types in vector | Use list for mixed types |
| `vec[0]` in R | R is 1-indexed: `vec[1]` |
| Single bracket for list element | Double bracket: `list[[1]]` |
| Matrix with mixed types | Use data frame instead |
| Forgetting `stringsAsFactors=FALSE` | In older R versions |
| Not checking `is.na()` for missing values | Always check for NA |
| Installing package but not loading | Use `library(package)` after install |

---

## 14. 5-Mark Answer Framework

**Q: "Explain data structures in R with examples."** (5 marks)

**Answer Structure:**

**Introduction (1 mark):**
"R provides several data structures to store and manipulate data efficiently."

**Six Data Structures (3 marks):**
1. **Vector:** Same type elements, `c(1,2,3)`
2. **List:** Mixed types, `list(name="John", age=25)`
3. **Matrix:** 2D, same type, `matrix(1:6, nrow=2)`
4. **Array:** Multi-dimensional, `array(1:24, dim=c(2,3,4))`
5. **Factor:** Categorical, `factor(c("Male","Female"))`
6. **Data Frame:** Table-like, mixed types, `data.frame(Name=c("John","Jane"))`

**Comparison (1 mark):**
| Structure | Dimensions | Types |
|-----------|-----------|-------|
| Vector | 1D | Same |
| Matrix | 2D | Same |
| Array | nD | Same |
| List | 1D | Mixed |
| Data Frame | 2D | Mixed |

**Applications (1 mark):**
- Vector: Simple data sequences
- Matrix: Linear algebra
- Data Frame: Real-world datasets
- Factor: Categorical variables

---

## 15. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_EDA_W1_Notes.pdf | Week 1 notes (24 pages) — R introduction, data types, operators, R objects |
| VIT_MSc_Ds_EDA_W1_PPT.pdf | Week 1 PPT (24 pages) — Visual references |
| Martinez et al. Textbook | "Exploratory Data Analysis with MATLAB" — reference |
| Roger Peng Book | "Exploratory Data Analysis with R" — R programming reference |
| Syllabus OLMCA616 | Module 1 scope |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 16. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 1) | Status | Section |
|---------------------------|--------|---------|
| Introduction to R | ✅ | Section 1 |
| Packages and Library | ✅ | Section 11 |
| Data types | ✅ | Section 3 |
| Basic operators | ✅ | Section 4 |
| R objects - Vectors | ✅ | Section 5 |
| R objects - Lists | ✅ | Section 6 |
| R objects - Arrays | ✅ | Section 7 |
| R objects - Matrix | ✅ | Section 7 |
| R objects - Factors | ✅ | Section 8 |
| R objects - Data frame | ✅ | Section 9 |
| R file formats | ✅ | Section 10 |
| Importing and exporting files | ✅ | Section 10 |
| Data Visualization in R | ✅ | Section 11 |
| Lattice package | ✅ | Section 11 |
| Box plot, bar chart, scatter plot | ✅ | Section 11 |
| GGplot2 | ✅ | Section 11 |

### Coverage: 16/16 topics = 100% ✅

---

*Subject: Exploratory Data Analysis (OLMCA616)*
*Unit 1 — Module 1: Introduction to R Programming*
*Last Updated: November 2025 | VIT MCA Semester 3*
