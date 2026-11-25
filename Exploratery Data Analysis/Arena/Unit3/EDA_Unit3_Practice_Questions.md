# EDA Unit 3 — Practice Questions (FAT Pattern)
## Module 3: Data Pre-processing

---

## Section A: 1 Mark Each (10 Questions × 1 = 10 Marks)

**Q1.** Define data pre-processing.

**Q2.** Name the four main concepts of data pre-processing.

**Q3.** What is data cleaning?

**Q4.** Which R function is used to identify missing values?

**Q5.** Define data integration.

**Q6.** What does merge() function do in R?

**Q7.** Define data reduction.

**Q8.** What is MCAR?

**Q9.** Define multiple imputation.

**Q10.** Name the three phases of multiple imputation analysis.

---

## Section B: 2 Marks Each (15 Questions × 2 = 30 Marks)

**Q1.** What is the purpose of data pre-processing?

**Q2.** Differentiate between data cleaning and data transformation.

**Q3.** What are the common ways to handle missing data?

**Q4.** What is the difference between listwise and pairwise deletion?

**Q5.** Define normalization. Name its types.

**Q6.** What is the difference between feature selection and feature extraction?

**Q7.** Explain discretization with an example.

**Q8.** What is MAR? How is it different from MCAR?

**Q9.** What are the causes of missing data?

**Q10.** What is the difference between MCAR and MNAR?

**Q11.** What is hot-deck imputation?

**Q12.** What is the use of summary() function in data cleaning?

**Q13.** What are the issues in data integration?

**Q14.** What is the purpose of data reduction? Name procedures available.

**Q15.** What is LOCF (Last Observation Carried Forward)?

---

## Section C: 5 Marks Each (6 Questions × 5 = 30 Marks)

**Q1.** Explain data pre-processing. Describe its four main concepts with examples.

**Q2.** What is data cleaning? Explain the key steps involved in data cleaning with R functions.

**Q3.** Explain data transformation. Describe normalization types with formulas.

**Q4.** What is missing data? Explain three mechanisms (MCAR, MAR, MNAR) with examples.

**Q5.** Explain traditional methods for handling missing data. Compare deletion and imputation methods.

**Q6.** What is multiple imputation? Explain its three phases in detail.

---

## Answer Key (Selected)

### Section A:
- **A1:** Technique of cleaning and transforming raw data into format suitable for analysis
- **A2:** Data Cleaning, Data Integration, Data Reduction, Data Transformation
- **A3:** Process of identifying and rectifying errors, inconsistencies, inaccuracies in dataset
- **A4:** is.na()
- **A5:** Combining data from multiple heterogeneous sources into single dataset
- **A6:** Combines/merges two datasets based on common column
- **A7:** Process of reducing volume of data preserving quality
- **A8:** Missing Completely at Random — missingness purely random, unrelated to any variable
- **A9:** Creates multiple datasets with imputed values to account for uncertainty
- **A10:** Imputation Phase, Analysis Phase, Pooling Phase

### Section C (Framework):

**Q1:** Definition (1) → 4 concepts: Cleaning, Integration, Reduction, Transformation with brief explanation (3) → Examples/code (1)

**Q2:** Definition of cleaning (1) → Key steps: missing data, duplicates, outliers, data types, formats, text cleaning (3) → R functions: is.na(), summary(), duplicated(), unique() (1)

**Q4:** Definition of missing data (1) → MCAR: definition + example (1) → MAR: definition + example (1) → MNAR: definition + example (1) → Comparison/ignorable vs non-ignorable (1)

**Q6:** Definition (1) → Imputation Phase: Data Augmentation, I-step, P-step (2) → Analysis Phase: analyze each dataset separately (1) → Pooling Phase: Rubin's formulas, arithmetic average (1)

---

*Practice Questions — Unit 3 | EDA (OLMCA616) | VIT MCA FAT Pattern*
