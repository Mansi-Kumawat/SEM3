# BDA – Unit 1: Big Data Cycle
## Summary Notes | OLMCA606

---

## 1. Important Definitions

**Big Data:** Collection of datasets so large, diverse, and rapidly growing that traditional data management tools cannot efficiently store, process, or analyze them.

**5 V's of Big Data:** Volume, Velocity, Variety, Veracity, Value — five key characteristics defining Big Data.

**Structured Data:** Data with a defined repeating pattern in a predefined format, organized in fixed fields within records (e.g., RDBMS, CSV).

**Unstructured Data:** Data without logical or repeating patterns, in various formats (e.g., emails, videos, social media).

**Semi-Structured Data:** Schema-less or self-describing data with tags/markup elements (e.g., JSON, XML, NoSQL).

**Data Analytics:** Process of examining, transforming, and interpreting data to discover useful information and support decision-making.

**Descriptive Analytics:** Analyzes historical data to summarize past events. Answers: "What happened?"

**Diagnostic Analytics:** Examines data to determine why an event occurred. Answers: "Why did it happen?"

**Predictive Analytics:** Uses historical data, statistics, and ML to predict future outcomes. Answers: "What is likely to happen?"

**Prescriptive Analytics:** Uses predictive models, optimization, and AI to recommend best actions. Answers: "What should be done?"

**Analytics Cycle:** Systematic iterative process transforming raw data into actionable insights through defined phases.

**Dataset:** A collection of related data that is large, diverse, or rapidly generated beyond traditional database capabilities.

---

## 2. Evolution of Big Data — Key Milestones

| Year | Event |
|------|-------|
| 1937 | First major data project — FDR's Social Security Act (IBM punch cards) |
| 1943 | Colossus — first data-processing machine (Nazi code decryption) |
| 1960 | Automatic Data Compression (ACM) |
| 1970 | Japan Ministry of Post — data volume tracking |
| 1980 | Hungarian statistics office — population/economic data |
| 1990 | K.G. Coffman — Internet traffic study |
| 2000 | 3D data management, GIS, medical imaging |
| **2005** | **Roger Mougalas coined "Big Data" + Hadoop created by Yahoo!** |

---

## 3. Sources & Types of Data

### Sources
- **Internal:** Generated within organization (sales DB, HR data, CRM, ERP)
- **External:** From outside (business partners, Internet, government, market research)

### By Origin Type
| Type | Examples |
|------|----------|
| Social Data | Facebook, Twitter, LinkedIn |
| Machine Data | RFID, sensors, GPS |
| Transactional Data | eBay, Amazon, B2B |

### By Structure
| Type | Key Feature | Storage | Example |
|------|------------|---------|---------|
| Structured | Fixed format, repeating pattern | RDBMS | SQL tables |
| Semi-Structured | Schema-less, tags/markup | NoSQL, XML/JSON | JSON, XML |
| Unstructured | No pattern, various formats | File systems | Videos, emails |

---

## 4. The 5 V's of Big Data

| V | Definition | Example |
|---|-----------|---------|
| **Volume** | Amount/size of data | 500+ TB data generated daily by Facebook |
| **Velocity** | Speed of data generation | Millions of stock transactions/second |
| **Variety** | Diverse formats (structured + unstructured) | Text + images + video + sensor data |
| **Veracity** | Quality, accuracy, reliability | Fake reviews reduce veracity |
| **Value** | Useful insights for decision-making | Customer patterns → product recommendations |

**Mnemonic:** "Very Vast Velociously Verified Value"

---

## 5. Types of Analytics

| Type | Question | Time | Technique |
|------|----------|------|-----------|
| Descriptive | What happened? | Past | Reports, aggregation |
| Diagnostic | Why did it happen? | Past | Correlation, root cause |
| Predictive | What will happen? | Future | ML, statistical models |
| Prescriptive | What should we do? | Future | Optimization, AI |

---

## 6. Analytics Cycle — 6 Phases

```
Collect → Process → Clean → Analyze → Visualize → Deploy/Monitor
   ↶_____________________________________________↷  (iterative)
```

| Phase | Key Activity |
|-------|-------------|
| 1. Data Collection | Gather from sources (surveys, sensors, APIs) |
| 2. Data Processing | Convert to usable format, sort, organize |
| 3. Data Cleaning | Remove errors, duplicates, handle missing values |
| 4. Data Analysis | Apply statistical/ML techniques |
| 5. Visualization & Reporting | Charts, dashboards, reports |
| 6. Deployment & Monitoring | Implement insights, track KPIs |

---

## 7. Roles in Analytic Projects

| Role | Core Responsibility |
|------|-------------------|
| Data Engineer | Build/maintain data pipelines and infrastructure |
| Data Scientist | Apply ML, statistical models for insights |
| Data Analyst | Create reports, answer business questions |
| Business Analyst | Bridge tech team and business stakeholders |
| Data Architect | Design data architecture and governance |
| ML Engineer | Deploy ML models to production |
| BI Developer | Create dashboards (Tableau, Power BI) |

---

## 8. Big Data Challenges

1. **Storage** — Need distributed systems for petabytes
2. **Processing Speed** — Need parallel processing (MapReduce, Spark)
3. **Data Quality** — Accuracy and consistency
4. **Security & Privacy** — Protection and compliance
5. **Integration** — Combining diverse data types
6. **Cost** — Expensive infrastructure and talent
7. **Skill Gap** — Shortage of qualified professionals
8. **Real-time Processing** — Low latency requirements

---

## 9. Types of Datasets

| Type | Definition | Sub-types |
|------|-----------|-----------|
| Categorical | Values are categories/groups, no arithmetic | Nominal (no order), Ordinal (ordered) |
| Numerical | Quantitative data, arithmetic possible | Discrete (countable), Continuous (measurable) |
| Multivariate | 3+ variables per observation | — |
| Correlation | 2+ variables to find relationships | Positive, Negative, No correlation |
| Bivariate | Exactly 2 variables | — |

### Correlation Types
- **Positive:** Both increase/decrease together (Study Hours ↑ → Marks ↑)
- **Negative:** One increases, other decreases (Price ↑ → Demand ↓)
- **No Correlation:** No relationship (Shoe Size vs Exam Marks)

---

## 10. Applications in Industries

| Industry | Application |
|----------|-------------|
| Retail | Recommendations, demand forecasting, segmentation |
| Healthcare | EHR, disease prediction, personalized medicine |
| Finance | Fraud detection, risk assessment, algo trading |
| Telecom | Network optimization, churn prediction |
| Media | Content recommendation (Netflix, Spotify) |
| Energy | Smart grids, demand forecasting |
| Education | Personalized learning, at-risk identification |
| Transport | Traffic management, route optimization |
| Agriculture | Precision farming, yield prediction |
| Government | Smart cities, crime analysis |

---

## 11. Last-Minute Revision — One-Page Recap

```
BIG DATA = Too big for traditional tools

5 V's: Volume | Velocity | Variety | Veracity | Value

DATA TYPES:
  Structured → Fixed format (SQL, CSV)
  Semi-Structured → Tags/markup (JSON, XML)
  Unstructured → No format (video, email)

4 ANALYTICS:
  Descriptive → What happened?
  Diagnostic  → Why?
  Predictive  → What will happen?
  Prescriptive → What to do?

CYCLE: Collect → Process → Clean → Analyze → Visualize → Deploy

2005 = Roger Mougalas (term "Big Data") + Yahoo (Hadoop)
```

---

## 12. Common Mistakes & Confusions

| Mistake | Correct Understanding |
|---------|----------------------|
| "Big Data = just large data" | Big Data = large + diverse + fast-growing + needs new tools |
| Confusing Diagnostic with Descriptive | Descriptive = WHAT happened, Diagnostic = WHY it happened |
| Semi-structured = structured | Semi-structured is schema-less with tags (NOT fixed format) |
| Velocity = volume | Velocity = SPEED of data, Volume = SIZE of data |
| Veracity = variety | Veracity = QUALITY/accuracy, Variety = DIVERSITY of formats |

---

## 13. Exam-Ready Keywords

- **Roger Mougalas, 2005** — Coined "Big Data"
- **Yahoo, 2005** — Created Hadoop
- **5 V's** — Volume, Velocity, Variety, Veracity, Value
- **Colossus, 1943** — First data-processing machine
- **Social Security Act, 1937** — First major data project
- **Structured/Unstructured/Semi-structured** — Three data types
- **DDPP** — Descriptive, Diagnostic, Predictive, Prescriptive
- **CPCAVD** — Analytics Cycle phases
