# Exploratory Data Analysis — Unit 3 Comprehensive Lecture Notes
## Module 3: Data Pre-processing (Week 3 + Week 4)
### Subject: OLMCA616 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Explain** what data pre-processing is and why it's needed
2. **Perform** data cleaning using R functions
3. **Integrate** data from multiple sources using merge()
4. **Reduce** data dimensionality using PCA and feature selection
5. **Transform** data using normalization, smoothing, discretization
6. **Identify** types of missing data (MCAR, MAR, MNAR)
7. **Apply** traditional methods for handling missing data
8. **Implement** multiple imputation analysis
9. **Answer** exam questions using 5-mark framework

---

## 1. Introduction to Data Pre-processing

### Hook 🎯
Raw data = kachra! Errors, missing values, noise — sab hota hai. Analysis se pehle data ko clean aur ready banana zaroori hai — warna "Garbage In, Garbage Out"!

### Data Mining Process (4 Steps) 🌟

| Step | Description |
|------|-------------|
| **1. Data Gathering** | Collect data from various sources |
| **2. Data Preparation** | Pre-processing — cleaning, transforming |
| **3. Mining** | Apply algorithms to find patterns |
| **4. Analysis** | Interpret results, gain insights |

> **Data Pre-processing = Step 2: Data Preparation**

### Definition 🌟
> **"Data Pre-processing is a technique that involves cleaning and transforming raw data into a format suitable for analysis. It refines and conditions data to identify hidden patterns."**

### Four Main Concepts 🌟

| Concept | Description |
|---------|-------------|
| **Data Cleaning** | Fix errors, inconsistencies, missing values |
| **Data Integration** | Combine data from multiple sources |
| **Data Reduction** | Reduce volume, preserve quality |
| **Data Transformation** | Change structure/format of data |

### Why Needed? 🌟
- Raw data has errors, missing values, noise
- Different formats from different sources
- Inconsistent naming, units, scales
- Without pre-processing → analysis results unreliable!

### R Packages for Pre-processing 🌟
- **readr/data.table** — Loading data
- **tidyr** — Missing value handling, reshaping
- **dplyr** — Variable transformation, filtering
- **caret** — Data scaling, pre-processing
- **reshape2** — Reshaping data frames

---

## 2. Data Cleaning

### Hook 🎯
Data cleaning = data ka doctor! Errors detect karo, fix karo, aur analysis-ready banao!

### Definition 🌟
> **"Data cleaning is a meticulous process that involves identifying and rectifying errors, inconsistencies, and inaccuracies in a dataset."**

### Key Steps 🌟

| Step | Description | R Function |
|------|-------------|------------|
| **Handle Missing Data** | Impute or remove | `is.na()`, `complete.cases()` |
| **Remove Duplicates** | Prevent bias | `duplicated()`, `unique()` |
| **Handle Outliers** | Identify skewing values | Box plots, Z-scores |
| **Correct Data Types** | Appropriate types | `as.numeric()`, `as.factor()` |
| **Standardize Formats** | Consistent dates, units | `format()`, `strptime()` |
| **Clean Text Data** | Fix misspellings | `tm_map()`, `tidytext` |
| **Fix Inconsistent Entries** | Naming conventions | Find-and-replace, regex |
| **Address Units** | Common unit conversion | Document conversions |
| **Ensure Scales** | Normalize/scale | `scale()`, `preProcess()` |

### Handling Missing Data 🌟

```r
# Check missing values
is.na(airquality$Ozone)     # TRUE/FALSE for each value
complete.cases(airquality)   # TRUE if row has no missing

# Compute mean ignoring NA
mean(airquality$Ozone, na.rm = TRUE)

# Summary to identify missing columns
summary(airquality)
```

### Purpose 🌟
- Removes errors and redundancy
- Improves reliability and accuracy
- Ensures consistency
- Regulates analysis approach

### Tools 🌟
- **OpenRefine** — Open-source data cleaning tool
- **Cloudingo** — Data quality management
- **Melissa Clean Suite** — Address and data cleansing

---

## 3. Data Integration

### Hook 🎯
Multiple sources se data hai? Combine karo ek dataset mein — lekin redundancy aur schema issues ka dhyan rako!

### Definition 🌟
> **"Data integration is the process of combining data from multiple heterogeneous sources into a single cohesive dataset."**

### Types of Data Integration 🌟

| Type | Description |
|------|-------------|
| **Manual** | Human intervention to combine data |
| **Middleware** | Integration tools connect systems |
| **Virtual** | Unified view without moving data |
| **ETL** | Extract, Transform, Load |

### Issues 🌟

| Issue | Description |
|-------|-------------|
| **Schema Integration** | Different schemas from various sources |
| **Entity Identification** | Same entity, different names across sources |
| **Redundancy** | Duplicate data when column names differ |
| **Metadata Conflicts** | Different metadata descriptions |
| **Value Detection** | How values are stored differently |

### Forms of Integrated Data 🌟
- **Data Warehousing** — Central repository
- **Data Federation** — Virtual unified view
- **Data Consolidation** — Physical merge

### R Demo 🌟

```r
# Basic merge
merged <- merge(dataset1, dataset2)

# Problem: Different column names create redundancy
# Solution: Rename first, then merge
names(table1)[names(table1) == "FN"] <- "FirstName"
merged <- merge(table1, table2, by = "FirstName")
# Redundancy avoided, table size reduced!
```

---

## 4. Data Reduction

### Hook 🎯
Bahut zyada data hai? Volume reduce karo — lekin quality preserve karo! PCA aur feature selection use karo!

### Definition 🌟
> **"Data reduction is the process of reducing the volume of data while preserving the quality and essential information."**

### Purpose 🌟
- Makes analysis easier
- Reduces storage space
- Improves computational efficiency

### Procedures 🌟

| Procedure | Description |
|-----------|-------------|
| **Dimensionality Reduction** | Reduce number of features |
| **Data Compression** | Lossless or lossy |
| **Numerosity Reduction** | Fewer data points |
| **Discretization** | Continuous → categorical |
| **Data Cube Aggregation** | Summarize across dimensions |

### Dimensionality Reduction 🌟

> **"Technique of reducing the number of features (dimensions/variables) to important/significant variables — called principal variables."**

**Example:** 3D image reduced to 2D without losing important features!

#### Feature Selection 🌟

| Aspect | Details |
|--------|---------|
| **What** | Select important features, eliminate less important |
| **Also known as** | Feature elimination technique |
| **Methods** | Filter, Wrapper, Embedded |
| **Advantage** | Simple to implement |
| **Disadvantage** | Information might be lost |

#### Feature Extraction 🌟

| Aspect | Details |
|--------|---------|
| **What** | Form NEW features from original features |
| **Result** | Higher dimension → lower dimension |
| **Advantage** | Keeps structure of data |
| **Disadvantage** | Difficult to define/interpret new features |

#### Other Techniques 🌟
- **PCA** — Principal Component Analysis
- **LDA** — Linear Discriminant Analysis
- **GDA** — Generalized Discriminant Analysis
- **CCA** — Canonical Correlation Analysis
- **Factor Analysis**

```r
# Subset selection
subset_data <- original_data[original_data$column > 10, ]

# Correlation for feature selection
correlation_matrix <- cor(original_data)
```

---

## 5. Data Transformation

### Hook 🎯
Data ka structure change karo — categorical se numerical, numerical se categorical. Analysis faster aur easier ban jayegi!

### Definition 🌟
> **"Data transformation is a process of transforming the structure of data. Categorical data needs to be converted into numerical value, or numerical into categorical. This conversion depends on processing methods."**

### Methods 🌟

#### 5.1 Smoothing 🌟
- Reduces noise and variability
- Replaces individual values with smoothed average
- Useful for time-series data

```r
smoothed_data <- smooth(original_data, method = "simple")
```

#### 5.2 Aggregation 🌟
- Combines multiple data points into single summary value
- Reduces granularity, generates higher-level insights

```r
aggregated_data <- aggregate(data$variable, 
                              by = list(data$group), 
                              FUN = mean)
```

#### 5.3 Discretization 🌟
- Transforms continuous data → discrete categories/bins

```r
discretized_data <- cut(data$numeric_var, 
                        breaks = 3, 
                        labels = c("Low", "Medium", "High"))
```

#### 5.4 Normalization 🌟

**Three Types:**

| Type | Formula | Result |
|------|---------|--------|
| **Min-Max** | (v - min) / (max - min) | Values between 0 to 1 |
| **Z-Score** | (v - mean) / std_dev | Mean = 0, SD = 1 |
| **Decimal Scaling** | Move decimal point j places | Scaled down proportionally |

**Min-Max Normalization Formula:**
```
v' = (v - min_A) / (max_A - min_A)
```
Linear transformation. New values between 0 and 1.

**Z-Score Normalization Formula:**
```
v' = (v - mean_A) / std_dev_A
```
Where v' = new value, v = old value, μ_A = mean, σ_A = standard deviation

```r
# Min-Max normalization using caret
library(caret)
normalized <- preProcess(dataframe, method = c("center", "scale"))
dataframe_norm <- predict(normalized, dataframe)
```

### Purpose 🌟
- Makes work easier
- Large numbers transformed between 0-1 → faster analysis
- Handles time complexity

---

## 6. Data Discretization

### Hook 🎯
Continuous data ko categories mein divide karo! Age ko bins mein daalo — Child, Young, Adult, Senior. Analysis simple ho jaata hai!

### Definition 🌟
> **"Discretization transforms continuous data into discrete categories or bins."**

### Methods 🌟

| Method | Description | Example |
|--------|-------------|---------|
| **Equal Width** | Same range for each bin | 0-20, 20-40, 40-60, 60-80 |
| **Equal Frequency** | Same count per bin | 25% data in each quartile |
| **Concept Hierarchy** | Categorical levels | City → State → Country |

### Examples 🌟

| Variable | Bins | Categories |
|----------|------|------------|
| **Age** | 0-18, 19-35, 36-60, 60+ | Child, Young, Adult, Senior |
| **Income** | <30K, 30-70K, >70K | Low, Medium, High |
| **Temperature** | <15°C, 15-30°C, >30°C | Cold, Warm, Hot |
| **Score** | 0-40, 41-60, 61-80, 81-100 | Fail, Pass, Good, Excellent |

### Advantages 🌟
- Simplifies data representation
- Reduces effect of outliers
- Easier for certain algorithms (decision trees)
- Faster processing

```r
# Equal width binning
cut(age, breaks = seq(0, 100, by = 20))

# Equal frequency (quartiles)
cut(income, breaks = quantile(income, probs = seq(0, 1, 0.25)))

# Custom labels
cut(score, breaks = c(0, 40, 60, 80, 100), 
    labels = c("Fail", "Pass", "Good", "Excellent"))
```

---

## 7. Introduction to Missing Data

### Hook 🎯
Missing data = bahut common problem! Survey mein log kuch questions skip karte hain. Iska analysis pe bahut impact padta hai — bias aa sakta hai!

### Definition 🌟
> **"Missing data refers to the absence of values for certain observations or variables. It is a common challenge in real-world datasets."**

### Causes 🌟

| Cause | Description | Example |
|-------|-------------|---------|
| **Non-response** | No information provided | Questionnaire skipped |
| **Sensitive items** | Uncomfortable sharing | Income, health questions |
| **Attrition** | Participants drop out | Long-term studies |
| **Equipment failure** | Technical errors | Sensor malfunction |
| **Human error** | Mistakes in collection | Data entry errors |
| **Research errors** | Improper collection | Wrong values entered |

### Impact 🌟

| Impact | Description |
|--------|-------------|
| **Bias** | Inaccurate or incomplete results |
| **Reduced Power** | Ability to detect real effects compromised |
| **Decreased Precision** | Estimates less precise due to smaller sample |

### Key Terms 🌟

| Term | Definition |
|------|-----------|
| **Missing Data Pattern** | Configuration of observed values and missing data |
| **Missing Data Mechan** | Relationship between observed variables and probability of missing |

### Where Does It Occur? 🌟
- Research (economics, sociology, political science)
- Government/private entity studies
- Clinical trials
- Survey research
- Longitudinal studies

---

## 8. Types of Missing Data (Three Mechanisms)

### Hook 🎯
Teen types hain missing data ke — MCAR, MAR, MNAR. Ye samajhna bahut zaroori hai — handling method depend karti hai type pe!

### MCAR — Missing Completely at Random 🌟

| Aspect | Description |
|--------|-------------|
| **Definition** | Missingness is purely random, unrelated to any variable |
| **Characteristics** | Independent of observed AND unobserved variables |
| **Analysis** | Unbiased |
| **Classification** | **IGNORABLE** |
| **Example** | Coin flip decides which data is missing |
| **Probability** | Not related to any other variable |

> MCAR sabse simple case — analysis pe koi effect nahi padta!

### MAR — Missing At Random 🌟

| Aspect | Description |
|--------|-------------|
| **Definition** | Missingness related to OBSERVED variables, not missing values |
| **Characteristics** | Can be explained by other complete variables |
| **Analysis** | Asymptotically unbiased with full information |
| **Classification** | **IGNORABLE** |
| **Example** | Men skip depression surveys — related to maleness, not depression |
| **Probability** | Related to some other variable in dataset |

> MAR more realistic than MCAR. Modern methods assume MAR!

### MNAR — Missing Not At Random 🌟

| Aspect | Description |
|--------|-------------|
| **Definition** | Missingness related to the MISSING VALUES THEMSELVES |
| **Also known as** | Nonignorable nonresponse |
| **Characteristics** | Systematically related to unobserved data |
| **Classification** | **NON-IGNORABLE** |
| **Example** | Drug users skip drug survey — missing BECAUSE of drug use |
| **Probability** | Associated with the variable itself |

> MNAR sabse complex case — strategies needed to find causes!

### Comparison Table 🌟

| Feature | MCAR | MAR | MNAR |
|---------|------|-----|------|
| **Missingness** | Random | Related to observed | Related to missing values |
| **Bias** | None | Possible | Significant |
| **Ignorable?** | Yes | Yes | No |
| **Complexity** | Simple | Medium | Most complex |
| **Example** | Coin flip | Men skip salary | Drug users skip survey |

---

## 9. Traditional Methods for Missing Data

### Hook 🎯
Missing data handle karne ke 2 main methods hain — Deletion (remove karo) aur Imputation (fill karo). Dono ke advantages aur disadvantages hain!

### Method 1: Deletion Method 🌟

| Technique | Description | Pros | Cons |
|-----------|-------------|------|------|
| **Listwise Deletion** | Remove entire row with any missing value | Simple | Loss of information |
| **Pairwise Deletion** | Use available data per analysis | More data retained | Inconsistent N |

**Disadvantages:**
- Information loss
- Bias if not MCAR
- Reduced sample size
- Results may not be representative

### Method 2: Imputation Method 🌟

| Technique | Description | Best For |
|-----------|-------------|----------|
| **Mean Imputation** | Fill with column mean | Quick, simple |
| **Median Imputation** | Fill with median | Skewed distributions |
| **Hot-Deck** | Random draw from similar respondents | Survey data |
| **Cold-Deck** | Use values from external source | Known reference data |
| **Regression** | Predict using regression model | Strong relationships |
| **Stochastic Regression** | Regression + random error | More realistic |
| **Last Observation Carried Forward (LOCF)** | Last available score | Longitudinal studies |
| **Similar Response Pattern** | Donor with similar profile | Survey matching |
| **Averaging Available Items** | Compute scale score | Questionnaires |

### Hot-Deck Imputation Details 🌟
- Random draw from observed data replaces each missing value
- Typically draws from subsample of respondents scoring similarly on matching variables
- Preserves data distribution

### LOCF Details 🌟
- Specific to longitudinal designs
- Replaces missing values with last available observed score
- Example: Participant drops out after week 5 of 8-week study → week 5 score fills remaining waves

---

## 10. Bayesian Estimation

### Hook 🎯
Bayesian approach — prior beliefs + data evidence = posterior distribution. Missing data handle karne ka powerful method!

### Three Major Steps 🌟

| Step | Description |
|------|-------------|
| **1. Prior Distribution** | Subjective beliefs about parameter values BEFORE collecting data |
| **2. Likelihood Function** | Data's evidence about parameter values |
| **3. Posterior Distribution** | Combine prior + likelihood = updated probabilities |

### Prior Distribution 🌟
- Explains beliefs about relative probability of parameter values
- Example: Researcher A believes depression rates 0.10-0.15 are likely
- Researcher B assigns equal weight to every proportion (noninformative prior)

### Likelihood Estimation 🌟
- Collect data, use likelihood function
- Apply maximum likelihood principles
- Example: 7 out of 100 diagnosed cases → substitute into density function

### Posterior Distribution 🌟
- Composite distribution combining prior and likelihood
- If high prior probability at parameter value → posterior increases at that point
- Noninformative prior → posterior identical to likelihood

---

## 11. Multiple Imputation Analysis

### Hook 🎯
Multiple imputation = gold standard! Ek value se fill karne ki jagah, multiple datasets banao — uncertainty account hoti hai!

### Definition 🌟
> **"Multiple Imputation creates multiple datasets with imputed values to account for uncertainty in missing data imputation."**

### Three Steps 🌟

| Step | Description |
|------|-------------|
| **1. Imputation Phase** | Data Augmentation Algorithm generates multiple datasets |
| **2. Analysis Phase** | Analyze each imputed dataset separately |
| **3. Pooling Phase** | Combine into single results |

### Imputation Phase Details 🌟

**Data Augmentation Algorithm:**
- Iterative algorithm cycling between I-step and P-step

| Step | Action |
|------|--------|
| **I-step (Imputation)** | Uses stochastic regression to impute missing values |
| **P-step (Posterior)** | Uses filled-in data to generate new estimates of mean vector and covariance matrix |

- Repeats multiple times → generates several copies of data
- Each copy has unique estimates of missing values
- Relies on Bayesian analysis for posterior distribution

### Analysis Phase 🌟
- Consists of m statistical analyses (one per imputed dataset)
- Provides multiple sets of parameter estimates and standard errors

### Pooling Phase 🌟
- Rubin's (1987) formulas for combining results
- Parameter estimates = arithmetic average of m analyses
- Standard errors = slightly more complex combination formula

### Advantages 🌟

| Advantage | Description |
|-----------|-------------|
| **Accounts for uncertainty** | Reflects variability in imputation |
| **Better standard errors** | More accurate than single imputation |
| **Valid inference** | Statistical tests are valid |
| **Flexible** | Works with many analysis methods |

### R Implementation 🌟
```r
library(mice)
# Multiple Imputation by Chained Equations
imputed_data <- mice(dataset, m = 5, seed = 123)
# Analyze each imputed dataset
fit <- with(imputed_data, lm(outcome ~ predictor))
# Pool results
pooled <- pool(fit)
summary(pooled)
```

---

## 12. Missing Data Patterns & Characteristics

### Patterns 🌟

| Pattern | Description |
|---------|-------------|
| **Unit Nonresponse** | Entire observations/cases missing |
| **Item Nonresponse** | Specific variables within observations missing |
| **Monotone Pattern** | Missing values in consistent pattern (beginning/end only) |
| **Non-Monotone Pattern** | No consistent pattern |

### Characteristics 🌟

| Characteristic | Description |
|----------------|-------------|
| **Informative Missingness** | Missing values convey information |
| **Non-Informative Missingness** | No additional information from missingness |
| **Sparse Missing Data** | Small percentage missing |
| **Dense Missing Data** | Significant portion missing |

### Visualization 🌟
- **Missing Data Heatmap** — Shows presence/absence of values
- **Histograms** — Distribution of missing values across variables
- **Bar Charts** — Count of missing per variable

### Best Practices 🌟
- Understand nature and patterns BEFORE deciding strategy
- Document handling of missing data for transparency
- Use appropriate software tools (R: dplyr, mice)

---

## 13. Learning Tricks

### Trick 1: Data Pre-processing Steps (4)
**"C-I-R-T"** → Cleaning, Integration, Reduction, Transformation
→ *"Clean It Right, Totally!"*

### Trick 2: Missing Data Types (3)
**"MCAR-MAR-MNAR"** → Remember: C=Complete, A=At, N=Not
→ *"Completely random, At random, Not at random"*

### Trick 3: Normalization Types (3)
**"M-Z-D"** → Min-Max, Z-Score, Decimal
→ *"Minimum to Zero to Decimal"*

### Trick 4: Multiple Imputation Steps (3)
**"I-A-P"** → Imputation, Analysis, Pooling
→ *"Impute, Analyze, Pool!"*

### Trick 5: Transformation Methods (4)
**"S-A-D-N"** → Smoothing, Aggregation, Discretization, Normalization
→ *"Simply Analyze Data Now!"*

---

## 14. Common Mistakes ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Skipping pre-processing | Always clean before analysis |
| Using mean() without na.rm | Use `na.rm = TRUE` |
| Listwise deletion always | Consider imputation for small datasets |
| Assuming MAR when MNAR | Test and verify missingness mechanism |
| Single imputation for complex data | Use multiple imputation |
| Ignoring schema issues in integration | Rename columns before merge |
| Normalizing without checking range | Verify 0-1 or standard normal |
| Forgetting to document missing data handling | Always document for reproducibility |

---

## 15. 5-Mark Answer Framework

**Q: "Explain data pre-processing techniques."** (5 marks)

**Answer Structure:**

**Introduction (1 mark):**
"Data pre-processing is a crucial step that involves cleaning and transforming raw data into a format suitable for analysis."

**Four Main Techniques (3 marks):**
1. **Data Cleaning:** Remove errors, handle missing values, remove duplicates
2. **Data Integration:** Combine multiple sources, handle schema issues
3. **Data Reduction:** PCA, feature selection, reduce volume
4. **Data Transformation:** Normalization (Min-Max, Z-Score), smoothing, discretization

**Additional (1 mark):**
Missing data handling: MCAR, MAR, MNAR. Methods: Deletion, Imputation, Multiple Imputation.

---

## 16. Sources Used

| Source | Content Used |
|--------|-------------|
| W3_Notes.pdf | Week 3 (24 pages, 19338 chars) — Pre-processing, Cleaning, Integration, Reduction, Transformation, Discretization |
| W4_Notes.pdf | Week 4 (23 pages, 26138 chars) — Missing Data, Traditional Methods, Multiple Imputation |
| OLMCA616 Module 3 PPT | 64 pages — visual reference (image-based) |
| Syllabus OLMCA616 | Module 3 scope |

---

## 17. Topic Coverage Checklist ✅

| Syllabus Topic | Status | Section |
|----------------|--------|---------|
| Introduction to Data Pre-processing | ✅ | 1 |
| Data Cleaning | ✅ | 2 |
| Data Integration | ✅ | 3 |
| Data Reduction | ✅ | 4 |
| Data Transformation | ✅ | 5 |
| Data Discretization | ✅ | 6 |
| Introduction to Missing Data | ✅ | 7 |
| Types: MCAR, MAR, MNAR | ✅ | 8 |
| Traditional Methods | ✅ | 9 |
| Missing Data Handling | ✅ | 9, 10, 12 |
| Multiple Imputation | ✅ | 11 |

### Coverage: 11/11 topics = 100% ✅

---

*Subject: Exploratory Data Analysis (OLMCA616)*
*Unit 3 — Module 3: Data Pre-processing*
*Last Updated: November 2025 | VIT MCA Semester 3*
