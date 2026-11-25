# Web and Social Media Analytics — Unit 7 Comprehensive Lecture Notes (IMPROVED)
## Module 7: Analyzing Social Platform Data (Week 11 + Week 12)
### Subject: OLMCA620 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Identify** 3 types of social media data with examples
2. **Differentiate** RESTful vs Stream APIs
3. **Describe** 5 data preprocessing steps
4. **Explain** 3 approaches to Sentiment Analysis
5. **Describe** Named Entity Recognition (NER) with entity types
6. **Analyze** Brand Activity, Popularity & Emotions
7. **Explain** YouTube Data Analytics (structured + unstructured)
8. **Describe** Web Scraping process and tools
9. **Explain** Topic Modelling using LDA
10. **Describe** Digital Campaigns and optimization strategies
11. **Answer** exam questions using 5-mark framework

---

## 1. Social Media Data Types

### Hook 🎯
Instagram pe jab aap koi photo post karte ho, toh 3 types ka data banta hai: (1) Likes count = structured, (2) Caption text = unstructured, (3) JSON metadata with tags = semi-structured. Ek post se teen tarah ka data!

### Definition (YAAD KARO — Exam)
> **"Social media data exists in three forms: Structured (tabular, organized), Unstructured (raw text/media), and Semi-structured (JSON, hashtags, metadata)."**

### Three Types Explained 🌟

| Type | Format | Query-able | Example | Tools |
|------|--------|-----------|---------|-------|
| **Structured** | Tabular, rows-columns | Yes — SQL | User profiles, likes count, follower count, demographics | SQL, Excel |
| **Unstructured** | Raw, no fixed format | No — needs NLP | Posts, comments, images, videos, audio | NLP, ML |
| **Semi-structured** | Some structure (tags/metadata) | Partially | JSON from APIs, hashtags, XML data | JSON parsers |

### Why This Matters 🌟
- **Structured data** → Easy to analyze, quick insights
- **Unstructured data** → 80% of social media data is unstructured — richest source of insights
- **Semi-structured** → Bridge between both — APIs return this format

---

## 2. APIs — RESTful & Stream APIs

### Hook 🎯
Twitter se data chahiye? Direct website se copy-paste karoge toh slow hoga aur limit bhi hai. API use karo — official, fast, legal! Do types hain:

### Definition 🌟
> **"APIs (Application Programming Interfaces) are official platform tools that allow programmatic access to social media data in a structured format."**

### RESTful APIs 🌟

| Feature | Description |
|---------|-------------|
| **Model** | Request-response — client sends request, server responds |
| **Use Case** | Historical data retrieval (past tweets, old posts) |
| **Rate Limit** | Limited requests per hour (Twitter: 300 requests/15 min) |
| **Data Format** | JSON response |
| **Examples** | Twitter REST API, Facebook Graph API, Instagram API |

### Stream APIs 🌟

| Feature | Description |
|---------|-------------|
| **Model** | Real-time continuous data flow |
| **Use Case** | Live monitoring, trending topics, real-time alerts |
| **Rate Limit** | Higher than REST — continuous connection |
| **Data Format** | Continuous JSON stream |
| **Examples** | Twitter Firehose, Reddit Stream API, YouTube Live API |

### Comparison Table 🌟

| Feature | RESTful API | Stream API |
|---------|------------|------------|
| **Data Type** | Historical | Real-time |
| **Connection** | Request-response | Persistent connection |
| **Rate Limit** | Lower | Higher |
| **Use Case** | Research, analysis | Monitoring, alerts |
| **Complexity** | Simpler | More complex |

### Advantages of APIs 🌟
- **Official access** — legal, no Terms of Service violation
- **Structured data** — JSON format, easy to process
- **Rate limits** — fair usage, platform stability
- **Authentication** — secure, tracked access

---

## 3. Data Preprocessing (5 Steps — EXAM MEIN AAYENGA)

### Hook 🎯
Raw social media data kachre jaisa hota hai — emojis, typos, repeated words, irrelevant content. Analysis se pehle clean karna zaroori hai! 5 steps hain:

### 5 Preprocessing Steps 🌟

| Step | What It Does | Example |
|------|-------------|---------|
| **1. Cleaning** | Remove noise, duplicates, irrelevant data | Remove "RT @user:", URLs, special characters |
| **2. Tokenization** | Split text into words/tokens | "I love India" → ["I", "love", "India"] |
| **3. Normalization** | Lowercase, remove special chars | "I Love INDIA!!!" → "i love india" |
| **4. Stop Word Removal** | Remove common words | "the", "is", "at", "which" remove |
| **5. Stemming/Lemmatization** | Reduce to root form | "running" → "run", "better" → "good" |

### Exploratory Data Analysis (EDA) 🌟
> **"EDA is understanding data through visualization and statistics before formal modelling."**

- **Word clouds** — most frequent words visually
- **Frequency distributions** — which words appear most
- **Sentiment distributions** — positive vs negative ratio
- **Identifying patterns, outliers, and trends**

---

## 4. Sentiment Analysis (3 Approaches + 3 Levels)

### Hook 🎯
Amazon pe product review padha: "The phone is amazing but battery life is terrible!" — overall positive ya negative? Sentiment Analysis ye decide karta hai!

### Definition (YAAD KARO — Exam)
> **"Sentiment Analysis is the process of determining the emotional tone behind text — classifying it as positive, negative, or neutral."**

### Three Approaches 🌟

| Approach | How It Works | Tools/Algorithms | Pros | Cons |
|----------|-------------|-----------------|------|------|
| **Lexicon-based** | Sentiment dictionaries — each word has a score | VADER, SentiWordNet, AFINN | Fast, no training needed | Can't handle sarcasm |
| **Machine Learning** | Train classifier on labeled data | Naive Bayes, SVM, Random Forest | Better accuracy | Needs labeled data |
| **Deep Learning** | Neural networks learn patterns | BERT, GPT, LSTM | Best accuracy, handles context | Computationally expensive |

### Three Levels 🌟

| Level | Scope | Example |
|-------|-------|---------|
| **Document level** | Overall sentiment of entire text | "Great phone!" → Positive |
| **Sentence level** | Sentiment per sentence | "Great phone. Bad battery." → +ve then -ve |
| **Aspect level** | Sentiment toward specific features | "Great camera, bad battery" → camera:+ve, battery:-ve |

---

## 5. Named Entity Recognition (NER)

### Definition (YAAD KARO — Exam)
> **"Named Entity Recognition (NER) is the process of identifying and classifying named entities in text into predefined categories like PERSON, ORGANIZATION, LOCATION, DATE, and PRODUCT."**

### 5 Entity Types 🌟

| Type | Description | Example from Text |
|------|-------------|-------------------|
| **PERSON** | Names of people | "Sundar Pichai" |
| **ORGANIZATION** | Companies, institutions | "Google", "IIT Delhi" |
| **LOCATION** | Cities, countries, landmarks | "Mumbai", "India" |
| **DATE/TIME** | Temporal expressions | "November 2025", "Monday" |
| **PRODUCT** | Brand names, products | "iPhone 15", "Samsung Galaxy" |

### Worked Example 🌟
**Text:** "Apple launched iPhone 15 in Cupertino on September 12, 2023, and Tim Cook praised its features."

| Entity | Type |
|--------|------|
| Apple | ORGANIZATION |
| iPhone 15 | PRODUCT |
| Cupertino | LOCATION |
| September 12, 2023 | DATE |
| Tim Cook | PERSON |

### Use in SMA 🌟
- **Trend tracking** — which brands/people trending
- **Competitor analysis** — track competitor mentions
- **Influencer identification** — find key PERSON entities

---

## 6. Brand Activity, Popularity & Emotions

### Brand Activity Metrics 🌟
| Metric | What It Measures |
|--------|-----------------|
| **Post Frequency** | How often brand posts |
| **Engagement Rate** | Likes+Comments / Followers × 100 |
| **Response Time** | How quickly brand replies |

### Popularity Metrics 🌟
| Metric | Description |
|--------|-------------|
| **Likes** | Positive reception count |
| **Shares** | Content spread count |
| **Followers** | Audience size |
| **Mentions** | How often brand is talked about |
| **Reach** | Unique people who saw content |
| **Share of Voice** | Brand mentions vs competitors |

### Emotion Analysis 🌟
| Emotion | Description | Example |
|---------|-------------|---------|
| **Joy** | Happiness, excitement | "Love this product! 😍" |
| **Anger** | Frustration, outrage | "Terrible service! 😡" |
| **Sadness** | Disappointment | "Expected more 😢" |
| **Surprise** | Unexpected reaction | "Didn't expect this! 😮" |

> **Emotion vs Sentiment:** Sentiment is positive/negative/neutral (3 categories). Emotions are more granular (joy, anger, sadness, surprise, fear, disgust).

---

## 7. Digital Campaigns & YouTube Analytics

### Digital Campaigns 🌟
> **"Digital campaigns are marketing efforts using digital channels (social media, email, search) to promote products or services."**

### YouTube Campaign Types 🌟

| Type | Purpose | Example |
|------|---------|---------|
| **Brand Awareness** | Increase visibility | Nike "Just Do It" campaign video |
| **Product Launch** | Introduce new product | Apple iPhone launch event stream |
| **Tutorial** | Educate users | "How to use our app" video |
| **Testimonial** | Build trust via customers | Customer success story video |

### Key Campaign Elements 🌟
1. **Title** — Catchy, SEO-optimized
2. **Thumbnail** — Eye-catching visual
3. **Description** — Detailed info with keywords
4. **CTA (Call to Action)** — "Subscribe", "Buy Now", "Learn More"
5. **Tags** — For discoverability

### YouTube Data: Structured vs Unstructured 🌟

| Structured | Unstructured |
|-----------|-------------|
| View count | Video content (visual+audio) |
| Likes/Dislikes | Comments text |
| Subscriber count | Titles, descriptions |
| Watch time | Tags (text) |
| CTR | Thumbnails (images) |
| Demographics | Audio transcript |

> **Integration = Complete Picture:** Structured tells WHAT happened (1M views), Unstructured tells WHY (comments show people loved the humor).

---

## 8. Web Scraping

### Definition 🌟
> **"Web Scraping is the process of programmatically extracting data from websites using automated tools."**

### 4 Key Tools 🌟

| Tool | Type | Best For |
|------|------|----------|
| **BeautifulSoup** | HTML parser | Simple pages, static content |
| **Scrapy** | Full framework | Large-scale scraping projects |
| **Selenium** | Browser automation | Dynamic pages, JavaScript rendering |
| **Puppeteer** | Headless Chrome | Modern web apps, SPAs |

### Scraping Process (4 Steps) 🌟
```
Step 1: Send HTTP request → webpage server ko request bhejo
Step 2: Parse HTML response → HTML ko parse karo
Step 3: Extract relevant data → specific elements extract karo
Step 4: Store in structured format → CSV, JSON, ya database mein save karo
```

### Ethical Considerations 🌟 (IMPORTANT)
- **Respect robots.txt** — website ka rules file
- **Follow rate limits** — server ko overload mat karo
- **Read Terms of Service** — legal restrictions check karo
- **Don't scrape personal data** without consent
- **Identify your scraper** — proper User-Agent header

---

## 9. Topic Modelling with LDA

### Definition (YAAD KARO — Exam)
> **"Latent Dirichlet Allocation (LDA) is a topic modelling algorithm that discovers hidden topics in a collection of documents. Each document is a mixture of topics, and each topic is a mixture of words."**

### How LDA Works 🌟
```
Input: Collection of documents (forum posts, tweets)
Output: K topics, each with top words

Example with K=3:
Topic 1: "cricket match ball wicket run" (Sports topic)
Topic 2: "price buy discount sale offer" (Shopping topic)
Topic 3: "code bug function deploy" (Tech topic)

Each document = mixture:
Doc 1: 70% Topic 1, 20% Topic 2, 10% Topic 3
```

### Use in Forum Analysis 🌟
- **Trend discovery** — kaunse topics trending hain
- **Content categorization** — posts ko topics mein divide karo
- **Community insights** — community kis baare mein discuss karti hai

---

## 10. Campaign Optimization & Challenges

### Optimization Strategies 🌟

| Strategy | Description | Example |
|----------|-------------|---------|
| **A/B Testing** | Compare different ad versions | Version A: red button vs Version B: green button |
| **Audience Refinement** | Target based on analytics data | Show ads only to 18-25 age group |
| **Content Optimization** | Based on engagement data | More video content if videos get more engagement |
| **Timing Optimization** | Post when audience active | Post at 8 PM if that's peak time |
| **Budget Allocation** | Based on ROI metrics | More budget to best-performing ads |

### Challenges in Campaign Analysis 🌟

| Challenge | Description |
|-----------|-------------|
| **Data Volume** | Massive amounts to process (millions of comments) |
| **Data Quality** | Fake engagement, bot activity, spam |
| **Privacy Regulations** | GDPR, consent requirements limit data access |
| **Attribution** | Linking conversions to specific touchpoints |
| **Real-time Analysis** | Need instant insights for live campaigns |

---

## 11. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Data Types
**"S-U-S"** → Structured, Unstructured, Semi-structured

### Trick 2: Preprocessing Steps
**"C-T-N-S-S"** → Clean, Tokenize, Normalize, Stop words, Stem
→ *"Cats Take Naps So Sweetly"*

### Trick 3: Sentiment Approaches
**"L-M-D"** → Lexicon, ML, Deep Learning
→ *"Love My Dog"*

### Trick 4: NER Entity Types
**"P-O-L-D-P"** → Person, Org, Location, Date, Product
→ *"People Often Love Delicious Pizza"*

### Trick 5: Scraping Tools
**"B-S-S-P"** → BeautifulSoup, Scrapy, Selenium, Puppeteer
→ *"Beautiful Spiders Scrape Pages"*

### Trick 6: Campaign Elements
**"T-T-D-C-T"** → Title, Thumbnail, Description, CTA, Tags
→ *"Two Tigers Don't Catch Tigers"*

---

## 12. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| REST API = real-time | REST = historical, Stream = real-time |
| Sentiment = Emotion | Sentiment is +/-/neutral, Emotion is granular (joy, anger) |
| Scraping = always legal | Must respect robots.txt and ToS |
| LDA = supervised learning | LDA is UNSUPERVISED — no labeled data needed |
| Structured data = only useful | Unstructured has 80% of social media data — most valuable |
| NER = only for English | NER works for multiple languages including Hindi |

---

## 13. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_WSMA_W11_Study_Material.pdf | Week 11 notes — Data types, APIs, Sentiment, NER |
| VIT_MSc_Ds_WSMA_W12_Study_Material.pdf | Week 12 notes — Campaigns, YouTube, Scraping, LDA |
| W11 Q&A-1.pdf | Week 11 PPT — Visual references |
| W11 Social Media Data Analytics-1.pdf | Week 11 PPT — Data analytics concepts |
| Week_12_Social_Media_Analytics (1).pdf | Week 12 PPT — Campaign optimization |
| Syllabus OLMCA620 | Module 7 scope |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 14. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 7) | Status | Section |
|---------------------------|--------|---------|
| Social Media Data types | ✅ | Section 1 |
| APIs (RESTful & Stream) | ✅ | Section 2 |
| Data Preprocessing | ✅ | Section 3 |
| EDA (Exploratory Data Analysis) | ✅ | Section 3 |
| Sentiment Analysis | ✅ | Section 4 |
| Named Entity Recognition | ✅ | Section 5 |
| Brand Activity & Emotions | ✅ | Section 6 |
| Digital Campaigns | ✅ | Section 7 |
| YouTube Data Analytics | ✅ | Section 7 |
| Web Scraping | ✅ | Section 8 |
| Topic Modelling (LDA) | ✅ | Section 9 |
| Campaign Optimization | ✅ | Section 10 |

### Coverage: 12/12 topics = 100% ✅

---

*Subject: Web and Social Media Analytics (OLMCA620)*
*Unit 7 — Module 7: Analyzing Social Platform Data*
*Last Updated: November 2025 | VIT MCA Semester 3*
