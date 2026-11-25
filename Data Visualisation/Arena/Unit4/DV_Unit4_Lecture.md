# Data Visualization — Unit 4 Comprehensive Lecture Notes
## Module 4: Time Series and Geospatial Data Visualization (Week 7 + Week 8)
### Subject: OLMCA618 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Visualize** multiple response variables using appropriate techniques
2. **Identify** and interpret three types of trends (upward, downward, stable)
3. **Apply** advanced smoothing techniques (SMA, WMA, Exponential)
4. **Differentiate** Vector vs Raster geospatial data
5. **Explain** three map projection types
6. **Build** Choropleth maps with proper classification methods
7. **Create** Cartograms (contiguous, non-contiguous, Dorling)
8. **Design** Point Maps (simple, dot density, event)
9. **Construct** Proportional Symbol Maps (continuous vs graduated)
10. **Implement** Cluster Maps (marker clustering, heat maps, hotspots)
11. **Answer** exam questions using 5-mark framework

---

## 1. Two or More Response Variables

### Hook 🎯
Business mein ek saath multiple metrics track karte hain — sales, profit, customer satisfaction. Sab ek saath visualize karoge toh patterns dikhte hain jo individually nahi dikhte!

### Definition 🌟
> **"Multiple Response Variables are several outputs measured at the same time — studied together to understand system behavior as a whole."**

### Four Visualization Methods 🌟

| Method | Description | Best For | Limitation |
|--------|-------------|----------|------------|
| **Multi-Line Chart** | One line per variable on shared time axis | Few variables (2-5), similar scales | Crowded with many lines |
| **Dual-Axis Plot** | Two units on left/right axes | Two variables with different units | Scale choices can mislead |
| **Faceted View** | Split into separate panels | Many variables | Harder to compare across panels |
| **Parallel Coordinates** | Each observation as line across parallel axes | Many variables, pattern detection | Complex to interpret |

### Multi-Line Chart 🌟
**Structure:**
- X-axis = Time
- Multiple Y-lines = Different variables
- Each line has own color/label

**When to Use:**
- 2-5 variables
- Similar scales
- Compare trends over time

**Example:** Monthly sales, profit, customer count — all on same chart

### Dual-Axis Plot 🌟
**Structure:**
- Left Y-axis = Variable 1 (e.g., Revenue in ₹)
- Right Y-axis = Variable 2 (e.g., Satisfaction score 1-10)
- X-axis = Time

**When to Use:**
- Two variables with very different units
- Show relationship between them

**⚠️ Danger:** Scale choices can mislead! Always label both axes clearly.

### Faceted View 🌟
**Structure:**
- Separate panel for each variable
- Same X-axis (time) across all panels
- Aligned vertically or in grid

**When to Use:**
- Many variables (5+)
- Different scales
- Need clear individual views

### Parallel Coordinates 🌟
**Structure:**
- Multiple vertical axes (one per variable)
- Each observation = line across all axes
- Patterns emerge from line crossings

**When to Use:**
- Many variables simultaneously
- Detect hidden relationships
- Cluster identification

### Applications 🌟
- **Healthcare:** Patient vitals (BP, heart rate, temperature)
- **Finance:** Market indicators (stocks, bonds, forex)
- **Climate:** Weather data (temperature, humidity, rainfall)
- **Industrial:** Process control (multiple sensors)

---

## 2. Visualizing Trends

### Hook 🎯
Stock market pe nazar hai — upar ja raha hai ya neeche? Long-term pattern kya hai? Trend analysis se pata chalta hai!

### Definition 🌟
> **"A trend is the general, long-term direction of data over time — growth, decline, or stability."**

### Three Trend Types 🌟

| Trend Type | Description | Slope | Example |
|------------|-------------|-------|---------|
| **Upward** | Values rise over time | Positive (+) | Population growth, online sales, stock prices |
| **Downward** | Values fall over time | Negative (-) | Declining demand, falling pollution, battery drain |
| **Stable** | Little variation | Near zero (≈0) | Constant machine output, consistent performance |

### Linear vs Nonlinear Trends 🌟

| Type | Description | Example |
|------|-------------|---------|
| **Linear** | Straight line growth/decline | Simple interest, constant speed |
| **Nonlinear** | Curved pattern | Exponential growth (virus spread), S-curve (product lifecycle) |

### Why Trend Visualization Matters 🌟
1. **Detects long-term patterns** hidden in raw numbers
2. **Spots changes in behavior** early
3. **Monitors progress** over time
4. **Supports forecasting** and business decisions

### Trend Lines 🌟
**What is it?** Line that best represents the data pattern

**Types:**
- **Linear trend line:** Straight line (y = mx + c)
- **Polynomial trend line:** Curved (quadratic, cubic)
- **Exponential trend line:** Rapid growth/decline

**How to add:** Most charting tools have "Add Trendline" option

### Moving Averages for Trends 🌟
**Purpose:** Smooth out short-term fluctuations, reveal underlying trend

**Method:** Average of last 'n' observations

**Example:** 3-period moving average = (x₁ + x₂ + x₃) / 3

---

## 3. Advanced Smoothing Techniques

### Hook 🎯
Daily sales data mein bahut up-down hai — noise hai. Underlying pattern kya hai? Smoothing se noise hatate hain, real trend reveal karte hain!

### Definition 🌟
> **"Smoothing is the process of removing noise from data to reveal underlying patterns and trends."**

### Three Smoothing Methods 🌟

#### 3.1 Simple Moving Average (SMA) 🌟
**Formula:**
```
SMA = (x₁ + x₂ + ... + xₙ) / n
```
Where n = window size

**Characteristics:**
- Equal weights to all observations in window
- Simple to calculate
- Reacts slowly to changes

**Example:** 5-day SMA for stock price = average of last 5 days

#### 3.2 Weighted Moving Average (WMA) 🌟
**Formula:**
```
WMA = (w₁x₁ + w₂x₂ + ... + wₙxₙ) / (w₁ + w₂ + ... + wₙ)
```
Where weights decrease for older observations (w₁ > w₂ > ... > wₙ)

**Characteristics:**
- Recent observations get more weight
- More responsive than SMA
- Better for trending data

**Example:** Weights = 5, 4, 3, 2, 1 for 5-period WMA

#### 3.3 Exponential Smoothing 🌟
**Formula:**
```
Sₜ = α × xₜ + (1 - α) × Sₜ₋₁
```
Where:
- Sₜ = smoothed value at time t
- xₜ = actual value at time t
- α = smoothing parameter (0 to 1)

**Characteristics:**
- Exponentially decreasing weights
- Most responsive method
- Widely used in forecasting

**Choosing α:**
| α Value | Behavior | Best For |
|---------|----------|----------|
| **α → 1** | More responsive, tracks changes fast | Rapidly changing data |
| **α → 0** | Smoother, less reactive to noise | Stable data with occasional spikes |
| **α = 0.2-0.3** | Balanced | Most applications |

### Window Size Trade-off 🌟
- **Shorter window** (n = 3-5): More responsive but noisy
- **Longer window** (n = 10-20): Smoother but slow to react

**Rule of thumb:** Start with n = √(number of observations)

---

## 4. Visualizing Geospatial Data

### Hook 🎯
Swiggy ke deliveries ka map dekho — kaunse areas mein zyada orders hain? Geographic patterns turant dikh jaate hain! Ye hai geospatial visualization ki power.

### Definition 🌟
> **"Geospatial Data is data with geographic component — latitude, longitude, addresses, regions, or any location-based information."**

### Two Data Types 🌟

| Type | Description | Examples | Characteristics |
|------|-------------|----------|-----------------|
| **Vector** | Points, lines, polygons | Cities (points), roads (lines), countries (polygons) | Precise locations, boundaries, discrete objects |
| **Raster** | Grid of cells/pixels | Satellite imagery, elevation maps, temperature grids | Continuous surfaces, regular grid, pixel-based |

### Five Main Map Types 🌟

| Map Type | Shows | Best For | Example |
|----------|-------|----------|---------|
| **Point Map** | Individual locations | Exact positions, clustering | Store locations, crime incidents |
| **Choropleth Map** | Regions shaded by value | Regional patterns, comparisons | Population density by state |
| **Bubble Map** | Circles sized by magnitude | Location + magnitude | City population |
| **Heat Map** | Density visualization | Concentration patterns | Traffic density |
| **Proportional Symbol Map** | Symbol size = value | Magnitude at locations | Sales by region |

### Why Geospatial Visualization? 🌟
1. **Reveals geographic patterns** — kaunse regions mein zyada activity hai
2. **Shows regional variations** — state-wise, district-wise comparison
3. **Supports location-based decisions** — where to open new store?

### Real Examples 🌟
- **COVID tracking:** Cases by district (choropleth)
- **Swiggy/Zomato:** Delivery zones (point + heat maps)
- **Real estate:** Property prices by locality (bubble map)
- **Elections:** Voting patterns by constituency (choropleth)

---

## 5. Map Projections and Layers

### Hook 🎯
Earth gol hai (3D), map flat hai (2D). 3D ko 2D mein convert karo toh kuch na kuch distort hoga! Projection choose karna = trade-off decide karna.

### Map Projection Definition 🌟
> **"Map Projection is the process of converting 3D Earth surface to 2D map — always involves some distortion (shape, area, distance, or direction)."**

### Three Projection Types 🌟

| Projection | Projects Onto | Preserves | Distorts | Best For | Example |
|------------|---------------|-----------|----------|----------|---------|
| **Cylindrical** | Cylinder | Shape | Area | Equatorial regions, navigation | Mercator |
| **Conic** | Cone | Area | Shape | Mid-latitudes | Albers (US maps) |
| **Azimuthal** | Flat plane | Direction from center | Area/shape away from center | Polar regions | Polar projection |

### Cylindrical Projection 🌟
**How it works:** Wrap cylinder around Earth, project surface onto it, unroll

**Properties:**
- Preserves shape (conformal)
- Distorts area (Greenland looks huge!)
- Straight lines = great circles (navigation)

**Example:** Mercator projection — used by Google Maps

**Best for:** Navigation, equatorial regions

### Conic Projection 🌟
**How it works:** Place cone on Earth, project surface onto it, unroll

**Properties:**
- Preserves area (equal-area)
- Distorts shape
- Good for mid-latitudes

**Example:** Albers projection — used for US maps

**Best for:** Countries spanning east-west (USA, India)

### Azimuthal Projection 🌟
**How it works:** Project from center point onto flat plane

**Properties:**
- Preserves direction from center
- Distorts area and shape away from center
- Circular map

**Example:** Polar projection — North Pole at center

**Best for:** Polar regions, radio transmission coverage

### Map Layers 🌟

| Layer | Content | Purpose |
|-------|---------|---------|
| **Base Layer** | Geography (countries, roads, rivers) | Context and reference |
| **Data Layer** | Your visualization (points, choropleth, symbols) | Main information |
| **Overlay Layer** | Additional info (labels, boundaries, annotations) | Extra context |

**How layers work:**
1. Base layer provides geographic context
2. Data layer shows your main visualization
3. Overlay layer adds supplementary information

**Example:**
- Base: India map with state boundaries
- Data: COVID cases choropleth (color-coded states)
- Overlay: State names, total count label

---

## 6. Choropleth Mapping

### Hook 🎯
Election results dekho — kaunsa state kis party ka hai? Colors se turant dikh jata hai! Ye hai choropleth map — regions shaded by value.

### Definition 🌟
> **"Choropleth Map shades regions by statistical value — darker shades mean higher values, so patterns across areas appear at a glance."**

### Components 🌟
1. **Boundaries:** States, districts, countries (administrative units)
2. **Numeric variable:** One value per region (e.g., population density)
3. **Color scale:** Sequential (light to dark) or diverging (two extremes)
4. **Classes:** Group values into categories (5-7 classes ideal)
5. **Legend:** Explains what each color means

### Three Classification Methods 🌟

| Method | How It Works | Advantage | Disadvantage | Best For |
|--------|-------------|-----------|--------------|----------|
| **Equal Interval** | Equal-sized ranges (0-20, 20-40, 40-60) | Simple, easy to understand | Sensitive to outliers | Uniformly distributed data |
| **Quantile** | Equal number of regions per class | Balanced distribution | May group similar values together | Skewed data |
| **Natural Breaks** | Groups similar values together (Jenks algorithm) | Reveals natural groupings | Complex to calculate | Data with natural clusters |

### Color Choice 🌟

| Data Type | Color Scale | Example |
|-----------|-------------|---------|
| **Low to High** | Sequential (light → dark) | Light blue → Dark blue |
| **Two extremes from midpoint** | Diverging (two colors from neutral) | Blue ← White → Red |
| **Categories** | Categorical (distinct hues) | Red, Blue, Green, Orange |

### ⚠️ CRITICAL: Normalization 🌟
**Problem:** Raw counts mostly reflect region size or population
- Large state = more cases (just because it's big!)
- Populous state = more votes (just because more people!)

**Solution:** Use rates or densities
- ❌ Total population → ✅ Population per square kilometer
- ❌ Total COVID cases → ✅ Cases per 100,000 people
- ❌ Total votes → ✅ Vote percentage

**Why normalize?** Makes regions fairly comparable regardless of size

### Applications 🌟
- Population density by state
- Election results by constituency
- Literacy rate by district
- Income levels by region
- Disease rates by area

### Advantages 🌟
1. Easy to read and interpret
2. Shows regional patterns clearly
3. Works well with administrative boundaries

### Limitations 🌟
1. Large regions look more important than small ones
2. Hides variation inside a region (ecological fallacy)
3. Boundary choice affects pattern (MAUP - Modifiable Areal Unit Problem)

---

## 7. Cartograms

### Hook 🎯
World map pe Russia bahut bada dikhta hai, par population mein China aur India aage! Normal map misleading hai. Cartogram mein statistic decides size — fair representation!

### Definition 🌟
> **"Cartogram is a map where regions are resized by statistical variable instead of physical area — distortion on purpose for fair representation."**

### Why Use Cartograms? 🌟
- **Normal map:** Large countries attract attention even when their values are small
- **Cartogram:** Statistic decides size — reveals true magnitude
- **Fair representation:** Population-based maps show populous countries larger

### How They Are Made 🌟
1. **Assign value** to every region (e.g., population)
2. **Resize regions** in proportion to value
3. **Adjust neighbors** so overall arrangement stays recognizable

### Three Types 🌟

| Type | Description | Advantage | Disadvantage |
|------|-------------|-----------|--------------|
| **Contiguous** | Regions connected, shapes distorted but recognizable | Maintains topology, can identify countries | Complex to create |
| **Non-contiguous** | Regions resized but gaps appear | Simpler to create | Less recognizable, gaps confusing |
| **Dorling** | Regions replaced with circles/symbols sized by value | Clean, abstract, easy to compare | Loses geographic shape |

### Contiguous Cartogram 🌟
**How it looks:** Countries still connected but shapes distorted
- Populous countries swell up (India, China)
- Large but sparse countries shrink (Russia, Canada)
- Overall arrangement recognizable

**Best for:** Maintaining geographic context

### Non-contiguous Cartogram 🌟
**How it looks:** Regions resized with gaps between them
- Simpler geometry
- Easier to create
- Harder to identify regions

**Best for:** Simplified visualization

### Dorling Cartogram 🌟
**How it looks:** Circles or symbols instead of regions
- Circle size = value
- Positioned approximately at region location
- Clean and abstract

**Best for:** Clear comparison, abstract view

### Examples 🌟
- **Population-based world map:** India and China huge, Russia small
- **Election-result map:** States sized by electoral votes, not area
- **GDP cartogram:** Economic power visualization

---

## 8. Point Maps

### Hook 🎯
City mein saare ATMs kahan hain? Har ATM ek point on map — point map! Simple but powerful.

### Definition 🌟
> **"Point Map plots individual locations as points on a map — shows exact locations and spatial patterns."**

### Three Types 🌟

| Type | Description | Best For | Example |
|------|-------------|----------|---------|
| **Simple Point Map** | Each point = one location | Show distribution, clustering | Store locations, hospitals |
| **Dot Density Map** | Each dot = specific number | Show concentration | Each dot = 1000 people |
| **Event Map** | Points for specific events in time/space | Track incidents | Earthquakes, accidents |

### Simple Point Map 🌟
**Structure:**
- Base map (geography)
- Points at exact locations
- Each point = one entity

**What it shows:**
- Distribution pattern
- Clustering (points grouped together)
- Dispersal (points spread out)

**Example:** All McDonald's locations in Jaipur

### Dot Density Map 🌟
**Structure:**
- Each dot represents specific number of occurrences
- Dots placed randomly within region (or at actual locations)

**What it shows:**
- Concentration visually
- Density patterns

**Example:** Each dot = 1000 people — densely populated areas have more dots

### Event Map 🌟
**Structure:**
- Points for specific events
- Often include time dimension
- May show severity/magnitude

**What it shows:**
- Incident locations
- Temporal patterns
- Severity distribution

**Example:** Earthquake locations with magnitude, accident spots with severity

### Spatial Patterns to Look For 🌟

| Pattern | Description | Meaning |
|---------|-------------|---------|
| **Clustering** | Points grouped together | Hotspot, attraction point |
| **Dispersal** | Points spread evenly | Uniform distribution |
| **Linear** | Points along line | Following road, river, coast |
| **Outliers** | Isolated points | Anomalies, special cases |

### Design Tips 🌟
1. **Use transparency** for overlapping points (see density)
2. **Vary point size** for magnitude (bigger = more)
3. **Color-code by category** (different colors for different types)
4. **Avoid overplotting** — use clustering if too many points

---

## 9. Proportional Symbol Maps

### Hook 🎯
Cities ki population dikhani hai — Mumbai biggest circle, Delhi slightly smaller, Jaipur medium. Symbol size se magnitude dikhna chahiye!

### Definition 🌟
> **"Proportional Symbol Map uses symbol size to show magnitude at a location — larger symbol means higher value."**

### Two Types 🌟

| Type | Description | Advantage | Disadvantage |
|------|-------------|-----------|--------------|
| **Continuous Symbols** | Symbol size proportional to actual value | Accurate representation | Hard to compare similar sizes |
| **Graduated Symbols** | Symbols in size classes/ranges | Easy to classify | Loses precision |

### Continuous Symbols 🌟
**How it works:**
- Symbol size (usually circle area) = actual value
- Smooth gradation from small to large
- No categories

**Critical design rule:**
- **Area** (not radius) should be proportional to value
- If value doubles → area doubles → radius increases by √2

**Example:** Circle area = city population

**Advantage:** Most accurate representation

**Challenge:** Human eye not great at comparing areas

### Graduated Symbols 🌟
**How it works:**
- Symbols grouped into size classes
- Discrete categories (small, medium, large)
- Each class has fixed symbol size

**Example:**
- Small circle: Population 0-100,000
- Medium circle: 100,001-500,000
- Large circle: 500,001+

**Advantage:** Easy to classify and compare

**Challenge:** Loses precision within classes

### Symbol Shape 🌟
| Shape | Use Case |
|-------|----------|
| **Circles** | Most common, neutral, widely understood |
| **Squares** | Alternative, easier to compare areas |
| **Other shapes** | Specific meanings (stars for capitals, etc.) |

### Design Considerations 🌟

1. **Area proportional to value:**
   - ❌ Wrong: Radius ∝ value (area grows too fast)
   - ✅ Correct: Area ∝ value (radius ∝ √value)

2. **Legend with reference symbols:**
   - Show 3-4 example symbols with values
   - Helps viewers estimate sizes

3. **Avoid overlapping symbols:**
   - Use transparency
   - Offset slightly if needed
   - Consider 3D effect (flattened)

4. **Size range:**
   - Smallest symbol should be visible
   - Largest shouldn't dominate
   - Max/min ratio ≤ 10:1 recommended

### Applications 🌟
- Population by city size
- Sales volume by region
- Earthquake magnitude at epicenter
- Market size by location

---

## 10. Cluster Maps

### Hook 🎯
Google Maps pe 1000 restaurants dikhane hain — sab points dikhayenge toh clutter ho jayega! Clustering se groups banao, count dikhao, zoom pe expand karo!

### Definition 🌟
> **"Cluster Map groups dense points to handle large datasets without clutter — marker clustering, heat maps, and density-based hotspots."**

### Three Approaches 🌟

| Approach | Description | Best For | Example |
|----------|-------------|----------|---------|
| **Marker Clustering** | Group nearby points into clusters, show count | Interactive maps, many points | Google Maps restaurant search |
| **Heat Maps** | Color intensity shows point density | Continuous density visualization | Traffic density, population |
| **Density-based Hotspots** | Statistical clustering (DBSCAN algorithm) | Identify significant concentrations | Crime hotspots, disease outbreaks |

### Marker Clustering 🌟
**How it works:**
1. Group nearby points into clusters based on distance
2. Show cluster marker with count (e.g., "15 restaurants")
3. Zoom in → clusters split into smaller clusters or individual points
4. Zoom out → clusters merge

**Advantages:**
- Handles thousands of points
- Clean interface
- Interactive exploration

**Example:** Google Maps — search "restaurants near me"

### Heat Maps 🌟
**How it works:**
1. Calculate point density across map
2. Color intensity represents density
3. Red = high density, Blue/Green = low density
4. Continuous surface (no discrete clusters)

**Advantages:**
- Shows continuous density
- Reveals patterns clearly
- Good for large datasets

**Example:** Traffic congestion map, population density

### Density-based Hotspots (DBSCAN) 🌟
**How it works:**
1. Statistical algorithm identifies dense regions
2. Distinguishes noise from actual clusters
3. Finds clusters of arbitrary shape (not just circular)

**Parameters:**
- **Epsilon (ε):** Maximum distance between points in cluster
- **MinPts:** Minimum points to form cluster

**Advantages:**
- Identifies significant concentrations
- Handles irregular shapes
- Separates noise

**Example:** Crime hotspot analysis, disease outbreak detection

### Why Cluster Maps? 🌟
1. **Handles thousands of points** without clutter
2. **Reveals concentration patterns** — kahan zyada activity hai
3. **Interactive exploration** — zoom in/out for different detail levels

### Applications 🌟
- **Real estate:** Property density by area
- **Retail:** Customer concentration analysis
- **Transportation:** Traffic hotspots identification
- **Emergency services:** Incident clustering for resource allocation

### Design Tips 🌟
1. **Choose right clustering radius:**
   - Too small → no clustering, still cluttered
   - Too large → everything in one cluster
   - Balance needed

2. **Use clear color scale:**
   - Heat map: intuitive color progression
   - Clusters: distinct colors for different densities

3. **Provide legend:**
   - Explain what colors/numbers mean
   - Show reference values

---

## 11. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Map Types (5)
**"P-C-B-H-P"** → Point, Choropleth, Bubble, Heat, Proportional
→ *"Please Call Big Harry Potter"*

### Trick 2: Projection Types (3)
**"C-C-A"** → Cylindrical, Conic, Azimuthal
→ *"Countries Can Always (be mapped)"*

### Trick 3: Choropleth Classification (3)
**"E-Q-N"** → Equal interval, Quantile, Natural breaks
→ *"Every Question Needs (classification)"*

### Trick 4: Cartogram Types (3)
**"C-N-D"** → Contiguous, Non-contiguous, Dorling
→ *"Countries Need (distortion)"*

### Trick 5: Point Map Types (3)
**"S-D-E"** → Simple, Dot density, Event
→ *"Some Data Exists (as points)"*

### Trick 6: Smoothing Methods (3)
**"S-W-E"** → Simple MA, Weighted MA, Exponential
→ *"Smooth With Ease"*

---

## 12. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Using raw counts in choropleth | Always normalize (use rates/densities) |
| Wrong projection for region | Cylindrical for equatorial, Conic for mid-latitudes |
| Too many classes in choropleth | 5-7 classes optimal |
| Radius proportional (not area) in symbol maps | Area should be proportional to value |
| Overplotting points | Use clustering or transparency |
| No legend | Always include legend with reference symbols |
| Ignoring MAUP (boundary effect) | Test different boundary choices |
| Dual-axis without clear labels | Label both axes explicitly |
| Too small/large smoothing window | Balance responsiveness vs smoothness |
| Non-contiguous cartogram without gaps explanation | Explain gaps or use contiguous |

---

## 13. 5-Mark Answer Framework

**Q: "Explain Choropleth Mapping with classification methods and design considerations."** (5 marks)

**Answer Structure:**

**Definition (1 mark):**
"Choropleth Map shades regions by statistical value — darker shades mean higher values, patterns at a glance."

**Components (1 mark):**
1. Boundaries (states/districts)
2. Numeric variable per region
3. Color scale
4. Classes (5-7 ideal)
5. Legend

**Classification Methods (1.5 marks):**
| Method | How | Best For |
|--------|-----|----------|
| Equal Interval | Equal ranges | Uniform data |
| Quantile | Equal count per class | Skewed data |
| Natural Breaks | Similar values together | Natural clusters |

**Design Considerations (1.5 marks):**
- **Normalize:** Use rates, not raw totals
- **Color choice:** Sequential for low→high, diverging for midpoint
- **Avoid:** Large regions dominating, ecological fallacy

---

## 14. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_DV_W7_Notes.pdf | Week 7 notes (30 pages) — Time Series, Trends, Smoothing, Geospatial intro |
| VIT_MSc_Ds_DV_W7_PPT.pdf | Week 7 PPT (14 pages) — Visual references |
| VIT_MSc_Ds_DV_W8_Notes.pdf | Week 8 notes (30 pages) — Choropleth, Cartograms, Point/Proportional/Cluster maps |
| VIT_MSc_Ds_DV_W8_PPT.pdf | Week 8 PPT (14 pages) — Visual examples |
| Claus O. Wilke Textbook | "Fundamentals of Data Visualization" — reference |
| Syllabus OLMCA618 | Module 4 scope |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 15. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 4) | Status | Section |
|---------------------------|--------|---------|
| Two or more response variables | ✅ | Section 1 |
| Visualizing trends | ✅ | Section 2 |
| Smoothing (advanced) | ✅ | Section 3 |
| Visualizing geospatial data | ✅ | Section 4 |
| Projections | ✅ | Section 5 |
| Layers | ✅ | Section 5 |
| Choropleth mapping | ✅ | Section 6 |
| Cartograms | ✅ | Section 7 |
| Point map | ✅ | Section 8 |
| Proportional symbol map | ✅ | Section 9 |
| Cluster map | ✅ | Section 10 |

### Coverage: 11/11 topics = 100% ✅

---

*Subject: Data Visualization (OLMCA618)*
*Unit 4 — Module 4: Time Series and Geospatial Data Visualization*
*Last Updated: November 2025 | VIT MCA Semester 3*
