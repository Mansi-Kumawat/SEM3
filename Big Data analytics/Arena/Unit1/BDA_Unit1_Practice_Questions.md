# BDA – Unit 1: Practice Questions & Active Recall Quiz

---

## Part A: 1-Mark MCQs (Practice)

**Q1.** Who coined the term "Big Data" and in which year?
- (A) Doug Cutting, 2003
- (B) Roger Mougalas, 2005
- (C) Jeff Dean, 2004
- (D) Jimmy Wales, 2006

**Q2.** Which of the following best describes "Velocity" in the 5 V's of Big Data?
- (A) The total size of data
- (B) The diversity of data formats
- (C) The speed at which data is generated
- (D) The accuracy of data

**Q3.** JSON and XML are examples of which type of data?
- (A) Structured Data
- (B) Unstructured Data
- (C) Semi-Structured Data
- (D) Raw Data

**Q4.** "What happened?" is the question answered by which type of analytics?
- (A) Predictive Analytics
- (B) Diagnostic Analytics
- (C) Prescriptive Analytics
- (D) Descriptive Analytics

**Q5.** Which of the following is NOT one of the 5 V's of Big Data?
- (A) Volume
- (B) Visibility
- (C) Velocity
- (D) Veracity

**Q6.** The Colossus machine was built in which year and for what purpose?
- (A) 1937, Social Security tracking
- (B) 1943, Deciphering Nazi codes
- (C) 2005, Web indexing
- (D) 1990, Internet traffic study

**Q7.** Which type of categorical data has a meaningful order?
- (A) Nominal
- (B) Ordinal
- (C) Discrete
- (D) Continuous

**Q8.** Hadoop was created by which company in 2005?
- (A) Google
- (B) IBM
- (C) Yahoo!
- (D) Microsoft

**Q9.** "What should be done?" is answered by:
- (A) Descriptive Analytics
- (B) Diagnostic Analytics
- (C) Predictive Analytics
- (D) Prescriptive Analytics

**Q10.** A dataset containing Student ID, Age, Gender, Study Hours, and Marks is an example of:
- (A) Univariate Dataset
- (B) Bivariate Dataset
- (C) Multivariate Dataset
- (D) Correlation Dataset

---

## Part B: 2-Mark Questions

**Q11.** Differentiate between structured and unstructured data with one example each.

**Q12.** What is the difference between Descriptive and Diagnostic Analytics? Give an example of each.

**Q13.** Define Veracity and Value from the 5 V's of Big Data. Why are they important?

**Q14.** What is the difference between Nominal and Ordinal categorical data? Give examples.

**Q15.** List any four roles in an analytic project and briefly describe each.

---

## Part C: 5-Mark Descriptive Questions

**Q16.** Explain the 5 V's of Big Data with suitable real-world examples for each V.

**Q17.** Describe the four types of Data Analytics. How are they different from each other? Explain with a single real-world scenario that uses all four types.

**Q18.** Explain the evolution of Big Data with key milestones from 1937 to 2005.

**Q19.** Describe the Analytics Cycle with all its phases. Why is it an iterative process?

**Q20.** Differentiate between structured, semi-structured, and unstructured data with examples. Why is unstructured data challenging to process?

---

## 📝 ANSWER KEY (Attempt first, then check!)

### Part A Answers
1. **(B)** Roger Mougalas, 2005
2. **(C)** The speed at which data is generated
3. **(C)** Semi-Structured Data
4. **(D)** Descriptive Analytics
5. **(B)** Visibility is NOT one of the 5 V's
6. **(B)** 1943, Deciphering Nazi codes
7. **(B)** Ordinal
8. **(C)** Yahoo!
9. **(D)** Prescriptive Analytics
10. **(C)** Multivariate Dataset (5 variables)

### Part B — Model Answers

**Q11. Structured vs Unstructured Data:**

**Structured Data** has a defined repeating pattern and predefined format. It is organized in fixed fields within records, making it easy for programs to sort, read, and process.
- **Example:** Relational database tables (e.g., a Student table with columns: ID, Name, Marks)

**Unstructured Data** does not have a logical or repeating pattern. It exists in various formats like emails, videos, images, and social media posts.
- **Example:** A YouTube video file or a collection of customer feedback emails

**Key difference:** Structured data fits neatly into rows and columns; unstructured data does not have a fixed schema.

---

**Q12. Descriptive vs Diagnostic Analytics:**

**Descriptive Analytics** summarizes historical data to describe what happened. It uses data aggregation and reporting.
- **Example:** "Last month's total sales were ₹25 lakh, with laptops being the top-selling product."

**Diagnostic Analytics** goes deeper to explain why something happened. It uses correlation, drill-down, and root cause analysis.
- **Example:** "Sales dropped 15% because a competitor launched a discount campaign and our marketing spend was reduced."

**Key difference:** Descriptive tells you WHAT; Diagnostic tells you WHY.

---

**Q13. Veracity and Value:**

**Veracity** refers to the quality, reliability, and accuracy of data. It measures whether the obtained data is correct and consistent. Only data with high veracity can be trusted for meaningful analysis.
- *Importance:* If data has errors or biases, the analysis results will be misleading (garbage in, garbage out).

**Value** refers to the useful insights and knowledge that can be extracted from data to drive business decisions and create competitive advantage.
- *Importance:* Without extracting value, Big Data is just a cost center. Value turns data into actionable business outcomes.

---

**Q14. Nominal vs Ordinal:**

**Nominal Data:** Categories with NO specific order or ranking. Cannot be sorted meaningfully.
- **Example:** Gender (Male/Female), Blood Group (A, B, AB, O), Department (IT, CSE)

**Ordinal Data:** Categories WITH a meaningful order or ranking. Can be sorted from low to high.
- **Example:** Education Level (School < UG < PG < PhD), Customer Satisfaction (Poor < Fair < Good < Excellent)

**Key difference:** Ordinal data has inherent ordering; nominal data does not.

---

**Q15. Four Roles in Analytic Projects:**

1. **Data Engineer:** Builds and maintains data pipelines and infrastructure. Ensures data is accessible and reliable for analysis.

2. **Data Scientist:** Applies statistical models and machine learning to extract insights. Creates predictive models and advanced analytics solutions.

3. **Data Analyst:** Analyzes data, creates reports and dashboards. Answers specific business questions using data visualization tools.

4. **Business Analyst:** Acts as a bridge between the technical team and business stakeholders. Translates data insights into actionable business decisions.

---

### Part C — Answer Outlines

**Q16. 5 V's of Big Data (5 Marks)**

*Structure your answer as:*
- Introduction: Define Big Data and introduce 5 V's
- For each V: Definition + Example + Why it matters
  - Volume: Size (Facebook 500TB/day)
  - Velocity: Speed (stock market transactions)
  - Variety: Diversity (text + video + sensor)
  - Veracity: Quality (fake reviews problem)
  - Value: Business insights (recommendation engines)
- Conclusion: All 5 V's together define Big Data

**Q17. Four Types of Analytics (5 Marks)**

*Structure:*
- Define Data Analytics
- For each type: Definition + Question it answers + Example
  - Descriptive → What happened? → Monthly sales report
  - Diagnostic → Why? → Why sales dropped
  - Predictive → What will? → Festive season forecast
  - Prescriptive → What to do? → Optimal route recommendation
- Single scenario: E-commerce company uses all four
- Comparison table

**Q18. Evolution of Big Data (5 Marks)**

*Structure:*
- Introduction
- Timeline with key milestones:
  - 1937: Social Security Act (first data project)
  - 1943: Colossus (first data processor)
  - 1960-1990: Various developments
  - 2005: Term coined + Hadoop
- Conclusion: Big Data evolved from simple record-keeping to complex distributed processing

**Q19. Analytics Cycle (5 Marks)**

*Structure:*
- Definition
- 6 phases with descriptions:
  1. Collection → 2. Processing → 3. Cleaning → 4. Analysis → 5. Visualization → 6. Deployment
- Why iterative: Results feed back into collection for continuous improvement
- Diagram

**Q20. Structured vs Semi-Structured vs Unstructured (5 Marks)**

*Structure:*
- Define each type
- Key characteristics table
- Examples
- Why unstructured is challenging:
  - No fixed format
  - Requires NLP/computer vision
  - High storage costs
  - Difficult to query
- Technologies used (Hadoop, NoSQL)
