# Exploratory Data Analysis — Unit 2 Comprehensive Lecture Notes
## Module 2: Data Evolution (Week 2)
### Subject: OLMCA616 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Define** data and explain data evolution
2. **Identify** different data types in R (Numeric, Integer, Logical, Complex)
3. **Read and write** data files (CSV, Text, Excel)
4. **Classify** data into Qualitative, Quantitative, Graphical, and High Dimensional types
5. **Explain** different sources of data (Time Series, Transactional, Biological, Spatial, Social Network)
6. **Compare** different data types with real-world examples
7. **Answer** exam questions using 5-mark framework

---

## 1. Data Definition

### Hook 🎯
Data = information ke basic building blocks! Business decisions ho ya scientific research — sab data pe depend karta hai. "Data is the new oil" — ye quote sach hai!

### Definition 🌟
> **"Data definition involves describing the characteristics of data, including its structure, form, and attributes."**

### Key Points 🌟
- Data represents **characteristics of objects and events** in coded form
- Coded as: **numbers, letters, symbols**
- Represents: objects, events, classes, transactions
- Used in: calculations, representations, analysis
- **Software industry** — most businesses rely on data for decisions
- Without data, no analysis, no insights, no predictions!

### Real-Life Example 🌟
Imagine ek shopkeeper — sales data rakhta hai. Us data se decide karta hai: kaunsa product best sell ho raha hai? Kaunse din zyada customers aate hain? Ye sab DATA se possible hai!

---

## 2. Data Types in R

### Hook 🎯
R mein har data ka ek type hota hai — jaise integers, decimals, text, boolean. Type samajhna zaroori hai — warna analysis galat hoga!

### Data Types 🌟

| Data Type | Description | Example | Key Note |
|-----------|-------------|---------|----------|
| **Numeric** | Decimal values | 3.14, 2.5, 10.7 | Default for numbers |
| **Integer** | Whole numbers | 5L, 10L, 100L | L suffix required |
| **Character** | Text strings | "hello", 'world' | Quotes mandatory |
| **Logical** | Boolean values | TRUE, FALSE | 0 or 1 internally |
| **Complex** | Complex numbers | 3 + 2i | Real + imaginary |

### Data Type Selection 🌟
> **"Choose the appropriate data type based on the nature of the data to optimize storage and facilitate analysis."**

- Wrong type = memory waste + wrong analysis
- Integer uses less memory than Numeric for whole numbers
- Character needed for text — can't use numeric
- Logical for TRUE/FALSE conditions

### Code Examples 🌟
```r
# Check data type
x <- 3.14
class(x)    # "numeric"

y <- 5L
class(y)    # "integer"

z <- "hello"
class(z)    # "character"

flag <- TRUE
class(flag) # "logical"

c <- 3 + 2i
class(c)    # "complex"
```

---

## 3. Reading & Writing Data Files

### Hook 🎯
Data bahar se aata hai — files, databases, APIs. R mein import/export kaise karein? Ye seekhna bahut zaroori hai real-world analysis ke liye!

### Reading Data 🌟

| Function | File Type | Usage |
|----------|-----------|-------|
| `read.csv()` | CSV files | Most common |
| `read.delim()` | Tab-delimited text | TSV files |
| `read.table()` | Generic text | Flexible |
| `read_excel()` | Excel files | Needs readxl package |

### Reading Parameters 🌟

| Parameter | Purpose | Example |
|-----------|---------|---------|
| `header` | First row has column names? | `header = TRUE` or `FALSE` |
| `sep` | Field separator | `sep = ","` for CSV, `sep = "\t"` for TSV |
| `dec` | Decimal character | `dec = "."` (default) |

### Working Directory 🌟
```r
# Check current directory
getwd()

# Set working directory
setwd("path/to/folder")

# Read file
data <- read.csv("airtravel.csv")
# Or with full path
data <- read.csv("D:/folder1/airtravel.csv")
```

### Writing Data 🌟
```r
# Write CSV
write.csv(data, "output.csv", row.names = FALSE)

# Write Excel (needs openxlsx package)
library(openxlsx)
write.xlsx(data, "output.xlsx")

# Write text file
write.table(data, "output.txt", sep = "\t")
```

### Error Handling 🌟
- R provides mechanisms for handling errors during file operations
- Use `tryCatch()` for robust code
- Check if file exists before reading
- Validate data after reading

---

## 4. Data Science and Data Evolution

### Hook 🎯
Data science = data ke saath experimentation! Aur data evolution — simple numbers se complex big data tak ka safar!

### Data Science 🌟
> **"Data science is all about experimenting with raw or structured data."**

- **Data is fuel** — drives business to right path
- Provides actionable insights
- Requires: statistical analysis + programming + domain knowledge

### Data Evolution 🌟

| Era | Characteristics |
|-----|----------------|
| **Traditional** | Simple numbers, small datasets, manual analysis |
| **Digital** | Computers, databases, structured data |
| **Big Data** | Massive, real-time, unstructured, multi-source |

### Three V's of Big Data 🌟

| V | Meaning | Description |
|---|---------|-------------|
| **Volume** | Size | Terabytes, petabytes of data |
| **Velocity** | Speed | Real-time data generation |
| **Variety** | Types | Structured, semi-structured, unstructured |

---

## 5. Types of Data: Qualitative / Categorical

### Hook 🎯
Qualitative data = descriptive, categories mein divide hota hai. Numbers se measure nahi kar sakte — par analysis mein bahut useful hai!

### Definition 🌟
> **"Qualitative or Categorical Data describes the object using a finite set of discrete classes. It cannot be counted or measured easily using numbers."**

### Two Sub-Types 🌟

| Type | Description | Ordering? | Examples |
|------|-------------|-----------|----------|
| **Nominal** | Categories with NO natural order | No | Gender (M/F), Color (Red/Blue), City |
| **Ordinal** | Categories WITH natural order | Yes | Education (HS→Bachelor→Master), Rating (Low→Medium→High) |

### Examples 🌟

**Nominal Data:**
- Gender: Male, Female
- Color: Red, Blue, Green
- Blood Type: A, B, AB, O
- Marital Status: Single, Married, Divorced

**Ordinal Data:**
- Education: High School < Bachelor < Master < PhD
- Survey: Strongly Disagree < Disagree < Neutral < Agree < Strongly Agree
- Pain Level: None < Mild < Moderate < Severe
- Grade: F < D < C < B < A

### Representation 🌟
- **Frequency tables** — count of each category
- **Bar charts** — visual comparison of categories
- **Pie charts** — proportion of each category
- **In R:** Use `factor()` for categorical variables

### Exam Tip 🌟
Qualitative data ko kabhi bhi mathematical operations mat karo — average nikalna meaningless hai! Gender ka average nahi nikal sakte!

---

## 6. Types of Data: Quantitative / Numeric

### Hook 🎯
Quantitative data = numbers! Countable ya measurable. Mathematical operations apply hote hain — mean, median, standard deviation — sab possible hai!

### Definition 🌟
> **"Quantitative data can be counted or measured and expressed in numerical values."**

### Two Sub-Types 🌟

| Type | Description | Values | Examples |
|------|-------------|--------|----------|
| **Discrete** | Countable, whole numbers only | Integers | Students: 30, Cars: 15 |
| **Continuous** | Measurable, any value in range | Decimals | Height: 5.8 ft, Temp: 37.2°C |

### Examples 🌟

**Discrete Data:**
- Number of students in class (can't be 30.5)
- Number of cars in parking lot
- Number of defects in product
- Pages in a book

**Continuous Data:**
- Height (5.8 ft, 5.81 ft, 5.812 ft — any precision)
- Weight (65.5 kg, 65.53 kg)
- Temperature (37.2°C, 37.25°C)
- Distance, Time, Salary

### Representation 🌟
- **Histogram** — frequency distribution
- **Box plot** — spread and outliers
- **Scatter plot** — relationship between two variables
- **Line chart** — trend over time

### Analysis Tools 🌟
- Central tendency: Mean, Median, Mode
- Dispersion: Range, Variance, Standard Deviation
- Relationship: Correlation, Regression
- Comparison: T-test, ANOVA

### Key Difference 🌟
| Feature | Discrete | Continuous |
|---------|----------|------------|
| Values | Whole numbers only | Any value in range |
| Counting | Countable | Measurable |
| Gaps | Between values | No gaps |
| Example | Students: 30 | Height: 5.812 ft |

---

## 7. Types of Data: Graphical Data & Flat Files

### Hook 🎯
Graphical data = visual representations! Images, charts. Flat files = simple text-based storage. Dono important hain data handling mein!

### Graphical Data 🌟

| Aspect | Details |
|--------|---------|
| **What** | Visual representations — images, charts, graphs |
| **Use** | Visualization, pattern recognition, presentation |
| **Formats** | PNG, JPEG (raster); SVG (vector); PDF (documents) |
| **Purpose** | Communication, analysis, documentation |

### Flat Files 🌟
> **"Flat files are plain text files that store structured data."**

| Format | Separator | Extension | Example |
|--------|-----------|-----------|---------|
| **CSV** | Comma | .csv | name,age,city |
| **TSV** | Tab | .tsv | name\tage\tcity |
| **Fixed-width** | Position | .txt | John25Delhi |

**Characteristics:**
- Simple & efficient for data transfer
- Small to medium datasets
- Easy to create, read, edit
- Processed using text editors or programs

### Databases 🌟

| Type | Structure | Examples | Use Case |
|------|-----------|----------|----------|
| **Relational** | Tables with relations | MySQL, PostgreSQL | Structured data, SQL queries |
| **NoSQL** | Document-based, flexible | MongoDB, Cassandra | Semi-structured, scalable |
| **Big Data** | Distributed | Hadoop, Spark | Massive datasets |

---

## 8. Types of Data: High Dimensional Data

### Hook 🎯
Jab data mein bahut zyada variables hon — thousands ya millions — woh high dimensional data hai! Modern data science ka biggest challenge!

### Definition 🌟
> **"High dimensional data is data with many variables/features (dimensions). Each observation is described by a large number of attributes."**

### Examples 🌟

| Domain | Data | Dimensions |
|--------|------|------------|
| **Genomics** | Gene expression | 20,000+ genes per sample |
| **Image Processing** | Images | Thousands of pixels as features |
| **Text Mining** | Documents | Thousands of words (TF-IDF vectors) |
| **Finance** | Stock data | Hundreds of indicators |

### Challenges 🌟

| Challenge | Description |
|-----------|-------------|
| **Curse of Dimensionality** | As dimensions increase, distance between points becomes meaningless |
| **Computational Complexity** | Increases exponentially with dimensions |
| **Memory Requirements** | Need huge storage and processing |
| **Visualization** | Impossible beyond 3 dimensions directly |
| **Overfitting** | Models become too complex |

### Solutions 🌟
- **Dimensionality Reduction:** PCA, MDS, t-SNE
- **Feature Selection:** Choose most important features
- **Regularization:** L1 (Lasso), L2 (Ridge)
- **Sparse Data Techniques:** Exploit sparsity

### Real-Life Example 🌟
Human genome: 3 billion base pairs! Ye extreme high dimensional data hai. Isko analyze karne ke liye dimensionality reduction zaroori hai!

---

## 9. Sources of Data: Time Series Data

### Hook 🎯
Time series = time ke saath data! Stock prices, weather, sales — sab time ke saath change hote hain. Pattern dhundna aur predict karna — yehi time series analysis hai!

### Definition 🌟
> **"Time series data is a sequence of data points collected or recorded at regular time intervals."**

### Characteristics / Components 🌟

| Component | Description | Example |
|-----------|-------------|---------|
| **Trend** | Long-term direction (up/down) | Stock market going up over years |
| **Seasonality** | Repeating patterns at fixed intervals | Holiday sales spike every December |
| **Cyclical** | Longer-term fluctuations | Economic cycles (boom/recession) |
| **Irregular** | Random, unpredictable noise | Unexpected events (pandemic) |

### Stationarity 🌟
> **"A time series is stationary if its statistical properties (mean, variance) don't change over time."**

- Many algorithms REQUIRE stationary data
- Test: Augmented Dickey-Fuller test
- Convert: Differencing, transformation

### How to Analyze Time Series 🌟

| Method | Purpose |
|--------|---------|
| **Forecasting** | Predict future values |
| **Segmentation** | Group similar time periods |
| **Classification** | Categorize time series |
| **Descriptive Analysis** | Find patterns in given data |

### Tools in R 🌟
```r
# Create time series object
ts_data <- ts(data, frequency=12, start=c(2020,1))

# Decompose into components
decomposed <- decompose(ts_data)
plot(decomposed)

# Forecast
library(forecast)
forecasted <- forecast(ts_data, h=12)
plot(forecasted)
```

### Examples 🌟
- Stock prices (daily, hourly)
- Weather data (temperature, rainfall)
- Sales figures (monthly, quarterly)
- Patient admissions (daily)
- Website traffic (hourly)

---

## 10. Sources of Data: Transactional Data

### Hook 🎯
Har business transaction record hota hai — purchase, sale, payment. Ye data business intelligence aur fraud detection ke liye gold hai!

### Definition 🌟
> **"Transactional data records the details of business transactions — each with a unique identifier (trans ID) and list of items."**

### Components 🌟

| Component | Description |
|-----------|-------------|
| **Transaction ID** | Unique identifier for each transaction |
| **Timestamp** | When transaction occurred |
| **Items/Products** | What was purchased/sold |
| **Quantities** | How many |
| **Prices** | Cost of each item |
| **Customer Info** | Who made the transaction |
| **Payment Method** | Cash, card, online |

### Uses 🌟
- **Business Analysis** — sales trends, popular products
- **Fraud Detection** — unusual transaction patterns
- **Accounting** — financial records, auditing
- **Inventory Management** — stock levels, reorder points
- **Customer Analysis** — buying behavior, loyalty

### Examples 🌟
- E-commerce orders (Amazon, Flipkart)
- Bank transactions (deposits, withdrawals)
- Credit card payments
- Insurance claims
- Hospital admissions

### Transactional vs Analytical Data 🌟

| Feature | Transactional | Analytical |
|---------|--------------|------------|
| **Purpose** | Record transactions | Analyze patterns |
| **Speed** | Fast processing | Complex queries |
| **Structure** | Normalized | Denormalized |
| **Volume** | Many small records | Large aggregated data |

---

## 11. Sources of Data: Biological Data

### Hook 🎯
Biological data = life science ka data! DNA, proteins, medical records — isse disease understanding, drug discovery, personalized medicine mein revolution aa raha hai!

### Definition 🌟
> **"Biological data is data generated from biological processes and research — including DNA sequences, protein structures, gene expression, and clinical records."**

### Types 🌟

| Type | Description | Examples |
|------|-------------|----------|
| **Genomic** | DNA/RNA sequences | Gene sequences, mutations |
| **Proteomic** | Protein data | Structures, interactions |
| **Clinical** | Medical records | Patient data, imaging |
| **Metabolomic** | Metabolic data | Pathways, chemicals |

### Major Databases 🌟

| Database | Content |
|----------|---------|
| **GenBank** | DNA sequences |
| **NCBI** | Comprehensive biomedical data |
| **PDB** | 3D protein structures |
| **UniProt** | Protein sequences & annotations |
| **KEGG** | Biological pathways |

### Challenges 🌟

| Challenge | Description |
|-----------|-------------|
| **Massive Volume** | Human genome = 3 billion base pairs |
| **Complexity** | Gene-protein-disease relationships |
| **Integration** | Combining different data types |
| **Privacy** | Patient data protection |

### Tools in R 🌟
- **Bioconductor** — genomic analysis packages
- **biomaRt** — data retrieval from databases
- **limma** — differential expression analysis

### Real-Life Impact 🌟
- Personalized medicine — treatment based on genes
- Drug discovery — finding new medicines
- Disease prediction — genetic risk assessment
- Cancer research — tumor analysis

---

## 12. Sources of Data: Spatial Data

### Hook 🎯
Spatial data = location data! Kahan pe kya hai — ye batata hai. Maps, GPS, satellite images — sab spatial data hain!

### Definition 🌟
> **"Spatial data is data with a geographical or spatial component — contains location coordinates, boundaries, and area information."**

### Two Main Types 🌟

| Type | Description | Components | Examples |
|------|-------------|------------|----------|
| **Vector** | Points, Lines, Polygons | Individual features | Cities, roads, boundaries |
| **Raster** | Grid-based | Cells with values | Satellite images, elevation |

### Vector Data Components 🌟

| Component | Description | Example |
|-----------|-------------|---------|
| **Points** | Individual locations | Cities, landmarks |
| **Lines/Polylines** | Connected points | Roads, rivers |
| **Polygons** | Enclosed areas | Land parcels, borders |

### Topological Relationships 🌟
Vector data maintains:
- **Adjacency** — what's next to what
- **Connectivity** — what connects to what
- **Containment** — what's inside what

### Applications 🌟
- **GIS** — Geographic Information Systems
- **Urban Planning** — city development
- **Environmental Studies** — habitat mapping
- **Navigation** — GPS, maps
- **Agriculture** — crop monitoring
- **Disaster Management** — flood mapping

### Tools in R 🌟
```r
library(sf)        # Simple Features for spatial data
library(sp)        # Classical spatial data
library(leaflet)   # Interactive maps
library(raster)    # Raster data analysis
```

---

## 13. Sources of Data: Social Network Data

### Hook 🎯
Social networks = relationships ka data! Facebook, LinkedIn, Twitter — sab network data generate karte hain. Who knows whom? Who influences whom? Ye sab analyze karte hain!

### Definition 🌟
> **"Social network data represents relationships between entities — nodes (actors) connected by edges (relationships)."**

### Components 🌟

| Component | Description | Example |
|-----------|-------------|---------|
| **Nodes** | Actors/entities | People, organizations |
| **Edges** | Relationships | Friendships, interactions |
| **Weights** | Relationship strength | Close friends vs acquaintances |
| **Attributes** | Node/edge properties | Age, location, type |

### Applications 🌟

| Application | Description |
|-------------|-------------|
| **Community Detection** | Finding groups/clusters |
| **Influence Analysis** | Who affects whom |
| **Recommendation Systems** | Suggesting connections |
| **Viral Marketing** | Spreading information |
| **Epidemiology** | Disease spread modeling |

### Challenges 🌟

| Challenge | Description |
|-----------|-------------|
| **Dynamic Nature** | Connections change over time |
| **Large Scale** | Millions/billions of users |
| **Sparsity** | Not all possible connections exist |
| **Privacy** | User data protection |
| **Multi-relational** | Different types of relationships |

### Tools in R 🌟
```r
library(igraph)    # Network analysis
# Gephi — external tool for visualization
```

### Real-Life Examples 🌟
- Facebook friend network
- Twitter follower/following
- LinkedIn professional connections
- Citation networks in research
- Collaboration networks in organizations

---

## 14. Comparison of Data Types

| Data Type | Nature | Storage | Analysis | Example |
|-----------|--------|---------|----------|---------|
| **Numeric** | Measurable | Efficient | Mathematical | Age, Income |
| **Categorical** | Discrete classes | Compact | Frequency-based | Gender, City |
| **Graphical** | Visual | Large | Pattern-based | Images, Charts |
| **High Dimensional** | Many features | Very large | Dimensionality reduction | Genes, Pixels |
| **Time Series** | Temporal | Sequential | Trend/Forecast | Stock, Weather |
| **Transactional** | Event records | Indexed | Aggregation | Orders, Payments |
| **Biological** | Life science | Massive | Statistical/ML | DNA, Medical |
| **Spatial** | Geographical | Large | Spatial analysis | Maps, GPS |
| **Social Network** | Relationships | Graph-based | Network analysis | Friends, Links |

---

## 15. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Types of Data (4)
**"N-C-G-H"** → Numeric, Categorical, Graphical, High Dimensional
→ *"Never Cheat Good Humans"*

### Trick 2: Data Sources (5)
**"T-T-B-S-S"** → Time Series, Transactional, Biological, Spatial, Social Network
→ *"Two Tigers Beat Seven Snakes"*

### Trick 3: Time Series Components (4)
**"T-S-C-I"** → Trend, Seasonality, Cyclical, Irregular
→ *"The Sun Comes In"* (sun rises, sets, cycles, sometimes irregular!)

### Trick 4: Qualitative Sub-Types
**"N-O"** → Nominal (No order), Ordinal (Has Order)
→ *"NO order — NO problem!"*

### Trick 5: Quantitative Sub-Types
**"D-C"** → Discrete (Countable), Continuous (measurable)
→ *"Discrete Count, Continuous Can-be-any"*

### Trick 6: 3 V's of Big Data
**"V-V-V"** → Volume, Velocity, Variety
→ *"Very Very Vast!"*

---

## 16. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Treating categorical as numeric (averaging gender) | Use frequency tables, mode |
| Ignoring data types in R (implicit conversion) | Explicitly check with class() |
| Confusing discrete and continuous | Discrete = countable, Continuous = measurable |
| Forgetting L for integer | 5L not 5 (5 is numeric) |
| Treating nominal same as ordinal | Nominal has no order, ordinal has order |
| Ignoring time series seasonality | Always check for seasonal components |
| Not handling high dimensions | Apply PCA/dimensionality reduction |
| Confusing spatial and network data | Spatial = geographic, Network = relationships |
| Not validating data after reading | Always check str(), summary(), head() |
| Mixing transactional with analytical data | Different purposes, different structures |

---

## 17. 5-Mark Answer Framework

**Q: "Explain different types of data with examples."** (5 marks)

**Answer Structure:**

**Introduction (1 mark):**
"Data can be classified into various types based on its nature, measurement scale, and structure. Understanding data types is essential for choosing appropriate analysis methods."

**Types (3 marks):**
1. **Numeric/Quantitative:** Measurable values
   - Discrete (countable): Students in class
   - Continuous (measurable): Height, temperature
2. **Categorical/Qualitative:** Discrete classes
   - Nominal (no order): Gender, Color
   - Ordinal (has order): Education level, Rating
3. **Graphical:** Visual representations — images, charts
4. **High Dimensional:** Many features — gene expression, text data

**Sources (1 mark):**
- Time Series, Transactional, Biological, Spatial, Social Network

**Conclusion (if space):**
"Proper data type identification leads to correct analysis and meaningful results."

---

## 18. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_EDA_W2_Notes.pdf | Week 2 notes (26 pages, 57063 chars) — Data types, data sources, all topics |
| OLMCA616-EDA Module 2 PPT | 42 pages — visual reference (image-based) |
| Syllabus OLMCA616 | Module 2 scope |
| VIT MCA FAT Pattern | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 19. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 2) | Status | Section |
|---------------------------|--------|---------|
| Data Evolution: Introduction | ✅ | Section 4 |
| Types of Data - Numeric | ✅ | Section 6 |
| Types of Data - Categorical | ✅ | Section 5 |
| Types of Data - Graphical | ✅ | Section 7 |
| Types of Data - High Dimensional | ✅ | Section 8 |
| Sources - Time Series Data | ✅ | Section 9 |
| Sources - Transactional Data | ✅ | Section 10 |
| Sources - Biological Data | ✅ | Section 11 |
| Sources - Spatial Data | ✅ | Section 12 |
| Sources - Social Network Data | ✅ | Section 13 |

### Coverage: 10/10 topics = 100% ✅

---

*Subject: Exploratory Data Analysis (OLMCA616)*
*Unit 2 — Module 2: Data Evolution*
*Last Updated: November 2025 | VIT MCA Semester 3*
