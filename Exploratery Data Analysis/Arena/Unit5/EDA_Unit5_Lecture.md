# Exploratory Data Analysis — Unit 5 Comprehensive Lecture Notes
## Module 5: Data Visualization (Week 6 + Week 7)
### Subject: OLMCA616 | Programme: MCA | VIT Online Education

---

## Learning Objectives
1. **Define** data visualization and its importance
2. **Create** Histograms, Pie charts, Box plots in R
3. **Explain** Multi-vari charts, Run charts, Andrew plots, Pareto charts
4. **Build** Scatter plots and Stem-and-leaf plots
5. **Implement** Heat maps and Voronoi diagrams
6. **Visualize** Geo data and streaming data
7. **Compare** different visualization techniques
8. **Answer** exam questions using 5-mark framework

---

## 1. Introduction to Data Visualization

### Hook 🎯
Data ko numbers mein dekhna mushkil hai — par visual banao toh patterns turant samajh aa jaate hain! Data visualization = data ki language!

### Definition 🌟
> **"Data Visualization is the process of converting information into a visual environment, making data easier to understand and derive conclusions from. Data is visualized using plots, graphs, maps, and images."**

### Why Important? 🌟

| Benefit | Description |
|---------|-------------|
| **Pattern Recognition** | Trends, correlations, outliers easily spotted |
| **Effective Communication** | Non-technical audience ko insights samjhao |
| **Decision Making** | Data-driven decisions, evidence-based |
| **Storytelling** | Data se kahani banao — engaging presentations |
| **Exploration** | Hidden insights discover karo |

### Platforms 🌟
| Platform | Type |
|----------|------|
| **Tableau** | Commercial BI tool |
| **Power BI** | Microsoft's BI solution |
| **Google Charts** | Free web-based |
| **Matplotlib** | Python library |
| **ggplot2** | R package (most powerful) |

### Features of Good Visualization 🌟
- Streaming data support
- AI integration
- Embeddability
- Collaboration features
- Interactive exploration
- Self-service capabilities

---

## 2. Histogram

### Hook 🎯
Continuous data ka distribution dekhna hai? Histogram banao — bars adjacent hote hain, unlike bar chart!

### Definition 🌟
> **"A histogram is a graphical representation of the distribution of continuous data. It divides data into bins and displays frequency or density in each bin."**

### Characteristics 🌟

| Feature | Description |
|---------|-------------|
| **X-axis** | Continuous data values (bins) |
| **Y-axis** | Frequency or density |
| **Bars** | ADJACENT — no gaps between bars |
| **Bins** | Number of intervals (adjustable) |
| **Shape** | Shows distribution shape (normal, skewed) |

### R Code 🌟
```r
# Basic histogram
hist(data)

# Customized
hist(data, breaks=10, col="blue", border="red",
     main="Distribution of Values",
     xlab="Values", ylab="Frequency")
```

### Uses 🌟
- Distribution shape — normal, skewed, bimodal
- Central tendency — where data is concentrated
- Spread — how wide is the distribution
- Outliers — unusual values visible

### Histogram vs Bar Chart 🌟

| Feature | Histogram | Bar Chart |
|---------|-----------|-----------|
| **Data Type** | Continuous | Categorical |
| **Bars** | Adjacent (no gaps) | Separated (gaps) |
| **Order** | No specific order | Any order |
| **Purpose** | Distribution shape | Category comparison |

---

## 3. Pie Chart

### Hook 🎯
Proportions dikhane ke liye pie chart best hai — par categories kam honi chahiye, warna confusing!

### Definition 🌟
> **"A pie chart is a circular chart divided into sectors, each representing the relative size of data. Also called a circle graph."**

### Characteristics 🌟
- Base is circle representing 100% of data
- Angle of each sector proportional to relative frequency
- Best for few categories (3-7)
- Simple and easy to understand

### R Code 🌟
```r
values <- c(30, 25, 20, 15, 10)
labels <- c("A", "B", "C", "D", "E")
colors <- c("red", "blue", "green", "yellow", "purple")

pie(values, labels=labels, col=colors,
    main="Pie Chart Example")
```

### Advantages 🌟
- Simple, visually appealing
- Shows proportions clearly
- Good for presenting to non-technical audience

### Disadvantages 🌟
- Hard to compare similar-sized slices
- Not suitable for many categories
- For precise comparison, use bar chart

---

## 4. Box Plot (Box-and-Whisker)

### Hook 🎯
Five-number summary ek diagram mein! Outliers instantly detect karo — box plot data ka X-ray hai!

### Definition 🌟
> **"A box plot is a standardized way of displaying data based on five-number summary: minimum, Q1, median, Q3, maximum."**

### Five-Number Summary 🌟

| Number | Description |
|--------|-------------|
| **Minimum** | Smallest value (excluding outliers) |
| **Q1 (25th)** | 25% data below this |
| **Median (50th)** | Middle value |
| **Q3 (75th)** | 75% data below this |
| **Maximum** | Largest value (excluding outliers) |

### Components 🌟

| Component | Description |
|-----------|-------------|
| **Box** | Q1 to Q3 (IQR = middle 50%) |
| **Line in box** | Median |
| **Whiskers** | Extend to min/max (1.5×IQR rule) |
| **Dots** | Outliers (outside whiskers) |
| **Notch** | Confidence interval around median |

### R Code 🌟
```r
# Basic box plot
boxplot(data)

# With notch
boxplot(data, notch=TRUE, col="lightblue")

# Multiple groups
boxplot(mpg ~ cyl, data=mtcars, col="lightgreen")
```

### Uses 🌟
- Detect skewness — unequal whiskers
- Compare distributions — side by side
- Find outliers — dots outside whiskers
- Identify spread — IQR width

---

## 5. Multi-vari Chart & Run Chart

### Multi-vari Chart 🌟
> **"A multi-vari chart displays multiple variables on the same chart to identify patterns and relationships."**

**Characteristics:**
- Shows how variables interact
- Useful for production process analysis
- Example: Monitor temperature, pressure, time simultaneously

### Run Chart 🌟
> **"A run chart is a line plot of data in time order — shows trends, shifts, patterns."**

**Characteristics:**
- Similar to control chart but WITHOUT control limits
- Tracks process over time
- Detects trends, shifts, cycles

### R Code 🌟
```r
# Run chart
plot(data, type="l", main="Run Chart")

# Multi-vari
matplot(x, y_matrix, type="l", lty=1)
```

---

## 6. Andrew Plots

### Hook 🎯
High-dimensional data ko visualize karna mushkil — Andrew plots se har observation ek curve ban jaata hai!

### Definition 🌟
> **"Andrew Plots visualize multivariate data by transforming each observation into a smooth curve using Fourier series."**

### Formula 🌟
```
f(t) = x₁/√2 + x₂·sin(t) + x₃·cos(t) + x₄·sin(2t) + x₅·cos(2t) + ...
```
where t ranges from -π to π

### Characteristics 🌟
- Similar observations → similar curves
- Helps identify clusters and outliers
- Smoothed version of parallel coordinate plane
- Each curve = one observation

### Uses 🌟
- High-dimensional data visualization
- Cluster detection
- Outlier identification
- Pattern recognition

---

## 7. Pareto Chart

### Hook 🎯
80% problems 20% causes se aate hain — Pareto principle! Pareto chart se important causes identify karo!

### Definition 🌟
> **"A Pareto chart is a bar chart with bars sorted in descending order PLUS a cumulative line graph. Based on Pareto Principle (80/20 rule)."**

### Components 🌟
1. **Bars** — sorted descending (largest first)
2. **Cumulative line** — running total percentage
3. **80% line** — identifies vital few causes

### R Code 🌟
```r
library(Pareto)
pareto.chart(values, names=categories,
             main="Pareto Analysis",
             ylab="Frequency",
             xlab="Categories")
```

### Uses 🌟
- Quality control — defect prioritization
- Root cause analysis
- Resource allocation
- Problem-solving (focus on vital few)

---

## 8. Scatter Plot

### Hook 🎯
Do variables ka relationship dekhna hai? Scatter plot banao — correlation instantly dikh jaata hai!

### Definition 🌟
> **"A scatter plot represents the relationship between two quantitative variables by plotting points on an X-Y coordinate system."**

### Types 🌟
| Type | Description |
|------|-------------|
| **Density Scatter** | Overlapping points show density |
| **Labelled Scatter** | Points labeled with identifiers |

### Interpretation 🌟

| Pattern | Meaning |
|---------|---------|
| **Upward** | Positive correlation (as X↑, Y↑) |
| **Downward** | Negative correlation (as X↑, Y↓) |
| **Random** | No correlation |
| **Curved** | Non-linear relationship |

### R Code 🌟
```r
# Basic scatter plot
plot(mtcars$wt, mtcars$mpg)

# Customized
plot(mtcars$wt, mtcars$mpg,
     pch=20, col="darkred",
     main="Scatterplot: Weight vs MPG",
     xlab="Weight (pounds)",
     ylab="Miles per Gallon")

# Add trend line
abline(lm(mpg ~ wt, data=mtcars), col="blue")
```

### Uses 🌟
- Correlation detection
- Trend identification
- Outlier spotting
- Relationship strength assessment

---

## 9. Stem-and-Leaf Plot

### Hook 🎯
Histogram distribution dikhata hai par values kho jaati hain. Stem-and-leaf DONO karta hai — distribution bhi, actual values bhi!

### Definition 🌟
> **"A stem-and-leaf plot displays the distribution of data while preserving actual values. Each value split into stem (leading) and leaf (trailing)."**

### Example 🌟
```
Data: 12, 15, 18, 22, 25, 28, 31

Stem | Leaf
  1  | 2 5 8
  2  | 2 5 8
  3  | 1
```

### Advantages 🌟

| Advantage | Description |
|-----------|-------------|
| **Preserves values** | Unlike histogram, actual data retained |
| **Shows shape** | Distribution visible |
| **Easy to construct** | By hand possible |
| **Comparison** | Side-by-side comparison easy |

### R Code 🌟
```r
stem(data)
```

### Limitation 🌟
Best for small to medium datasets — large datasets become unwieldy.

---

## 10. Heat Maps

### Hook 🎯
Matrix data ko colors se represent karo — patterns instantly visible! Correlation matrix, gene expression — sab heat maps se!

### Definition 🌟
> **"A heat map is a two-dimensional visualization using color to represent values in matrix data."**

### Features 🌟
| Feature | Description |
|---------|-------------|
| **Color Scale** | Gradient from low to high values |
| **Labels** | Row and column labels for context |
| **Hierarchical Clustering** | Groups similar items together |
| **2D Display** | Relationships between two sets of categories |

### R Code 🌟
```r
# Basic heatmap
heatmap(data_matrix)

# Advanced with pheatmap
library(pheatmap)
pheatmap(data_matrix,
         clustering_distance_rows="correlation",
         clustering_distance_cols="correlation")
```

### Uses 🌟
- Correlation matrices
- Gene expression analysis
- Website click patterns
- Time-series heatmap
- Performance metrics visualization

---

## 11. Voronoi Diagrams & Geo Data

### Voronoi Diagrams 🌟
> **"Voronoi diagrams partition space into regions based on distance to seed points. Each region contains all points closest to one seed."**

**Features:**
- Centroid — center of each Voronoi cell
- Nearest neighbors — along edges of cell
- Cell boundaries — equidistant from two seeds
- Related to Delaunay Triangulation (dual)

**Uses:**
- Spatial analysis
- Nearest neighbor problems
- Facility location
- Territory mapping

### Geo Data Visualization 🌟
> **"Geo data visualization represents geographic/spatial data with coordinates (latitude, longitude) on interactive maps."**

**Characteristics:**
- Dynamic — updates in real-time
- Interactive maps with streaming
- Spatial context for analysis

**R Packages:**

| Package | Purpose |
|---------|---------|
| **leaflet** | Interactive maps |
| **ggmap** | ggplot2 + Google Maps |
| **sf** | Simple Features for spatial |
| **sp** | Classical spatial data |

### Comparison 🌟

| Feature | Voronoi | Geo Data |
|---------|---------|----------|
| **Purpose** | Spatial partitioning | Geographic mapping |
| **Basis** | Distance to seeds | Coordinates |
| **Use** | Nearest neighbor | Location analysis |

---

## 12. Learning Tricks

### Trick 1: Chart Types (11)
**"H-P-B-M-R-A-P-S-S-H-V"**
→ Histogram, Pie, Box, Multi-vari, Run, Andrew, Pareto, Scatter, Stem, Heat, Voronoi
→ *"Happy Pandas Bring Many Rare Animals — Pretty Smart, So Happy, Very!"*

### Trick 2: Distribution Charts (3)
**"H-S-B"** → Histogram, Stem-and-leaf, Box plot
→ *"Histogram Shows Better!"*

### Trick 3: Relationship Charts
**"S-M-A"** → Scatter, Multi-vari, Andrew plots
→ *"See Multiple Angles!"*

### Trick 4: Box Plot Components (5)
**"M-Q-M-Q-M"** → Min, Q1, Median, Q3, Max
→ *"My Queen Makes Queen Magnificent!"*

---

## 13. Comparison Table

| Chart | Data Type | Purpose | R Function |
|-------|-----------|---------|------------|
| **Histogram** | Continuous | Distribution | hist() |
| **Pie** | Categorical | Proportions | pie() |
| **Box Plot** | Any | Summary + outliers | boxplot() |
| **Multi-vari** | Multiple | Multi-variable | matplot() |
| **Run Chart** | Time series | Trend over time | plot(type="l") |
| **Andrew Plots** | Multivariate | High-dimensional | andrews() |
| **Pareto** | Categorical | 80/20 prioritization | pareto.chart() |
| **Scatter** | 2 numeric | Relationship | plot() |
| **Stem-Leaf** | Numeric | Distribution + values | stem() |
| **Heat Map** | Matrix | Pattern with colors | heatmap() |
| **Voronoi** | Spatial | Partitioning | deldir() |

---

## 14. Common Mistakes ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Using pie for many categories | Use bar chart instead |
| Confusing histogram with bar chart | Histogram = continuous, Bar = categorical |
| Not checking skewness | Always examine distribution first |
| Using 3D charts unnecessarily | 2D is clearer |
| Ignoring color choices | Use colorblind-friendly palettes |
| Overcrowding charts | Keep it simple, readable |

---

## 15. 5-Mark Answer Framework

**Q: "Explain different types of charts used in data visualization."** (5 marks)

**Answer:**

**Introduction (1):**
"Data visualization uses various charts to represent data visually for better understanding."

**Charts with description (3):**
1. **Histogram** — continuous data distribution, adjacent bars
2. **Pie Chart** — proportions, sectors of circle
3. **Box Plot** — five-number summary, outliers
4. **Scatter Plot** — 2 variables relationship
5. **Heat Map** — matrix data with colors

**Conclusion/Comparison (1):**
"Each chart suited for specific data types and analysis purposes."

---

## 16. Topic Coverage ✅

| Syllabus Topic | Status |
|----------------|--------|
| Histogram | ✅ |
| Pie Charts | ✅ |
| Box Plot | ✅ |
| Multi-vari Chart | ✅ |
| Andrew Plots | ✅ |
| Run Chart | ✅ |
| Pareto Chart | ✅ |
| Scatter Plot | ✅ |
| Stem-and-Leaf | ✅ |
| Heat Maps | ✅ |
| Voronoi Diagrams | ✅ |
| Geo Data | ✅ |
| Streaming Data | ✅ |

### Coverage: 13/13 = 100% ✅

---

*Unit 5 — Data Visualization | EDA (OLMCA616) | VIT MCA*
