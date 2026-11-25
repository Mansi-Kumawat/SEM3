# EDA Important Topics — Exam Preparation Guide
## OLMCA616 — Exploratory Data Analysis

---

## 📊 Exam Pattern & Weightage

### Section-wise Distribution:

| Section | Type | Total Questions | Marks per Question | Total Marks |
|---------|------|-----------------|-------------------|-------------|
| **Section 1** | Module-wise | 12 questions | 2 marks each | 24 marks |
| **Section 2** | Module-wise | 15 questions | 5 marks each | 75 marks |
| **Section 3** | 1 mark each | 7 questions (attempt 6) | 1 mark each | 6 marks |
| **Total** | | | | **105 marks** |

### Module-wise Weightage:

| Module | Section 1 (2 marks) | Section 2 (5 marks) | Section 3 (1 mark) | Total Questions | Priority |
|--------|---------------------|---------------------|-------------------|-----------------|----------|
| **Module 1** | 1 | 2 | 1 | 4 | Normal |
| **Module 2** | 2 | 2 | 1 | 5 | Normal |
| **Module 3** | 2 | 2 | 1 | 5 | Normal |
| **Module 4** | 1 | **3** | 1 | 5 | 🔥 **HIGH** |
| **Module 5** | 2 | 2 | 1 | 5 | Normal |
| **Module 6** | 1 | 2 | 1 | 4 | Normal |
| **Module 7** | 1 | 2 | 1 | 4 | Normal |

### 🎯 Key Insights:
- **Module 4 is MOST IMPORTANT** — 3 questions in Section 2, expected 6-mark question
- **Section 2 carries maximum marks** (75 marks) — focus on 5-mark answers
- **Section 3** — all 7 modules equal weightage, attempt any 6

---

# MODULE 1: Introduction to R Programming

## Important Topics:
1. Data Types
2. Data Structures
3. Data Construction
4. Loops
5. Conditional Statements

---

## 1. Data Types in R

### Official Definition 🌟
> **"Data types in R specify the kind of value a variable can hold and determine what operations can be performed on that data."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Specify the kind of value"** — Variable mein kis type ka data rakh sakte hain
- **"Determine what operations"** — Kis type ke operations perform kar sakte hain (mathematical, logical, etc.)

### Types of Data Types 🌟

| Data Type | Description | Example | Operations |
|-----------|-------------|---------|------------|
| **Numeric** | Decimal numbers | 3.14, 2.5, 10.7 | All math operations |
| **Integer** | Whole numbers (with L suffix) | 5L, 10L, 100L | All math operations |
| **Character** | Text strings | "hello", "R programming" | Concatenation, comparison |
| **Logical** | Boolean values | TRUE, FALSE | AND, OR, NOT |
| **Complex** | Complex numbers | 3 + 2i | Complex arithmetic |

### Code Examples 🌟
```r
# Numeric
x <- 3.14
class(x)  # "numeric"

# Integer (L suffix zaroori!)
y <- 5L
class(y)  # "integer"

# Character
name <- "John"
class(name)  # "character"

# Logical
flag <- TRUE
class(flag)  # "logical"
```

### Exam-Ready Points 📝
- R has 5 basic data types
- Integer ke liye **L suffix** zaroori hai (5L, not 5)
- Character ke liye **quotes** zaroori hain
- Logical values: TRUE/FALSE (capital letters)
- Use `class()` function to check data type

---

## 2. Data Structures in R

### Official Definition 🌟
> **"Data structures in R are objects that store and organize data in different formats, each with specific characteristics and use cases."**

### Six Basic Data Structures 🌟

| Structure | Dimensions | Type | Use Case |
|-----------|-----------|------|----------|
| **Vector** | 1D | Same type | Simple sequences |
| **List** | 1D | Mixed types | Heterogeneous data |
| **Matrix** | 2D | Same type | Linear algebra |
| **Array** | nD | Same type | Multi-dimensional data |
| **Factor** | 1D | Categorical | Statistical modeling |
| **Data Frame** | 2D | Mixed types | Real-world datasets |

### Detailed Explanation 🌟

**1. Vector:**
```r
# Same type elements only
num_vec <- c(1, 2, 3, 4, 5)
char_vec <- c("a", "b", "c")
```
- Most basic data structure
- All elements must be same type
- Created using `c()` function

**2. List:**
```r
# Mixed types allowed
my_list <- list(name="John", age=25, scores=c(85, 90, 92))
```
- Can store different types
- Flexible structure
- Access using `[[]]` or `$`

**3. Matrix:**
```r
# 2D, same type
mat <- matrix(1:6, nrow=2, ncol=3)
```
- Two dimensions (rows × columns)
- All elements same type
- Created using `matrix()` function

**4. Array:**
```r
# n-dimensional, same type
arr <- array(1:24, dim=c(2, 3, 4))
```
- Can have any number of dimensions
- All elements same type
- Generalization of matrix

**5. Factor:**
```r
# Categorical data
gender <- factor(c("Male", "Female", "Male"))
```
- For categorical variables
- Stores levels
- Important for statistical models

**6. Data Frame:**
```r
# Table-like, mixed types
df <- data.frame(
  Name = c("John", "Jane"),
  Age = c(25, 30),
  Score = c(85, 92)
)
```
- Most used structure
- Rows = observations, Columns = variables
- Different columns can have different types
- Like Excel spreadsheet

### Exam-Ready Points 📝
- Vector = 1D, same type
- List = 1D, mixed type
- Matrix = 2D, same type
- Data Frame = 2D, mixed type (most important!)
- Factor = categorical data ke liye

---

## 3. Data Construction

### Official Definition 🌟
> **"Data construction refers to the process of creating and populating data structures with values in R programming."**

### Methods of Data Construction 🌟

**1. Using c() function:**
```r
# Vector creation
vec <- c(1, 2, 3, 4, 5)
```

**2. Using sequence operators:**
```r
# Sequence
seq_vec <- 1:10  # 1, 2, 3, ..., 10
seq_vec <- seq(1, 10, by=2)  # 1, 3, 5, 7, 9
```

**3. Using rep() function:**
```r
# Repeat values
rep_vec <- rep(5, times=3)  # 5, 5, 5
rep_vec <- rep(c(1, 2), each=3)  # 1, 1, 1, 2, 2, 2
```

**4. Using matrix():**
```r
# Matrix creation
mat <- matrix(1:6, nrow=2, ncol=3, byrow=TRUE)
```

**5. Using data.frame():**
```r
# Data frame creation
df <- data.frame(
  col1 = c(1, 2, 3),
  col2 = c("a", "b", "c")
)
```

**6. Using list():**
```r
# List creation
my_list <- list(a=1, b="text", c=TRUE)
```

### Exam-Ready Points 📝
- `c()` — combine values into vector
- `seq()` — create sequences
- `rep()` — repeat values
- `matrix()` — create 2D structure
- `data.frame()` — create table structure
- `list()` — create mixed-type collection

---

## 4. Loops in R

### Official Definition 🌟
> **"Loops in R are control structures that allow repeated execution of a block of code multiple times."**

### Types of Loops 🌟

**1. for Loop:**
```r
# When number of iterations known
for (i in 1:5) {
  print(i)
}
```
- Use when iterations count known
- Iterates over sequence/vector

**2. while Loop:**
```r
# When condition-based iteration
count <- 1
while (count <= 5) {
  print(count)
  count <- count + 1
}
```
- Use when condition-based
- Runs until condition becomes FALSE

**3. repeat Loop:**
```r
# Infinite loop with break
count <- 1
repeat {
  print(count)
  count <- count + 1
  if (count > 5) break
}
```
- Runs infinitely until `break`
- Must have exit condition

### Loop Control Statements 🌟

| Statement | Purpose | Example |
|-----------|---------|---------|
| **break** | Exit loop immediately | `if (x > 10) break` |
| **next** | Skip to next iteration | `if (x == 5) next` |

### Exam-Ready Points 📝
- **for** — known iterations
- **while** — condition-based
- **repeat** — infinite, needs break
- Use `break` to exit, `next` to skip

---

## 5. Conditional Statements

### Official Definition 🌟
> **"Conditional statements in R allow execution of different code blocks based on whether a condition is TRUE or FALSE."**

### Types of Conditional Statements 🌟

**1. if Statement:**
```r
if (condition) {
  # code if TRUE
}
```

**2. if-else Statement:**
```r
if (condition) {
  # code if TRUE
} else {
  # code if FALSE
}
```

**3. if-else if-else Statement:**
```r
if (condition1) {
  # code if condition1 TRUE
} else if (condition2) {
  # code if condition2 TRUE
} else {
  # code if all FALSE
}
```

**4. switch Statement:**
```r
result <- switch(
  expression,
  case1 = "value1",
  case2 = "value2",
  "default"
)
```

### Example 🌟
```r
# Grade calculation
marks <- 75

if (marks >= 90) {
  grade <- "A"
} else if (marks >= 80) {
  grade <- "B"
} else if (marks >= 70) {
  grade <- "C"
} else {
  grade <- "F"
}
print(grade)  # "C"
```

### Exam-Ready Points 📝
- **if** — single condition
- **if-else** — two branches
- **if-else if-else** — multiple conditions
- **switch** — multiple case selection
- Conditions must evaluate to TRUE/FALSE

---

# MODULE 2: Data Evolution

## Important Topics:
1. Nominal Data
2. Ordinal Data
3. Categorical Data
4. Qualitative Data
5. Quantitative Data
6. Discrete Data
7. Continuous Data
8. Sources of Data

---

## 1. Nominal Data

### Official Definition 🌟
> **"Nominal data is a type of categorical data where variables are divided into categories without any natural ordering or ranking."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Categorical data"** — Categories mein divided hai
- **"Without any natural ordering"** — Koi natural order nahi hai (ek dusre se bada/chhota nahi)

### Characteristics 🌟
- No inherent order
- Categories are mutually exclusive
- Can't perform mathematical operations
- Mode can be calculated (not mean/median)

### Examples 🌟
| Variable | Categories |
|----------|-----------|
| **Gender** | Male, Female, Other |
| **Blood Type** | A, B, AB, O |
| **City** | Delhi, Mumbai, Jaipur |
| **Color** | Red, Blue, Green |

### Analysis Methods 🌟
- **Frequency table** — count of each category
- **Mode** — most frequent category
- **Chi-square test** — test independence
- **Bar chart, Pie chart** — visualization

### Exam-Ready Points 📝
- Nominal = categories, NO order
- Example: Gender, Blood type
- Can't say Male > Female
- Use frequency table, mode

---

## 2. Ordinal Data

### Official Definition 🌟
> **"Ordinal data is a type of categorical data where categories have a natural ordering or ranking, but the intervals between categories are not necessarily equal."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Natural ordering or ranking"** — Categories ka ek order hai (chhota se bada)
- **"Intervals not necessarily equal"** — Par difference equal nahi hota

### Characteristics 🌟
- Has natural order/ranking
- Intervals between categories unknown/unequal
- Can determine greater/less than
- Median and mode can be calculated

### Examples 🌟
| Variable | Categories (Ordered) |
|----------|---------------------|
| **Education** | High School < Bachelor < Master < PhD |
| **Satisfaction** | Very Dissatisfied < Dissatisfied < Neutral < Satisfied < Very Satisfied |
| **Pain Level** | None < Mild < Moderate < Severe |
| **Grade** | F < D < C < B < A |

### Analysis Methods 🌟
- **Median** — middle value
- **Mode** — most frequent
- **Percentiles, Quartiles**
- **Bar chart** (ordered)

### Comparison: Nominal vs Ordinal 🌟

| Feature | Nominal | Ordinal |
|---------|---------|---------|
| **Order** | No order | Has order |
| **Example** | Gender | Education level |
| **Comparison** | Equal/Not equal | Greater/Less than |
| **Central Tendency** | Mode | Mode, Median |

### Exam-Ready Points 📝
- Ordinal = categories WITH order
- Example: Education, Satisfaction
- Can say PhD > Bachelor
- But can't say how much greater
- Use median, mode

---

## 3. Categorical Data

### Official Definition 🌟
> **"Categorical data represents characteristics or qualities that can be divided into groups or categories. It describes qualities rather than quantities."**

### Types of Categorical Data 🌟

| Type | Order | Example |
|------|-------|---------|
| **Nominal** | No order | Gender, Color |
| **Ordinal** | Has order | Education, Rating |

### Characteristics 🌟
- Represents qualities, not quantities
- Finite set of categories
- Can be numeric or text
- Used for classification

### Examples 🌟
- **Nominal:** Country, Marital Status, Brand
- **Ordinal:** Customer Rating, Severity Level

### In R: Factors 🌟
```r
# Create categorical variable
gender <- factor(c("Male", "Female", "Male", "Female"))

# Ordered factor
rating <- factor(c("Low", "Medium", "High"), 
                 ordered = TRUE,
                 levels = c("Low", "Medium", "High"))
```

### Exam-Ready Points 📝
- Categorical = qualitative data
- Two types: Nominal (no order), Ordinal (has order)
- Use factors in R
- Frequency table, bar chart for analysis

---

## 4. Qualitative Data

### Official Definition 🌟
> **"Qualitative data is descriptive information that captures qualities, characteristics, or attributes. It is non-numerical and categorical in nature."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Descriptive information"** — Qualities describe karta hai
- **"Non-numerical"** — Numbers mein nahi hota
- **"Categorical"** — Categories mein divided hota hai

### Characteristics 🌟
- Describes qualities/attributes
- Non-numerical (usually)
- Subjective interpretation
- Difficult to quantify

### Types 🌟
| Type | Description | Example |
|------|-------------|---------|
| **Nominal** | No order | Gender, Color |
| **Ordinal** | Has order | Satisfaction level |

### Examples 🌟
- Customer feedback (good, bad, average)
- Interview responses
- Observations
- Opinions

### Data Collection Methods 🌟
- Interviews
- Observations
- Open-ended surveys
- Focus groups

### Analysis Methods 🌟
- Content analysis
- Thematic analysis
- Frequency counts
- Cross-tabulation

### Exam-Ready Points 📝
- Qualitative = descriptive, non-numerical
- Also called categorical data
- Types: Nominal, Ordinal
- Difficult to analyze statistically
- Use frequency, mode

---

## 5. Quantitative Data

### Official Definition 🌟
> **"Quantitative data is numerical information that can be measured and expressed in numbers. It represents quantities and can be subjected to mathematical operations."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Numerical information"** — Numbers mein hota hai
- **"Can be measured"** — Measure kar sakte hain
- **"Mathematical operations"** — Add, subtract, average — sab possible

### Types of Quantitative Data 🌟

| Type | Description | Values | Example |
|------|-------------|--------|---------|
| **Discrete** | Countable | Whole numbers only | Number of students (30, not 30.5) |
| **Continuous** | Measurable | Any value in range | Height (5.8 ft, 5.81 ft, any precision) |

### Characteristics 🌟
- Numerical values
- Can perform arithmetic operations
- Objective measurement
- Statistical analysis possible

### Examples 🌟
**Discrete:**
- Number of children in family (0, 1, 2, 3...)
- Number of cars in parking
- Number of defects

**Continuous:**
- Height (5.8 ft, 5.812 ft)
- Weight (65.5 kg)
- Temperature (37.2°C)
- Time (2.5 hours)

### Analysis Methods 🌟
- Mean, Median, Mode
- Standard Deviation, Variance
- Correlation, Regression
- T-test, ANOVA

### Comparison: Discrete vs Continuous 🌟

| Feature | Discrete | Continuous |
|---------|----------|------------|
| **Values** | Countable, whole numbers | Measurable, any value |
| **Gaps** | Gaps between values | No gaps |
| **Example** | Students: 30 | Height: 5.812 ft |
| **Counting** | Can count | Can measure |

### Exam-Ready Points 📝
- Quantitative = numerical data
- Two types: Discrete (countable), Continuous (measurable)
- Discrete: Number of students
- Continuous: Height, weight, temperature
- Can calculate mean, SD, etc.

---

## 6. Discrete Data

### Official Definition 🌟
> **"Discrete data is quantitative data that can only take specific, separate values. It is countable and typically represented by whole numbers."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Specific, separate values"** — Fixed values hi le sakta hai
- **"Countable"** — Gin sakte hain
- **"Whole numbers"** — Usually integers hote hain

### Characteristics 🌟
- Countable values
- Gaps between possible values
- Cannot take fractional values
- Finite or countably infinite

### Examples 🌟
| Variable | Possible Values | Why Discrete? |
|----------|----------------|---------------|
| **Number of students** | 0, 1, 2, 3, ... | Can't have 30.5 students |
| **Number of cars** | 0, 1, 2, 3, ... | Can't have 2.3 cars |
| **Number of defects** | 0, 1, 2, 3, ... | Countable |
| **Dice roll** | 1, 2, 3, 4, 5, 6 | Only these 6 values |

### Visualization 🌟
- **Bar chart** — for discrete variables
- **Histogram** — with gaps between bars

### Statistical Measures 🌟
- Mean (if meaningful)
- Median
- Mode
- Variance, Standard Deviation

### Exam-Ready Points 📝
- Discrete = countable, whole numbers
- Example: Number of students, cars
- Can't be 30.5 students
- Gaps between values
- Use bar chart

---

## 7. Continuous Data

### Official Definition 🌟
> **"Continuous data is quantitative data that can take any value within a given range. It is measurable and can include fractional or decimal values."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Any value within a range"** — Range mein koi bhi value le sakta hai
- **"Measurable"** — Measure karte hain
- **"Fractional or decimal"** — Decimals bhi ho sakte hain

### Characteristics 🌟
- Measurable values
- No gaps between possible values
- Can take infinite values in range
- Precision depends on measurement tool

### Examples 🌟
| Variable | Possible Values | Why Continuous? |
|----------|----------------|-----------------|
| **Height** | 5.8 ft, 5.81 ft, 5.812 ft, ... | Any value possible |
| **Weight** | 65.5 kg, 65.53 kg, ... | Any precision |
| **Temperature** | 37.2°C, 37.25°C, ... | Continuous scale |
| **Time** | 2.5 hours, 2.53 hours, ... | Continuous |

### Visualization 🌟
- **Histogram** — continuous distribution
- **Line chart** — trends over continuous variable
- **Box plot** — spread and outliers

### Statistical Measures 🌟
- Mean, Median, Mode
- Standard Deviation, Variance
- Range, IQR
- Correlation, Regression

### Comparison: Discrete vs Continuous 🌟

| Feature | Discrete | Continuous |
|---------|----------|------------|
| **Values** | Separate, countable | Any value in range |
| **Decimals** | Usually no | Yes |
| **Gaps** | Yes | No |
| **Example** | Students: 30 | Height: 5.812 ft |
| **Measurement** | Counting | Measuring |

### Exam-Ready Points 📝
- Continuous = measurable, any value
- Example: Height, weight, temperature
- Can have decimals (5.812 ft)
- No gaps between values
- Use histogram, line chart

---

## 8. Sources of Data

### Official Definition 🌟
> **"Data sources refer to the origins or locations from which data is collected or obtained for analysis."**

### Types of Data Sources 🌟

| Source | Description | Example |
|--------|-------------|---------|
| **Primary Sources** | Data collected firsthand | Surveys, experiments |
| **Secondary Sources** | Data collected by others | Published reports, databases |

### Detailed Sources 🌟

**1. Surveys & Questionnaires:**
- Collect data directly from respondents
- Structured questions
- Example: Customer satisfaction survey

**2. Experiments:**
- Controlled environment
- Cause-effect relationships
- Example: Drug testing

**3. Observational Studies:**
- Observe without intervention
- Natural settings
- Example: Wildlife observation

**4. Databases:**
- Structured data storage
- Query-based access
- Example: SQL databases

**5. Published Sources:**
- Books, journals, reports
- Government publications
- Example: Census data

**6. Online Sources:**
- Websites, APIs
- Social media
- Example: Twitter data

**7. Sensors & IoT:**
- Automated data collection
- Real-time data
- Example: Temperature sensors

### Choosing Data Source 🌟

| Factor | Consideration |
|--------|---------------|
| **Accuracy** | How reliable is the source? |
| **Cost** | Budget constraints |
| **Time** | How quickly needed? |
| **Relevance** | Matches research question? |
| **Accessibility** | Can you access it? |

### Exam-Ready Points 📝
- Primary = collect yourself (surveys, experiments)
- Secondary = use others' data (reports, databases)
- Choose based on accuracy, cost, time
- Always check source reliability

---

# MODULE 3: Data Pre-processing

## Important Topics:
1. Types of Data Processing (Four Types)
2. Missing Data
3. Advantages and Limitations
4. Imputation Methods
5. Regression Methods

---

## 1. Types of Data Processing (Four Types)

### Official Definition 🌟
> **"Data processing refers to the manipulation of raw data to produce meaningful information. There are four main types of data processing techniques."**

### Four Types of Data Processing 🌟

**1. Data Cleaning:**

**Definition:** Process of identifying and correcting errors, inconsistencies, and inaccuracies in data.

**Activities:**
- Handle missing values
- Remove duplicates
- Correct errors
- Standardize formats

**Example:**
```r
# Remove duplicates
data <- unique(data)

# Handle missing values
data$age[is.na(data$age)] <- mean(data$age, na.rm=TRUE)
```

**2. Data Integration:**

**Definition:** Combining data from multiple sources into a unified dataset.

**Activities:**
- Merge datasets
- Resolve conflicts
- Remove redundancy
- Schema mapping

**Example:**
```r
# Merge two datasets
merged_data <- merge(df1, df2, by="ID")
```

**3. Data Transformation:**

**Definition:** Converting data from one format or structure into another.

**Activities:**
- Normalization
- Aggregation
- Discretization
- Feature extraction

**Example:**
```r
# Normalization
normalized_data <- scale(data)
```

**4. Data Reduction:**

**Definition:** Reducing the volume of data while maintaining its essential information.

**Activities:**
- Dimensionality reduction
- Feature selection
- Sampling
- Aggregation

**Example:**
```r
# PCA for dimensionality reduction
pca_result <- prcomp(data, scale=TRUE)
```

### Comparison Table 🌟

| Type | Purpose | Techniques | Example |
|------|---------|------------|---------|
| **Cleaning** | Fix errors | Handle missing, remove duplicates | Remove NA values |
| **Integration** | Combine sources | Merge, join | Combine customer databases |
| **Transformation** | Change format | Normalize, aggregate | Scale data 0-1 |
| **Reduction** | Reduce volume | PCA, feature selection | Reduce 100 features to 10 |

### Exam-Ready Points 📝
- 4 types: Cleaning, Integration, Transformation, Reduction
- Cleaning = fix errors
- Integration = combine sources
- Transformation = change format
- Reduction = reduce volume

---

## 2. Missing Data

### Official Definition 🌟
> **"Missing data refers to the absence of values for certain observations or variables in a dataset, which can occur due to various reasons and can impact analysis results."**

### Causes of Missing Data 🌟

| Cause | Description | Example |
|-------|-------------|---------|
| **Non-response** | Participants skip questions | Survey: income question skipped |
| **Equipment failure** | Technical issues | Sensor malfunction |
| **Data entry errors** | Human mistakes | Forgot to enter value |
| **Attrition** | Participants drop out | Long-term study: people leave |

### Types of Missing Data 🌟

**1. MCAR (Missing Completely at Random):**

**Definition:** Missingness is completely random, unrelated to any variable.

**Characteristics:**
- No pattern
- Unrelated to observed or unobserved data
- Analysis remains unbiased

**Example:** Lab equipment randomly fails

**2. MAR (Missing at Random):**

**Definition:** Missingness is related to observed variables, not the missing values themselves.

**Characteristics:**
- Pattern exists but can be explained by other variables
- Can be handled using observed data

**Example:** Men less likely to report depression (related to gender, not depression level)

**3. MNAR (Missing Not at Random):**

**Definition:** Missingness is related to the missing values themselves.

**Characteristics:**
- Pattern related to unobserved data
- Most difficult to handle
- Can bias results

**Example:** Drug users skip drug survey (missing because of drug use)

### Impact of Missing Data 🌟

| Impact | Description |
|--------|-------------|
| **Bias** | Results may be inaccurate |
| **Reduced Power** | Harder to detect effects |
| **Decreased Precision** | Estimates less precise |
| **Invalid Conclusions** | Wrong interpretations |

### Detection Methods 🌟
```r
# Check missing values
is.na(data)

# Count missing per column
colSums(is.na(data))

# Visualize
library(mice)
md.pattern(data)
```

### Exam-Ready Points 📝
- Missing data = absent values
- Causes: non-response, equipment failure, errors
- 3 types: MCAR (random), MAR (related to observed), MNAR (related to missing)
- Impact: bias, reduced power, invalid conclusions
- Always check for missing data before analysis

---

## 3. Advantages and Limitations of Missing Data Methods

### Advantages 🌟

| Method | Advantage |
|--------|-----------|
| **Deletion** | Simple, quick |
| **Mean Imputation** | Easy to implement |
| **Regression Imputation** | Uses relationships |
| **Multiple Imputation** | Accounts for uncertainty |

### Limitations 🌟

| Method | Limitation |
|--------|------------|
| **Deletion** | Loss of information, bias if not MCAR |
| **Mean Imputation** | Reduces variance, distorts distribution |
| **Regression Imputation** | Overestimates relationships |
| **Multiple Imputation** | Complex, computationally intensive |

### Comparison Table 🌟

| Method | Advantage | Limitation | When to Use |
|--------|-----------|------------|-------------|
| **Listwise Deletion** | Simple | Loses data | MCAR, small missing % |
| **Mean Imputation** | Easy | Reduces variance | Quick fix, not for publication |
| **Regression** | Uses relationships | Overestimates | Strong relationships |
| **Multiple Imputation** | Accounts for uncertainty | Complex | Best practice |

### Exam-Ready Points 📝
- No single best method
- Choose based on missing data type (MCAR/MAR/MNAR)
- Multiple imputation = gold standard
- Always report how missing data handled

---

## 4. Imputation Methods

### Official Definition 🌟
> **"Imputation is the process of replacing missing data with substituted values. It estimates missing values based on available data."**

### Types of Imputation Methods 🌟

**1. Mean/Median/Mode Imputation:**

**Definition:** Replace missing values with mean (numeric), median (skewed), or mode (categorical).

**Example:**
```r
# Mean imputation
data$age[is.na(data$age)] <- mean(data$age, na.rm=TRUE)
```

**Advantages:**
- Simple
- Quick
- Preserves sample size

**Disadvantages:**
- Reduces variance
- Distorts distribution
- Underestimates standard errors

**2. Hot-Deck Imputation:**

**Definition:** Replace missing values with values from similar cases (donors) in the current dataset.

**Process:**
1. Identify similar cases
2. Randomly select donor
3. Copy value from donor

**Advantages:**
- Preserves distribution
- Uses actual observed values

**Disadvantages:**
- Requires similar cases
- Computationally intensive

**3. Cold-Deck Imputation:**

**Definition:** Replace missing values with values from external sources or previous studies.

**Process:**
1. Find external source with similar variable
2. Use value from that source

**Advantages:**
- Uses external information
- Can be accurate

**Disadvantages:**
- External source may not match
- Less reliable

**4. Regression Imputation:**

**Definition:** Predict missing values using regression model based on other variables.

**Example:**
```r
# Predict age from income
model <- lm(age ~ income, data=data)
data$age[is.na(data$age)] <- predict(model, newdata=data[is.na(data$age),])
```

**Advantages:**
- Uses relationships
- More accurate than mean

**Disadvantages:**
- Overestimates relationships
- Perfect correlation assumed

**5. Stochastic Regression Imputation:**

**Definition:** Regression imputation + random error component.

**Process:**
1. Predict using regression
2. Add random error
3. More realistic than pure regression

**Advantages:**
- More realistic
- Preserves variance

**Disadvantages:**
- Random component
- Results vary

**6. Multiple Imputation:**

**Definition:** Create multiple datasets with different imputed values, analyze each, then combine results.

**Process:**
1. Create m datasets (usually 5-20)
2. Impute missing values differently in each
3. Analyze each dataset
4. Pool results

**Example:**
```r
library(mice)
imputed_data <- mice(data, m=5)
pooled_results <- pool(with(imputed_data, lm(y ~ x)))
```

**Advantages:**
- Accounts for uncertainty
- Valid statistical inference
- Gold standard

**Disadvantages:**
- Complex
- Computationally intensive

### Comparison Table 🌟

| Method | Complexity | Accuracy | When to Use |
|--------|-----------|----------|-------------|
| **Mean/Median** | Low | Low | Quick fix |
| **Hot-Deck** | Medium | Medium | Similar cases available |
| **Cold-Deck** | Low | Medium | External source reliable |
| **Regression** | Medium | High | Strong relationships |
| **Stochastic** | Medium | High | Preserve variance |
| **Multiple** | High | Highest | Best practice |

### Exam-Ready Points 📝
- Imputation = replace missing values
- Methods: Mean, Hot-deck, Cold-deck, Regression, Stochastic, Multiple
- Multiple imputation = best method
- Choose based on data, missing mechanism, resources

---

## 5. Regression Methods for Missing Data

### Official Definition 🌟
> **"Regression methods for missing data use statistical relationships between variables to predict and impute missing values."**

### Types of Regression Methods 🌟

**1. Simple Regression Imputation:**

**Definition:** Use one predictor variable to predict missing values.

**Formula:**
```
Y_missing = b0 + b1 * X
```

**Example:**
- Predict missing height from weight
- height = 50 + 0.5 * weight

**Advantages:**
- Simple
- Uses relationship

**Disadvantages:**
- Only one predictor
- May not be accurate

**2. Multiple Regression Imputation:**

**Definition:** Use multiple predictor variables to predict missing values.

**Formula:**
```
Y_missing = b0 + b1*X1 + b2*X2 + ... + bn*Xn
```

**Example:**
- Predict missing income from education, experience, age
- income = 20000 + 5000*education + 1000*experience + 200*age

**Advantages:**
- More accurate
- Uses multiple relationships

**Disadvantages:**
- Complex
- Requires complete data for predictors

**3. Logistic Regression Imputation:**

**Definition:** Use logistic regression for categorical missing values.

**Formula:**
```
P(Y=1) = 1 / (1 + e^-(b0 + b1*X1 + ... + bn*Xn))
```

**Example:**
- Predict missing gender (Male/Female) from other variables

**Advantages:**
- For categorical variables
- Probabilistic

**Disadvantages:**
- Binary outcome only
- Complex

### Steps in Regression Imputation 🌟

1. **Identify missing values**
2. **Select predictor variables**
3. **Build regression model** using complete cases
4. **Predict missing values**
5. **Replace missing values** with predictions

### Example in R 🌟
```r
# Data with missing values
data <- data.frame(
  age = c(25, 30, NA, 35, 40),
  income = c(30000, 40000, 50000, 60000, 70000)
)

# Build model using complete cases
model <- lm(income ~ age, data=data, na.action=na.exclude)

# Predict missing age
missing_rows <- is.na(data$age)
data$age[missing_rows] <- predict(model, newdata=data[missing_rows,])
```

### Advantages & Limitations 🌟

**Advantages:**
- Uses relationships between variables
- More accurate than mean imputation
- Preserves correlations

**Limitations:**
- Assumes linear relationships
- Overestimates relationships
- Requires complete data for predictors
- May not capture complex patterns

### Exam-Ready Points 📝
- Regression methods use relationships to predict missing values
- Simple regression = one predictor
- Multiple regression = multiple predictors
- Logistic regression = categorical outcome
- Steps: identify missing, build model, predict, replace
- Advantage: uses relationships
- Limitation: assumes linearity, overestimates

---

# MODULE 4: Data Analysis 🔥 HIGH PRIORITY

## Important Topics:
1. Definition of Data Analysis
2. Measures of Central Tendency
3. Variance
4. Standard Deviation
5. Z-Score

**⚠️ IMPORTANT: Module 4 has highest weightage in Section 2 (3 questions, expected 6-mark question)**

---

## 1. Definition of Data Analysis

### Official Definition 🌟
> **"Data analysis is the process of inspecting, cleaning, transforming, and modeling data with the goal of discovering useful information, informing conclusions, and supporting decision-making."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Inspecting"** — Data ko carefully dekhna, examine karna
- **"Cleaning"** — Errors, missing values, inconsistencies fix karna
- **"Transforming"** — Data ka format change karna (normalization, etc.)
- **"Modeling"** — Statistical/mathematical models apply karna
- **"Discovering useful information"** — Patterns, trends, insights find karna
- **"Informing conclusions"** — Results se conclusions nikalna
- **"Supporting decision-making"** — Better decisions lene mein help karna

### Core Concept 🌟

**Data Analysis Process:**

```
Raw Data → Inspect → Clean → Transform → Model → Analyze → Insights → Decisions
```

### Types of Data Analysis 🌟

| Type | Purpose | Example |
|------|---------|---------|
| **Descriptive** | What happened? | Sales report last month |
| **Diagnostic** | Why did it happen? | Why sales dropped? |
| **Predictive** | What will happen? | Forecast next month sales |
| **Prescriptive** | What should we do? | Recommended actions |

### Applications 🌟

| Domain | Use Case |
|--------|----------|
| **Business** | Sales analysis, customer behavior |
| **Healthcare** | Disease prediction, treatment effectiveness |
| **Finance** | Risk assessment, stock prediction |
| **Marketing** | Campaign effectiveness, customer segmentation |
| **Manufacturing** | Quality control, defect detection |

### Importance 🌟
- Converts raw data into actionable insights
- Supports evidence-based decision making
- Identifies patterns and trends
- Helps in problem-solving
- Reduces uncertainty

### Exam-Ready Points 📝 (6 Marks)

**Q: "Define data analysis and explain its types with examples."**

**Answer Structure:**

**Definition (2 marks):**
"Data analysis is the process of inspecting, cleaning, transforming, and modeling data with the goal of discovering useful information, informing conclusions, and supporting decision-making."

**Types (3 marks):**
1. **Descriptive Analysis** — What happened? Summarizes historical data. Example: Monthly sales report showing total revenue.

2. **Diagnostic Analysis** — Why did it happen? Identifies causes. Example: Analyzing why sales dropped in March.

3. **Predictive Analysis** — What will happen? Forecasts future. Example: Predicting next quarter sales.

4. **Prescriptive Analysis** — What should we do? Recommends actions. Example: Suggesting marketing strategies to increase sales.

**Importance (1 mark):**
- Converts data to insights
- Supports decision-making
- Identifies patterns
- Reduces uncertainty

---

## 2. Measures of Central Tendency

### Official Definition 🌟
> **"Measures of central tendency are statistical measures that identify a single value as representative of an entire distribution, indicating the center or typical value of a dataset."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Identify a single value"** — Ek value jo pura dataset represent kare
- **"Representative of entire distribution"** — Pura data kaisa hai, wo bataye
- **"Center or typical value"** — Middle value ya most common value

### Three Main Measures 🌟

#### A. Mean (Average)

**Definition:**
> **"Mean is the sum of all values divided by the number of values."**

**Formula:**
```
Mean (x̄) = (Σx) / n = (x₁ + x₂ + ... + xₙ) / n
```

**Where:**
- Σx = sum of all values
- n = number of values

**Example:**
```
Data: 10, 20, 30, 40, 50
Mean = (10 + 20 + 30 + 40 + 50) / 5 = 150 / 5 = 30
```

**Properties:**
- Uses all values
- Affected by outliers
- Best for symmetric distributions
- Sensitive to extreme values

**When to Use:**
- Numeric data
- No extreme outliers
- Symmetric distribution

**In R:**
```r
data <- c(10, 20, 30, 40, 50)
mean(data)  # 30
```

#### B. Median

**Definition:**
> **"Median is the middle value when data is arranged in order. It divides the dataset into two equal halves."**

**How to Calculate:**
1. Sort data in ascending order
2. If n is odd: Median = middle value
3. If n is even: Median = average of two middle values

**Examples:**

**Odd number of values:**
```
Data: 10, 20, 30, 40, 50 (n=5, odd)
Sorted: 10, 20, 30, 40, 50
Median = 30 (middle value)
```

**Even number of values:**
```
Data: 10, 20, 30, 40 (n=4, even)
Sorted: 10, 20, 30, 40
Median = (20 + 30) / 2 = 25
```

**Properties:**
- Not affected by outliers
- Robust measure
- Best for skewed distributions
- May not be actual data value (for even n)

**When to Use:**
- Skewed data
- Outliers present
- Ordinal data

**In R:**
```r
data <- c(10, 20, 30, 40, 50)
median(data)  # 30
```

#### C. Mode

**Definition:**
> **"Mode is the value that occurs most frequently in a dataset."**

**Example:**
```
Data: 1, 2, 2, 3, 3, 3, 4, 5
Mode = 3 (occurs 3 times, most frequent)
```

**Types:**
- **Unimodal:** One mode
- **Bimodal:** Two modes
- **Multimodal:** Multiple modes
- **No mode:** All values occur equally

**Properties:**
- Can be used for categorical data
- Not affected by outliers
- May not exist (all values unique)
- May have multiple modes

**When to Use:**
- Categorical data
- Most frequent category needed
- Nominal data

**In R:**
```r
data <- c(1, 2, 2, 3, 3, 3, 4, 5)
# R doesn't have built-in mode function
names(sort(-table(data)))[1]  # "3"
```

### Comparison Table 🌟

| Measure | Definition | Formula/Method | Best For | Outliers | Data Type |
|---------|-----------|----------------|----------|----------|-----------|
| **Mean** | Average | Σx / n | Symmetric, numeric | Affected | Numeric |
| **Median** | Middle value | Middle of sorted data | Skewed, outliers | Not affected | Numeric, Ordinal |
| **Mode** | Most frequent | Most common value | Categorical | Not affected | Any |

### Relationship in Different Distributions 🌟

| Distribution | Relationship |
|--------------|--------------|
| **Symmetric** | Mean = Median = Mode |
| **Positively Skewed** | Mean > Median > Mode |
| **Negatively Skewed** | Mean < Median < Mode |

### Exam-Ready Points 📝 (5 Marks)

**Q: "Explain measures of central tendency with formulas and examples."**

**Answer Structure:**

**Introduction (1 mark):**
"Measures of central tendency identify a single value representing the center of a distribution."

**Three Measures (3 marks):**

1. **Mean:** Sum of all values divided by number of values. Formula: Mean = Σx / n. Example: Data 10,20,30,40,50 → Mean = 150/5 = 30. Uses all values, affected by outliers.

2. **Median:** Middle value when sorted. For odd n: middle value. For even n: average of two middle values. Example: 10,20,30,40,50 → Median = 30. Not affected by outliers, good for skewed data.

3. **Mode:** Most frequent value. Example: 1,2,2,3,3,3,4 → Mode = 3. Can be used for categorical data, may have multiple modes.

**Comparison (1 mark):**
Mean uses all values but affected by outliers. Median robust to outliers. Mode for categorical data.

---

## 3. Variance

### Official Definition 🌟
> **"Variance is a statistical measure that quantifies the spread or dispersion of data points around the mean. It is calculated as the average of the squared differences from the mean."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Quantifies the spread"** — Data kitna spread hai, wo measure karta hai
- **"Around the mean"** — Mean se kitna door hain points
- **"Average of squared differences"** — Har point ka (value - mean)² ka average

### Formula 🌟

**Population Variance:**
```
σ² = Σ(xi - μ)² / N
```

**Sample Variance:**
```
s² = Σ(xi - x̄)² / (n - 1)
```

**Where:**
- xi = each value
- μ = population mean
- x̄ = sample mean
- N = population size
- n = sample size
- (n-1) = Bessel's correction

### Step-by-Step Calculation 🌟

**Example:**
```
Data: 10, 20, 30, 40, 50

Step 1: Calculate mean
x̄ = (10 + 20 + 30 + 40 + 50) / 5 = 150 / 5 = 30

Step 2: Calculate deviations from mean
(10-30) = -20
(20-30) = -10
(30-30) = 0
(40-30) = 10
(50-30) = 20

Step 3: Square the deviations
(-20)² = 400
(-10)² = 100
(0)² = 0
(10)² = 100
(20)² = 400

Step 4: Sum of squared deviations
Σ(xi - x̄)² = 400 + 100 + 0 + 100 + 400 = 1000

Step 5: Divide by (n-1) for sample variance
s² = 1000 / (5-1) = 1000 / 4 = 250
```

### Properties 🌟

| Property | Description |
|----------|-------------|
| **Always non-negative** | Variance ≥ 0 |
| **Units squared** | If data in meters, variance in m² |
| **Sensitive to outliers** | Extreme values increase variance |
| **Additive** | Var(X+Y) = Var(X) + Var(Y) if independent |

### Interpretation 🌟

| Variance Value | Meaning |
|----------------|---------|
| **Variance = 0** | All values same (no spread) |
| **Small variance** | Data clustered close to mean |
| **Large variance** | Data spread far from mean |

### Advantages & Limitations 🌟

**Advantages:**
- Uses all data points
- Mathematically tractable
- Foundation for other statistics

**Limitations:**
- Units are squared (hard to interpret)
- Sensitive to outliers
- Not intuitive

### In R 🌟
```r
data <- c(10, 20, 30, 40, 50)
var(data)  # 250
```

### Exam-Ready Points 📝 (5 Marks)

**Q: "Define variance. Explain its calculation with an example."**

**Answer Structure:**

**Definition (1 mark):**
"Variance quantifies the spread of data points around the mean, calculated as average of squared differences from mean."

**Formula (1 mark):**
Sample Variance: s² = Σ(xi - x̄)² / (n-1)

**Calculation Steps (2 marks):**
1. Calculate mean (x̄)
2. Find deviations (xi - x̄)
3. Square deviations (xi - x̄)²
4. Sum squared deviations
5. Divide by (n-1)

**Example (1 mark):**
Data: 10, 20, 30, 40, 50
Mean = 30
Variance = [(10-30)² + (20-30)² + (30-30)² + (40-30)² + (50-30)²] / (5-1)
= [400 + 100 + 0 + 100 + 400] / 4
= 1000 / 4 = 250

---

## 4. Standard Deviation

### Official Definition 🌟
> **"Standard deviation is the square root of variance. It measures the amount of variation or dispersion of a set of values in the same units as the original data."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"Square root of variance"** — Variance ka square root
- **"Same units as original data"** — Original data ke units mein hota hai (interpret kar sakte hain)
- **"Measures variation"** — Data kitna spread hai

### Formula 🌟

**Population Standard Deviation:**
```
σ = √(σ²) = √[Σ(xi - μ)² / N]
```

**Sample Standard Deviation:**
```
s = √(s²) = √[Σ(xi - x̄)² / (n-1)]
```

### Calculation Example 🌟

**Using previous variance example:**
```
Variance (s²) = 250
Standard Deviation (s) = √250 = 15.81
```

### Properties 🌟

| Property | Description |
|----------|-------------|
| **Always non-negative** | SD ≥ 0 |
| **Same units as data** | Interpretable |
| **Sensitive to outliers** | Extreme values increase SD |
| **Related to variance** | SD = √Variance |

### Interpretation 🌟

**Empirical Rule (for normal distribution):**

| Range | Percentage of Data |
|-------|-------------------|
| **Mean ± 1 SD** | ~68% of data |
| **Mean ± 2 SD** | ~95% of data |
| **Mean ± 3 SD** | ~99.7% of data |

**Example:**
```
Mean = 100, SD = 15

68% data between: 100 ± 15 = 85 to 115
95% data between: 100 ± 30 = 70 to 130
99.7% data between: 100 ± 45 = 55 to 145
```

### Comparison: Variance vs Standard Deviation 🌟

| Feature | Variance | Standard Deviation |
|---------|----------|-------------------|
| **Formula** | Σ(xi - x̄)² / (n-1) | √Variance |
| **Units** | Squared units | Original units |
| **Interpretability** | Hard to interpret | Easy to interpret |
| **Use** | Statistical calculations | Descriptive statistics |

### Why Standard Deviation is Important? 🌟

1. **Interpretable** — Same units as data
2. **Describes spread** — How far data points from mean
3. **Comparing variability** — Compare different datasets
4. **Outlier detection** — Points beyond 2-3 SD are outliers
5. **Normal distribution** — Empirical rule applies

### In R 🌟
```r
data <- c(10, 20, 30, 40, 50)
sd(data)  # 15.81
```

### Exam-Ready Points 📝 (5 Marks)

**Q: "Define standard deviation. How is it different from variance?"**

**Answer Structure:**

**Definition (1 mark):**
"Standard deviation is the square root of variance, measuring dispersion in same units as original data."

**Formula (1 mark):**
s = √[Σ(xi - x̄)² / (n-1)]

**Calculation (1 mark):**
If variance = 250, SD = √250 = 15.81

**Difference from Variance (2 marks):**

| Feature | Variance | Standard Deviation |
|---------|----------|-------------------|
| Units | Squared | Original |
| Interpretability | Hard | Easy |
| Use | Calculations | Description |

SD better for interpretation, variance for mathematical operations.

---

## 5. Z-Score

### Official Definition 🌟
> **"Z-score (standard score) represents how many standard deviations a data point is from the mean. It standardizes values to allow comparison across different distributions."**

### Phrase-by-Phrase Explanation (Hinglish) 🌟
- **"How many standard deviations"** — Mean se kitne SD door hai
- **"From the mean"** — Mean ke relative mein
- **"Standardizes values"** — Sab values ko same scale pe lata hai
- **"Comparison across distributions"** — Different datasets compare kar sakte hain

### Formula 🌟
```
Z = (X - μ) / σ
```

**Where:**
- X = data point value
- μ = mean of dataset
- σ = standard deviation

### Interpretation 🌟

| Z-Score | Meaning |
|---------|---------|
| **Z = 0** | Data point equals mean |
| **Z > 0** | Above mean |
| **Z < 0** | Below mean |
| **Z = 1** | 1 SD above mean |
| **Z = -2** | 2 SD below mean |

### Calculation Example 🌟

**Example:**
```
Dataset: Mean = 100, SD = 15
Data point: X = 130

Z = (130 - 100) / 15 = 30 / 15 = 2

Interpretation: This data point is 2 standard deviations above the mean.
```

### Properties 🌟

| Property | Description |
|----------|-------------|
| **Mean of Z-scores = 0** | Standardized to zero mean |
| **SD of Z-scores = 1** | Standardized to unit variance |
| **Unitless** | No units, comparable |
| **Identifies outliers** | |Z| > 3 often considered outlier |

### Applications 🌟

**1. Comparing Different Distributions:**
```
Student A: Math score = 85, Class mean = 75, SD = 10
Z_A = (85 - 75) / 10 = 1.0

Student B: Science score = 90, Class mean = 85, SD = 8
Z_B = (90 - 85) / 8 = 0.625

Conclusion: Student A performed better relative to class.
```

**2. Outlier Detection:**
```
Rule: |Z| > 3 → potential outlier
```

**3. Standardizing for Machine Learning:**
```
Transform all features to same scale
```

**4. Normal Distribution:**
```
Z-scores allow using standard normal table
P(Z < 1.96) = 0.975
```

### Z-Score Table (Standard Normal) 🌟

| Z | P(Z < z) |
|---|----------|
| -3.0 | 0.0013 |
| -2.0 | 0.0228 |
| -1.0 | 0.1587 |
| 0.0 | 0.5000 |
| 1.0 | 0.8413 |
| 2.0 | 0.9772 |
| 3.0 | 0.9987 |

### In R 🌟
```r
data <- c(10, 20, 30, 40, 50)
z_scores <- (data - mean(data)) / sd(data)
z_scores
# -1.26 -0.63  0.00  0.63  1.26
```

### Exam-Ready Points 📝 (5 Marks)

**Q: "Define Z-score. Explain its formula and applications."**

**Answer Structure:**

**Definition (1 mark):**
"Z-score represents how many standard deviations a data point is from the mean, used for standardization and comparison."

**Formula (1 mark):**
Z = (X - μ) / σ

**Interpretation (1 mark):**
- Z = 0: at mean
- Z > 0: above mean
- Z < 0: below mean

**Applications (2 marks):**
1. **Comparing distributions** — Different datasets ko compare kar sakte hain
2. **Outlier detection** — |Z| > 3 means outlier
3. **Standardization** — ML algorithms ke liye features standardize
4. **Probability calculation** — Normal distribution tables use

---

# MODULE 5: Data Visualization

## Important Topics:
1. Definition of Basic Plotting
2. Scatter Plot
3. Heat Maps
4. Strip Chart
5. Bar Graph
6. Box Plot

---

## 1. Definition of Basic Plotting

### Official Definition 🌟
> **"Basic plotting in R refers to the creation of visual representations of data using built-in plotting functions to explore patterns, relationships, and distributions."**

### Core Functions 🌟

| Function | Purpose | Example |
|----------|---------|---------|
| **plot()** | Generic plotting | Scatter plot, line plot |
| **hist()** | Histogram | Distribution |
| **barplot()** | Bar chart | Categorical comparison |
| **boxplot()** | Box plot | Distribution summary |
| **pie()** | Pie chart | Proportions |

### Basic plot() Syntax 🌟
```r
plot(x, y, type="p", main="Title", xlab="X Label", ylab="Y Label")
```

**Parameters:**
- `x, y` — data vectors
- `type` — "p" (points), "l" (lines), "b" (both)
- `main` — title
- `xlab, ylab` — axis labels
- `col` — color
- `pch` — point character

### Example 🌟
```r
# Simple scatter plot
x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 6, 8, 10)
plot(x, y, main="Scatter Plot", xlab="X-axis", ylab="Y-axis", col="blue")
```

### Exam-Ready Points 📝
- Basic plotting uses built-in R functions
- plot() is most versatile
- Parameters control appearance
- Used for data exploration

---

## 2. Scatter Plot

### Official Definition 🌟
> **"A scatter plot displays the relationship between two continuous variables by plotting points on a coordinate system, where each point represents an observation."**

### When to Use 🌟
- Relationship between two numeric variables
- Identify correlations
- Detect patterns, clusters, outliers

### Syntax 🌟
```r
plot(x, y, main="Title", xlab="X", ylab="Y", pch=19, col="blue")
```

### Example 🌟
```r
# Using mtcars dataset
plot(mtcars$wt, mtcars$mpg,
     main="Weight vs MPG",
     xlab="Weight (1000 lbs)",
     ylab="Miles Per Gallon",
     pch=19, col="red")
```

### Interpretation 🌟

| Pattern | Meaning |
|---------|---------|
| **Upward trend** | Positive correlation |
| **Downward trend** | Negative correlation |
| **No pattern** | No correlation |
| **Curved pattern** | Non-linear relationship |
| **Isolated points** | Outliers |

### Adding Trend Line 🌟
```r
plot(mtcars$wt, mtcars$mpg)
abline(lm(mpg ~ wt, data=mtcars), col="blue", lwd=2)
```

### Exam-Ready Points 📝
- Shows relationship between 2 continuous variables
- Identifies correlation (positive/negative/none)
- Detects outliers
- Can add trend line

---

## 3. Heat Maps

### Official Definition 🌟
> **"A heat map is a graphical representation of data where individual values are represented as colors in a two-dimensional grid."**

### When to Use 🌟
- Matrix data visualization
- Correlation matrices
- Time-series patterns
- Gene expression data

### Syntax 🌟
```r
heatmap(data_matrix, main="Title")
```

### Example 🌟
```r
# Correlation heatmap
cor_matrix <- cor(mtcars)
heatmap(cor_matrix, main="Correlation Heatmap")
```

### Interpretation 🌟
- **Darker color** = higher value
- **Lighter color** = lower value
- **Pattern recognition** = clusters, trends

### Advantages 🌟
- Visual pattern recognition
- Handles large matrices
- Intuitive color coding

### Exam-Ready Points 📝
- 2D grid with colors representing values
- Used for correlation matrices
- Darker = higher, lighter = lower
- Good for pattern recognition

---

## 4. Strip Chart

### Official Definition 🌟
> **"A strip chart (or strip plot) displays individual data points along a single axis, useful for small datasets or showing distribution of categorical groups."**

### When to Use 🌟
- Small datasets
- Show individual points
- Compare distributions across groups

### Syntax 🌟
```r
stripchart(data, method="jitter", pch=19, col="blue")
```

### Example 🌟
```r
# By group
stripchart(mpg ~ cyl, data=mtcars, method="jitter",
           main="MPG by Cylinders", xlab="Cylinders", ylab="MPG")
```

### Advantages 🌟
- Shows individual data points
- Simple visualization
- Good for small datasets

### Exam-Ready Points 📝
- Shows individual points on single axis
- Good for small datasets
- Can group by categories
- Shows distribution

---

## 5. Bar Graph

### Official Definition 🌟
> **"A bar graph displays categorical data with rectangular bars, where the height (or length) of each bar is proportional to the values it represents."**

### Types 🌟

| Type | Description |
|------|-------------|
| **Vertical** | Bars go up |
| **Horizontal** | Bars go sideways |
| **Grouped** | Multiple bars per category |
| **Stacked** | Bars divided into segments |

### Syntax 🌟
```r
barplot(height, names.arg=labels, main="Title", col="blue")
```

### Example 🌟
```r
# Simple bar plot
categories <- c("A", "B", "C", "D")
values <- c(10, 20, 15, 25)
barplot(values, names.arg=categories, main="Bar Graph", col="lightblue")
```

### When to Use 🌟
- Categorical data comparison
- Frequency distributions
- Discrete data visualization

### Exam-Ready Points 📝
- For categorical data
- Bar height = value
- Compare categories
- Types: vertical, horizontal, grouped, stacked

---

## 6. Box Plot

### Official Definition 🌟
> **"A box plot (box-and-whisker plot) displays the five-number summary of a dataset: minimum, Q1, median, Q3, and maximum."**

### Five-Number Summary 🌟

| Component | Description |
|-----------|-------------|
| **Minimum** | Smallest value (excluding outliers) |
| **Q1 (25th percentile)** | 25% data below this |
| **Median (50th percentile)** | Middle value |
| **Q3 (75th percentile)** | 75% data below this |
| **Maximum** | Largest value (excluding outliers) |

### Syntax 🌟
```r
boxplot(data, main="Title", ylab="Values", col="lightblue")
```

### Example 🌟
```r
boxplot(mtcars$mpg, main="MPG Distribution", ylab="Miles Per Gallon")
```

### Components 🌟

```
     Maximum ─────┐
                  │
     Q3 ──────────┤
                  │
     Median ──────┤
                  │
     Q1 ──────────┤
                  │
     Minimum ─────┘
     
     ○ Outliers
```

### Interpretation 🌟

| Feature | Meaning |
|---------|---------|
| **Box width** | Can show group size |
| **Box height (IQR)** | Spread of middle 50% |
| **Median line** | Central tendency |
| **Whisker length** | Range of data |
| **Outlier points** | Extreme values |

### Outlier Detection 🌟
```
Outlier if:
- Value < Q1 - 1.5 × IQR
- Value > Q3 + 1.5 × IQR
```

### Advantages 🌟
- Shows distribution shape
- Identifies outliers
- Compares multiple groups
- Robust to outliers (uses median)

### Exam-Ready Points 📝
- Shows five-number summary
- Box = IQR (Q1 to Q3)
- Line in box = median
- Whiskers = range (excluding outliers)
- Dots = outliers
- Good for comparing groups

---

# MODULE 6: Outlier Analysis

## Important Topics:
1. K-Nearest Neighbour (KNN) Algorithm
2. Outlier Detection Methods:
   - Density-Based Method
   - Depth-Based Method
   - Distance-Based Method
   - Extreme Value Analysis
   - Local Outlier Factor (LOF)

---

## 1. K-Nearest Neighbour (KNN) Algorithm

### Official Definition 🌟
> **"KNN is a non-parametric algorithm that classifies or predicts based on the majority vote or average of K nearest data points in the feature space."**

### How It Works 🌟

**Steps:**
1. Choose K (number of neighbors)
2. Calculate distance from query point to all other points
3. Find K nearest neighbors
4. For classification: majority vote
5. For regression: average of K neighbors

### Distance Metrics 🌟

| Metric | Formula | Use Case |
|--------|---------|----------|
| **Euclidean** | √Σ(xi - yi)² | Default, continuous |
| **Manhattan** | Σ|xi - yi| | High dimensions |
| **Minkowski** | (Σ|xi - yi|^p)^(1/p) | General |

### Example 🌟
```r
library(class)
# KNN classification
prediction <- knn(train, test, cl, k=5)
```

### For Outlier Detection 🌟
- Points far from K nearest neighbors → outliers
- Large average distance to K neighbors → outlier score

### Advantages & Limitations 🌟

**Advantages:**
- Simple to understand
- No training required (lazy learning)
- Works for classification & regression

**Limitations:**
- Computationally expensive
- Sensitive to K choice
- Sensitive to irrelevant features
- Requires scaling

### Exam-Ready Points 📝
- KNN uses K nearest neighbors
- Distance-based algorithm
- For classification: majority vote
- For regression: average
- Sensitive to K choice

---

## 2. Outlier Detection Methods

### Density-Based Method 🌟

**Definition:** Identifies outliers based on local density — points in low-density regions are outliers.

**Concept:**
- Normal points: high local density
- Outliers: low local density

**Advantages:**
- Detects local outliers
- Works with varying density clusters

**Limitations:**
- Computationally intensive
- Parameter sensitive

---

### Depth-Based Method 🌟

**Definition:** Measures how deep a point is within data distribution — points near boundary (low depth) are outliers.

**Concept:**
- Like peeling onion layers
- Outer layers = outliers

**Advantages:**
- No distribution assumption
- Handles asymmetric data

**Limitations:**
- Computationally expensive
- Ties at convex hull

---

### Distance-Based Method 🌟

**Definition:** Points far from their neighbors (large distance) are outliers.

**Methods:**
- K-NN distance
- Average K-NN distance
- Reverse K-NN

**Advantages:**
- Simple
- No distribution assumption

**Limitations:**
- Sensitive to K
- Distance metric choice matters

---

### Extreme Value Analysis 🌟

**Definition:** Statistical method focusing on tail of distribution — extreme values are outliers.

**Concept:**
- Models extreme events
- Uses extreme value theory

**Advantages:**
- Theoretically sound
- Good for risk analysis

**Limitations:**
- Assumes distribution
- Complex

---

### Local Outlier Factor (LOF) 🌟

**Definition:** Compares local density of a point with its neighbors — LOF > 1 indicates outlier.

**Formula:**
```
LOF(x) = Average density of neighbors / Density of x
```

**Interpretation:**
- LOF ≈ 1: normal point
- LOF > 1: outlier (higher = more outlier)

**Advantages:**
- Detects local outliers
- Works with varying density

**Limitations:**
- Parameter sensitive (K)
- Computationally intensive

### Comparison of Outlier Detection Methods 🌟

| Method | Basis | Best For | Limitation |
|--------|-------|----------|------------|
| **Density-Based** | Local density | Varying density | Complex |
| **Depth-Based** | Data depth | Asymmetric data | Expensive |
| **Distance-Based** | Neighbor distance | Simple cases | Sensitive to K |
| **Extreme Value** | Tail analysis | Risk analysis | Assumes distribution |
| **LOF** | Density ratio | Local outliers | Parameter sensitive |

### Exam-Ready Points 📝
- Density: low density = outlier
- Depth: low depth = outlier
- Distance: far from neighbors = outlier
- Extreme Value: tail of distribution
- LOF: LOF > 1 = outlier

---

# MODULE 7: Dimensionality Reduction

## Important Topics:
1. Forward Feature Selection
2. Backward Feature Selection
3. Principal Component Analysis (PCA)
4. Canonical Correlation Analysis (CCA)
5. Genetic Algorithm
6. Dimensionality Reduction – Basic Concepts

---

## 1. Forward Feature Selection

### Official Definition 🌟
> **"Forward feature selection is a wrapper method that starts with no features and iteratively adds the most significant feature until a stopping criterion is met."**

### Algorithm 🌟

```
Step 1: Start with empty feature set
Step 2: For each feature not in set:
          - Add it temporarily
          - Evaluate model performance
Step 3: Add feature that gives best improvement
Step 4: Repeat until stopping criterion
```

### Advantages & Limitations 🌟

**Advantages:**
- Simple
- Finds good subset

**Limitations:**
- Computationally expensive
- Can't remove features once added

---

## 2. Backward Feature Selection

### Official Definition 🌟
> **"Backward feature selection starts with all features and iteratively removes the least significant feature until a stopping criterion is met."**

### Algorithm 🌟

```
Step 1: Start with all features
Step 2: For each feature in set:
          - Remove it temporarily
          - Evaluate model performance
Step 3: Remove feature that causes least degradation
Step 4: Repeat until stopping criterion
```

### Comparison: Forward vs Backward 🌟

| Feature | Forward | Backward |
|---------|---------|----------|
| **Start** | Empty set | All features |
| **Process** | Add features | Remove features |
| **Speed** | Faster initially | Slower initially |
| **Best for** | Few relevant features | Many irrelevant features |

---

## 3. Principal Component Analysis (PCA)

### Official Definition 🌟
> **"PCA is a linear dimensionality reduction technique that transforms data into a new coordinate system where the greatest variance lies on the first coordinate (principal component), second greatest on second, and so on."**

### Steps 🌟

```
1. Standardize data (mean=0, SD=1)
2. Compute covariance matrix
3. Calculate eigenvectors and eigenvalues
4. Sort by eigenvalue (descending)
5. Select top k components
6. Transform data
```

### Key Concepts 🌟

**Principal Components:**
- Orthogonal (uncorrelated)
- Capture maximum variance
- PC1 > PC2 > PC3 in variance explained

**Eigenvalues:**
- Amount of variance captured by each PC
- Larger = more important

### Advantages & Limitations 🌟

**Advantages:**
- Reduces dimensionality
- Removes multicollinearity
- Noise reduction

**Limitations:**
- Linear only
- Loses interpretability
- Sensitive to scaling

### Exam-Ready Points 📝
- Linear dimensionality reduction
- Transforms to principal components
- Steps: standardize, covariance, eigenvectors, select, transform
- Captures maximum variance

---

## 4. Canonical Correlation Analysis (CCA)

### Official Definition 🌟
> **"CCA finds relationships between two sets of variables by identifying linear combinations (canonical variates) that have maximum correlation."**

### When to Use 🌟
- Two sets of variables
- Find relationships between sets
- Example: Academic variables vs Job performance variables

### Output 🌟
- Canonical correlations
- Canonical variates (linear combinations)

### Advantages & Limitations 🌟

**Advantages:**
- Finds relationships between variable sets
- Dimensionality reduction for two datasets

**Limitations:**
- Assumes linearity
- Sensitive to multicollinearity

---

## 5. Genetic Algorithm

### Official Definition 🌟
> **"Genetic Algorithm is an optimization technique inspired by natural selection that evolves solutions over generations using selection, crossover, and mutation."**

### For Feature Selection 🌟

**Representation:**
- Chromosome = binary string (1=selected, 0=not)
- Example: 10110 = features 1,3,4 selected

**Operators:**
1. **Selection** — Choose best chromosomes
2. **Crossover** — Combine parents
3. **Mutation** — Random changes

**Fitness:** Model performance with selected features

### Advantages & Limitations 🌟

**Advantages:**
- Global search
- Handles large spaces
- Doesn't get stuck in local optima

**Limitations:**
- Complex to implement
- Parameter tuning
- Computationally expensive

---

## 6. Dimensionality Reduction – Basic Concepts

### Official Definition 🌟
> **"Dimensionality reduction is the process of reducing the number of features while preserving important information."**

### Why Needed? 🌟
- Curse of dimensionality
- Reduces computation
- Improves model performance
- Visualization (2D/3D)

### Two Approaches 🌟

| Approach | Description | Examples |
|----------|-------------|----------|
| **Feature Selection** | Choose subset of features | Forward, Backward, GA |
| **Feature Extraction** | Create new features | PCA, LDA, CCA |

### Exam-Ready Points 📝
- Reduces number of features
- Two approaches: Selection & Extraction
- Benefits: less computation, better performance
- Curse of dimensionality

---

## 📚 Preparation Strategy

### High Priority (Module 4):
1. ✅ Master all 5 topics thoroughly
2. ✅ Prepare 6-mark answers
3. ✅ Practice numerical problems (mean, variance, SD, Z-score)
4. ✅ Definitions word-by-word yaad karo

### Medium Priority (Other Modules):
1. ✅ Understand basic definitions
2. ✅ Know advantages/limitations
3. ✅ Prepare 2-mark and 5-mark answers

### General Tips:
1. ✅ PPT folder ke module-based files zaroor padho
2. ✅ Definitions important hain — exact yaad karo
3. ✅ Examples ke saath samjhao
4. ✅ Diagrams/tables use karo wherever possible
5. ✅ Section 3 ke liye sab modules prepare karo

---

**🎯 ALL THE BEST FOR YOUR EXAMS!**
