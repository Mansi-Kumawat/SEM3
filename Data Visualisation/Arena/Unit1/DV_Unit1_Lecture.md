# Data Visualization — Unit 1 Comprehensive Lecture Notes
## Module 1: Introduction to Data Visualization (Week 1 + Week 2)
### Subject: OLMCA618 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Define** Data Visualization and explain its importance
2. **Describe** the 6-step Visualization Pipeline
3. **Identify** 5 types of Image Labelling
4. **Classify** 4 types of data (Qualitative, Temporal, Spatial, Multivariate)
5. **Explain** Visual Aesthetics and their accuracy ranking
6. **Describe** 3 components of Data-to-Aesthetic Mapping
7. **Differentiate** Cartesian, Polar, and Nonlinear coordinate systems
8. **Identify** 3 types of Color Scales (Categorical, Sequential, Diverging)
9. **Answer** exam questions using the 5-mark answer framework

---

## 1. What is Data Visualization?

### Hook 🎯
Socho ek company ke paas 10,000 customers ka data hai — sales, age, location, spending patterns. Ek table mein dekhoge toh kuch samajh nahi aayega. Lekin ek scatter plot ya heat map banao — turant patterns dikhenge! Yehi hai Data Visualization ki power.

### Definition (YAAD KARO — Exam)
> **"Data Visualization is the graphical representation of data and information using visual elements like charts, graphs, and maps to make data easier to understand, analyze, and communicate."**

### Phrase-by-Phrase Breakdown 🌟
- **"Graphical representation"** = Visual format mein dikhana (tables nahi)
- **"Using visual elements"** = Charts, graphs, maps, colors, shapes
- **"Easier to understand"** = Complex data ko simple banana
- **"Analyze"** = Patterns, trends, outliers dekhna
- **"Communicate"** = Insights ko dusron ko samjhana

### Why It Matters 🌟
1. **Speed:** Human brain visuals ko text se 60,000x faster process karta hai
2. **Pattern Recognition:** Raw tables hidden patterns nahi dikha sakte
3. **Decision Making:** Data-driven decisions ke liye essential
4. **Communication:** Technical insights ko non-technical logon ko samjhana
5. **Exploration:** Data ke saath interact karke insights discover karna

### Real-Life Examples 🌟
- **COVID-19 Dashboard:** Johns Hopkins ka world map — daily cases, deaths track karna
- **Stock Market Charts:** Candlestick charts — price movements visualize karna
- **Instagram Insights:** Engagement rates, follower growth graphs
- **Google Analytics:** Website traffic, user behavior dashboards
- **Swiggy/Zomato Maps:** Delivery tracking, restaurant locations

### Applications in Industry 🌟
| Industry | Use Case | Example |
|----------|----------|---------|
| Healthcare | Patient monitoring, disease tracking | COVID dashboards, ECG visualization |
| Finance | Stock analysis, risk management | Candlestick charts, heat maps |
| Marketing | Campaign performance, customer behavior | Social media analytics dashboards |
| E-commerce | Sales trends, user journey | Conversion funnels, recommendation visuals |
| Education | Student performance tracking | Grade distributions, attendance charts |

---

## 2. The Visualization Pipeline (6 Steps)

### Hook 🎯
Pizza order karte waqt kya hota hai? Order → Kitchen → Cooking → Plating → Serving. Har step ka ek role hai. Data Visualization mein bhi 6-step pipeline hai — raw data se final visual tak.

### Definition 🌟
> **"The Visualization Pipeline is a 6-step process that transforms raw data into a meaningful visual representation, from data acquisition to view rendering."**

### 6 Steps Explained 🌟

| Step | Name | What Happens | Example |
|------|------|--------------|---------|
| **1** | **Data Acquisition** | Data collect karo sources se | Download CSV, query database, API call |
| **2** | **Data Parsing** | Extract aur structure karo | JSON parse, CSV split into rows-columns |
| **3** | **Data Filtering** | Irrelevant data remove karo | Remove null values, outliers, duplicates |
| **4** | **Data Mining** | Statistical/ML methods apply karo | Calculate averages, clustering, regression |
| **5** | **Visual Mapping** | Data ko visual elements mein map karo | Temperature → color red-blue, city → position |
| **6** | **View Rendering** | Final visualization display karo | Chart/graph render karo screen pe |

### Key Point 🌟
**User Interaction** pipeline ke kisi bhi stage pe ho sakta hai — zoom, filter, drill-down, hover details. Interactive dashboards (Tableau, Power BI) ye sab allow karte hain.

### Real-Life Example 🌟
**Swiggy Order Tracking:**
1. **Acquisition:** Restaurant se order details API se
2. **Parsing:** JSON mein order ID, items, amount extract
3. **Filtering:** Cancelled orders remove
4. **Mining:** Estimated delivery time calculate karna
5. **Mapping:** Delivery boy location → map pe blue dot
6. **Rendering:** Real-time map show karna user ko

---

## 3. Labelling of Images

### Hook 🎯
Self-driving car ko kaise pata chalta hai ki ye "car" hai aur ye "person"? Images pe labels lagake ML model train karte hain! Image labelling = AI ka foundation.

### Definition 🌟
> **"Image Labelling is the process of assigning metadata tags or annotations to images, used in machine learning training and data visualization to teach algorithms to recognize patterns."**

### 5 Types of Image Labelling 🌟

| Type | Description | Use Case | Example |
|------|-------------|----------|---------|
| **1. Classification** | Puri image ko ek category dena | Image recognition | "Cat" ya "Dog" tag |
| **2. Object Detection** | Bounding boxes around objects | Counting, tracking | Car ke around box |
| **3. Semantic Segmentation** | Pixel-level classification | Medical imaging | Tumor region highlight |
| **4. Instance Segmentation** | Individual objects separate karna | Crowd analysis | Each person alag color |
| **5. Keypoint Annotation** | Landmark points mark karna | Face recognition | Eyes, nose, mouth points |

### Annotation Tools 🌟
- **LabelImg:** Simple bounding box tool
- **CVAT (Computer Vision Annotation Tool):** Professional, supports all types
- **VGG Image Annotator:** Free, web-based
- **Labelbox:** Enterprise-level, team collaboration

### Challenges 🌟
- **Subjectivity:** Different annotators different labels de sakte hain
- **Scale:** Thousands of images label karna time-consuming
- **Quality Control:** Consistency maintain karna
- **Cost:** Expert annotators expensive hote hain (medical images)

### Real-Life Examples 🌟
- **Self-Driving Cars:** Tesla — road signs, pedestrians, other cars detect karna
- **Medical Imaging:** X-ray, MRI mein tumors highlight karna
- **E-commerce:** Product images pe tags — "red", "dress", "summer collection"
- **Security:** CCTV footage mein suspicious activity detect karna

---

## 4. Types of Data in Visualization

### Hook 🎯
Ek restaurant ka data socho: (1) Customer ka naam = qualitative, (2) Order ka time = temporal, (3) Restaurant ka location = spatial, (4) Bill amount + items + rating = multivariate. Har data type ka different chart!

### Definition 🌟
> **"Data types determine which visual encoding method to use. There are 4 main types: Qualitative (categorical), Temporal (time-based), Spatial (geographic), and Multivariate (multiple variables)."**

### 4 Types Explained 🌟

#### 4.1 Qualitative (Categorical) Data 🌟
**Definition:** Non-numerical data that represents categories or qualities.

| Subtype | Description | Example | Chart Type |
|---------|-------------|---------|------------|
| **Nominal** | No order, just categories | Colors (red, blue, green), Cities | Bar chart, Pie chart |
| **Ordinal** | Has order/ranking | Ratings (⭐⭐⭐⭐), Grades (A, B, C) | Bar chart (ordered) |

**Real Examples:**
- Blood groups: A, B, AB, O (Nominal — no order)
- Movie ratings: Poor, Fair, Good, Excellent (Ordinal — has order)

#### 4.2 Temporal (Time-based) Data 🌟
**Definition:** Data collected over time, showing trends and patterns.

**Examples:**
- Daily stock prices
- Monthly sales figures
- Hourly website traffic
- Yearly population growth

**Chart Types:**
- **Line charts:** Trends over time (most common)
- **Area charts:** Cumulative values
- **Time series plots:** Multiple metrics over time

**Real Example:** Instagram follower growth — 1000 → 2000 → 5000 over 6 months (line chart)

#### 4.3 Spatial (Geographic) Data 🌟
**Definition:** Location-based data — latitude, longitude, addresses, regions.

**Examples:**
- COVID cases by state
- Restaurant locations in Jaipur
- Delivery zones in a city
- Weather patterns across India

**Chart Types:**
- **Choropleth maps:** Color-coded regions (states, districts)
- **Point maps:** Individual locations marked
- **Heat maps:** Density visualization
- **Proportional symbol maps:** Circle size = value

**Real Example:** Swiggy delivery map — show karta hai kaunse areas mein orders zyada hain

#### 4.4 Multivariate Data 🌟
**Definition:** Multiple variables visualized simultaneously.

**Examples:**
- Student performance: Marks + Attendance + Assignments + Participation
- Product sales: Price + Quantity + Category + Region + Season

**Chart Types:**
- **Scatter plots:** 2-3 variables (x, y, color/size)
- **Parallel coordinates:** Many variables in parallel axes
- **Bubble charts:** x, y, size, color = 4 variables
- **Heat maps:** Matrix of correlations

### Comparison Table 🌟

| Data Type | Nature | Key Question | Best Chart |
|-----------|--------|--------------|------------|
| Qualitative | Categories | "What kind?" | Bar, Pie |
| Temporal | Time-based | "When/How changed?" | Line, Area |
| Spatial | Location | "Where?" | Maps |
| Multivariate | Multiple vars | "Relationships?" | Scatter, Parallel |

---

## 5. Aesthetics and Visual Mapping

### Hook 🎯
Ek cricket match socho — scoreboard pe runs = bar height (length), team colors = category (color hue), player rank = position on list. Ye sab "aesthetics" hain — visual properties jo data represent karte hain.

### Definition 🌟
> **"Aesthetics in data visualization are the visual properties used to encode data — position, length, angle, area, color hue, color intensity, shape, and opacity."**

### Visual Variables Ranked by Accuracy 🌟

Humans different visual properties ko different accuracy se perceive karte hain:

| Rank | Visual Variable | Accuracy | Example |
|------|----------------|----------|---------|
| **1** | **Position** | Most accurate | Scatter plot points (x, y) |
| **2** | **Length** | Very high | Bar chart heights |
| **3** | **Angle** | High | Pie chart slices |
| **4** | **Area** | Medium | Bubble/circle sizes |
| **5** | **Color Hue** | Medium-low | Different colors for categories |
| **6** | **Color Intensity** | Low | Light-to-dark gradients |
| **7** | **Shape** | Low | Different point shapes |
| **8** | **Opacity** | Lowest | Transparency for density |

### Key Rule (Exam Important) 🌟
**"Use the most accurate visual encoding for the most important data."**

Example: Agar aapko exact values compare karni hain → Bar chart use karo (length). Agar sirf categories dikhani hain → Pie chart chalega (color hue).

### Real-Life Example 🌟
**Amazon Product Page:**
- **Price** → Large font, bold (Position — most important)
- **Rating** → Stars (Length — very visible)
- **Category** → Color label (Color hue)
- **Stock status** → Green/Red indicator (Color intensity)

---

## 6. Mapping Data to Aesthetics (3 Components)

### Hook 🎯
Temperature data ko color se dikhana hai — toh 3 cheezein chahiye: (1) Temperature values (data variable), (2) Color red-blue (visual attribute), (3) 10°C=blue, 40°C=red (scale — mapping rule).

### Definition 🌟
> **"Data-to-Aesthetic Mapping is the process of connecting data variables to visual attributes using scales as the mapping rule."**

### 3 Components of Mapping 🌟

| Component | What It Is | Example |
|-----------|-----------|---------|
| **1. Data Variables** | Aapke paas kaunsa data hai | Temperature, City, Date |
| **2. Visual Attributes** | Kaise dikhate ho | X-position, Color, Size |
| **3. Scales** | Mapping rule | 10-40°C → 0-500 pixels |

### Worked Example 🌟
**Task:** India ke cities ka temperature visualize karo.

| Component | Value |
|-----------|-------|
| Data Variable | Temperature (10°C to 40°C) |
| Visual Attribute | Color (Blue to Red) |
| Scale | Linear: 10°C = Blue, 25°C = White, 40°C = Red |

### Cognitive Limits 🌟 (Important for Exam)
Human brain ki limitations:
- **Color Hue:** Maximum 7 ± 2 categories (5-9 colors)
- **Shape:** Maximum 5-7 different shapes
- **Size:** Hard to compare more than 5 different sizes

**Rule:** Agar 10+ categories hain → Multiple charts banao ya legend use karo.

---

## 7. Coordinate Systems and Axes

### Hook 🎯
Google Maps pe location kaise dhundte ho? Latitude aur Longitude — ye ek coordinate system hai! Data visualization mein bhi coordinate systems use hote hain data ko positions pe map karne ke liye.

### Definition 🌟
> **"A Coordinate System is a framework that defines how data coordinates map to positions on a plot or visualization."**

### 3 Types of Coordinate Systems 🌟

| Type | Description | Best For | Example |
|------|-------------|----------|---------|
| **1. Cartesian** | Two perpendicular axes (x, y) | Most data | Bar, Line, Scatter |
| **2. Curvilinear (Polar)** | Radius + Angle (r, θ) | Cyclical data | Radar, Clock |
| **3. Nonlinear** | Log/Exponential scales | Wide ranges | Exponential growth |

### 7.1 Cartesian Coordinate System 🌟

**Definition:** "Two perpendicular axes — horizontal (x-axis) and vertical (y-axis) — intersecting at the origin (0,0)."

**Features:**
- Most common system — bar charts, scatter plots, line charts
- Easy to read and interpret
- Linear scales — equal spacing = equal value difference
- Best for: comparing values, showing trends

**Axis Components (5 Parts — Exam Important):**

| Component | Function | Example |
|-----------|----------|---------|
| **Axis Line** | Shows the measurement scale | X-axis line, Y-axis line |
| **Tick Marks** | Small marks showing specific values | Marks at 0, 10, 20, 30 |
| **Tick Labels** | Numbers/text at tick marks | "10", "20", "30" |
| **Axis Label** | Describes what axis measures | "Temperature (°C)" |
| **Grid Lines** | Help read values visually | Horizontal/vertical lines |

**Quadrants and Sign Patterns 🌟:**

| Quadrant | X | Y | Sign | Example Point |
|----------|---|---|------|---------------|
| I (Top-Right) | + | + | (+,+) | (3, 4) |
| II (Top-Left) | - | + | (-,+) | (-3, 4) |
| III (Bottom-Left) | - | - | (-,-) | (-3, -4) |
| IV (Bottom-Right) | + | - | (+,-) | (3, -4) |

**Limitations:**
- Cannot show cyclical patterns well
- Poor for data with exponential range

**Real Example:** Student marks — X-axis = Subject, Y-axis = Marks (0-100)

### 7.2 Nonlinear Axes 🌟

**Definition:** "Axes where equal visual distance does NOT represent equal data value."

**6 Types of Nonlinear Scales:**

| Type | Description | When to Use | Example |
|------|-------------|-------------|---------|
| **Logarithmic** | Each tick = 10× previous | Multiple orders of magnitude | pH scale, earthquake magnitude, sound dB |
| **Exponential** | Values grow exponentially | Rapid growth data | Population growth, virus spread |
| **Power** | y = x^n transformation | Skewed distributions | Income distribution, city sizes |
| **Square Root** | y = √x transformation | Moderate skew | Count data, Poisson data |
| **Reciprocal** | y = 1/x transformation | Inverse relationships | Speed vs time, resistance |

**Log Scale Example:**
- Linear: 1, 2, 3, 4, 5 (equal steps of 1)
- Log: 1, 10, 100, 1000, 10000 (each step × 10)

**When to Use:**
- Data spans multiple orders of magnitude (1 to 1,000,000)
- Comparing relative changes (percentages)
- Compressing wide ranges to fit on screen
- Skewed data with outliers

**Warning:** ⚠️ Log axes ko always clearly label karo — "Log Scale" likho — warna misinterpretation ho sakta hai!

### 7.3 Curved Axes (Polar Coordinates) 🌟

**Definition:** "Polar coordinates use radius (r) and angle (θ) instead of x and y."

**Best For:**
- Cyclical/periodic data
- Daily patterns (24-hour cycle)
- Seasonal patterns
- Directional data (wind direction)

**Examples:**
- **Radar charts:** Compare multiple metrics (skills assessment)
- **Rose diagrams:** Wind direction patterns
- **Clock visualizations:** Activity by hour of day

**Other Curved Coordinate Systems 🌟:**

| System | Coordinates | Use Case | Example |
|--------|-------------|----------|---------|
| **Polar** | (r, θ) radius + angle | 2D circular data | Radar charts, pie charts |
| **Cylindrical** | (r, θ, z) — polar + height | 3D cylindrical objects | Pipes, containers |
| **Spherical** | (r, θ, φ) — radius + 2 angles | 3D spherical data | Earth surface, globe |

**Real Example:** Restaurant traffic — 24 hours ka pattern (lunch peak, dinner peak, night low) — polar chart mein circle naturally 24 hours represent karta hai.

---

## 8. Color Scales (3 Types)

### Hook 🎯
Traffic light socho — Red = Stop, Yellow = Caution, Green = Go. Ye ek sequential color scale hai! Color scales data ki values ko colors se represent karte hain.

### Definition 🌟
> **"A Color Scale is a mapping between data values and colors, used to encode information visually. There are 3 main types: Categorical, Sequential, and Diverging."**

### 3 Types Explained 🌟

#### 8.1 Categorical Color Scale 🌟
**Use:** Distinct categories (no order)
**Design:** Different hues — red, blue, green, yellow, purple
**Example:** Different departments in a company — HR (blue), IT (green), Sales (red), Marketing (orange)

**Rule:** Colors should be visually distinct — colorblind-friendly colors use karo.

#### 8.2 Sequential Color Scale 🌟
**Use:** Ordered values (low to high)
**Design:** Light to dark of same hue
**Example:** Temperature — Light blue (cold) → Dark red (hot)

**Real Example:** COVID heat map — Light yellow (few cases) → Dark red (many cases)

#### 8.3 Diverging Color Scale 🌟
**Use:** Two extremes from a neutral midpoint
**Design:** Two hues meeting at neutral color
**Example:** Survey responses — Blue (Strongly Disagree) ← White (Neutral) → Red (Strongly Agree)

**Real Example:** Stock market — Green (profit) ← Gray (break-even) → Red (loss)

### Comparison Table 🌟

| Type | Data Type | Design | Example |
|------|-----------|--------|---------|
| Categorical | Nominal (no order) | Different hues | Departments, categories |
| Sequential | Ordinal (ordered) | Light → Dark | Temperature, income |
| Diverging | Two extremes + neutral | Two hues from center | Agree-Disagree, Profit-Loss |

### Color Accessibility 🌟 (Important)
- **Colorblind-friendly:** Red-Green avoid karo, Blue-Orange better hai
- **Contrast:** Text aur background mein enough contrast rakho
- **Cultural meaning:** Red = danger/loss (Western), Red = prosperity (India/China)
- **Print compatibility:** Grayscale mein bhi readable hona chahiye

### Color Perception: Hue, Saturation, Lightness 🌟

| Property | What It Is | Example |
|----------|-----------|---------|
| **Hue** | The actual color (red, blue, green) | Red hue, Blue hue |
| **Saturation** | Color intensity/vividness | Vivid red vs dull red |
| **Lightness** | How light/dark the color is | Light blue vs dark blue |

### Rainbow Maps Problem 🌟
**Issue:** Rainbow color scales (ROYGBIV) are popular but problematic:
- **Perception issue:** Human eye doesn't perceive all colors equally
- **Not perceptually uniform:** Yellow appears brighter than blue at same value
- **Colorblind issues:** Red-green transitions hard for colorblind users
- **Recommendation:** Use viridis, plasma, or cividis instead of rainbow

### Geographic Coordinate System 🌟
**Definition:** "Uses latitude and longitude to specify locations on Earth's surface."

| Component | Range | Example |
|-----------|-------|---------|
| **Latitude** | -90° to +90° (Equator = 0°) | Jaipur: 26.9° N |
| **Longitude** | -180° to +180° (Prime Meridian = 0°) | Jaipur: 75.8° E |

**Used in:** Maps, GPS, Geospatial visualizations, Location-based analytics

---

## 9. Directory of Visualizations

### Hook 🎯
Ek toolbox socho — hammer, screwdriver, wrench — har tool ka apna kaam. Visualization mein bhi har chart type ka apna kaam hai. Kaunsa chart kab use karna hai — ye jaana zaroori hai!

### Quick Reference Chart 🌟

| Data Type | Chart Type | Purpose |
|-----------|-----------|---------|
| **Categorical** | Bar Chart | Compare categories |
| **Categorical (parts)** | Pie Chart | Show proportions |
| **Time Series** | Line Chart | Show trends over time |
| **Distribution** | Histogram | Show frequency distribution |
| **Relationship (2 vars)** | Scatter Plot | Correlation between variables |
| **Geographic** | Choropleth Map | Regional patterns |
| **Multivariate** | Parallel Coordinates | Compare many variables |
| **Hierarchy** | Treemap | Nested proportions |

### Choosing the Right Chart 🌟 (Exam Important)

**Step 1:** Identify data type (Qualitative? Temporal? Spatial? Multivariate?)
**Step 2:** Identify your goal (Compare? Show trend? Show relationship? Show distribution?)
**Step 3:** Choose chart based on both

**Examples:**
- "Compare sales across 5 products" → Bar chart
- "Show website traffic over 12 months" → Line chart
- "Show relationship between price and demand" → Scatter plot
- "Show COVID cases by state" → Choropleth map

---

## 10. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Visualization Pipeline Steps
**"A-P-F-M-V-R"** → Acquisition, Parsing, Filtering, Mining, Visual Mapping, Rendering
→ *"All Pizza Fans Make Very Relish"* 🍕

### Trick 2: Image Labelling Types (5)
**"C-O-S-I-K"** → Classification, Object detection, Semantic, Instance, Keypoint
→ *"Cats Often Sleep In Kitchen"*

### Trick 3: Visual Variable Accuracy (8)
**"P-L-A-A-C-C-S-O"** → Position, Length, Angle, Area, Color Hue, Color Intensity, Shape, Opacity
→ *"People Love Apples At Apple Store, Computer Shop Open"* 🍎

### Trick 4: Data Types (4)
**"Q-T-S-M"** → Qualitative, Temporal, Spatial, Multivariate
→ *"Quick Tigers Swim Much"* 🐯

### Trick 5: Color Scales (3)
**"C-S-D"** → Categorical, Sequential, Diverging
→ *"Cat Sits Down"*

### Trick 6: Coordinate Systems (3)
**"C-C-N"** → Cartesian, Curvilinear, Nonlinear
→ *"Cars Can Navigate"*

---

## 11. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| "Visualization is just making pretty charts" | It's about understanding and communicating data insights |
| Using pie chart for 10 categories | Use bar chart — human can't compare 10 angles accurately |
| Log scale without labelling | Always label log axes clearly |
| More than 7 colors in one chart | Max 7±2 for color hue (cognitive limit) |
| Same color scale for all data | Categorical → distinct hues; Sequential → light-dark |
| Cartesian for cyclical data | Use Polar coordinates for daily/seasonal patterns |
| 3D charts for simple data | 2D is clearer — 3D adds distortion |

---

## 12. 5-Mark Answer Framework

**Q: "Explain Data Visualization and its importance."** (5 marks)

**Answer Structure:**

**Definition (1 mark):**
"Data Visualization is the graphical representation of data and information using visual elements like charts, graphs, and maps to make data easier to understand, analyze, and communicate."

**Types of Data (1 mark):**
- Qualitative (Nominal, Ordinal)
- Temporal (Time-series)
- Spatial (Geographic)
- Multivariate

**Visualization Pipeline (1 mark):**
6 steps: Acquisition → Parsing → Filtering → Mining → Visual Mapping → Rendering

**Importance (1.5 marks):**
1. Human brain processes visuals 60,000x faster than text
2. Reveals hidden patterns in data
3. Enables data-driven decision making
4. Facilitates communication of insights

**Real-World Applications (0.5 marks):**
- Healthcare: COVID dashboards
- Finance: Stock market charts
- Marketing: Social media analytics

---

## 13. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_DV_W1_Notes.pdf | Week 1 notes (26 pages) — Intro, Labelling, Data Types, Aesthetics, Scales |
| VIT_MSc_Ds_DV_W1_PPT.pdf | Week 1 PPT (12 pages) — Visual references |
| VIT_MSc_Ds_DV_W2_Notes.pdf | Week 2 notes (26 pages) — Coordinate Systems, Axes, Color Scales |
| VIT_MSc_Ds_DV_W2_PPT.pdf | Week 2 PPT (14 pages) — Visual examples |
| Claus O. Wilke Textbook | "Fundamentals of Data Visualization" — reference |
| Syllabus OLMCA618 | Module 1 scope |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 14. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 1) | Status | Section |
|---------------------------|--------|---------|
| Introduction | ✅ | Section 1 |
| Categories | ✅ | Section 4 (Data Types) |
| Labelling of images | ✅ | Section 3 |
| Mapping data onto aesthetics | ✅ | Section 6 |
| Types of Aesthetics | ✅ | Section 5 |
| Types of Data | ✅ | Section 4 |
| Scales Mapping Data to Aesthetics | ✅ | Section 6, 8 |
| Coordinate Systems and Axes | ✅ | Section 7 |
| Cartesian coordinates | ✅ | Section 7.1 |
| Nonlinear axes | ✅ | Section 7.2 |
| Coordinate systems with curved axes | ✅ | Section 7.3 |
| Color scales | ✅ | Section 8 |
| Directory of visualizations | ✅ | Section 9 |

### Coverage: 13/13 topics = 100% ✅

---

*Subject: Data Visualization (OLMCA618)*
*Unit 1 — Module 1: Introduction to Data Visualization*
*Last Updated: November 2025 | VIT MCA Semester 3*
