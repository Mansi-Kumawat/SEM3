# Web and Social Media Analytics — Unit 4 Comprehensive Lecture Notes
## Module 4: Community Analysis & Information Diffusion (Week 5 + Week 6)
### Subject: OLMCA620 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Define** Social Communities (Explicit vs Implicit)
2. **Differentiate** Overlapping vs Disjoint Communities
3. **Explain** Cliques, Maximal Clique, Maximum Clique
4. **Describe** Girvan-Newman Algorithm step by step
5. **Calculate** Modularity (Q) and interpret its values
6. **Compare** Label Propagation, Louvain, and Infomap methods
7. **Explain** Clique Percolation and Spectral Clustering
8. **Evaluate** communities using internal and external metrics
9. **Describe** Information Diffusion and Herd Behaviour
10. **Explain** Independent Cascade Model
11. **Describe** Diffusion of Innovation theory
12. **Explain** SIR Epidemic Model with formulas
13. **Answer** exam questions using the 5-mark framework

---

## 1. Social Communities

### Hook 🎯
College mein alag-alag groups hote hain — tech club wale alag, sports wale alag, cultural wale alag. Ye sab communities hain! Har group ke andar members zyada interact karte hain, aur doosre groups se kam. Social networks mein bhi yahi hota hai!

### Definition (YAAD KARO — Exam)
> **"A Community in a social network is a group of nodes with dense internal connections and sparse external connections."**

### Explicit vs Implicit Communities 🌟

| Feature | Explicit Communities | Implicit Communities |
|---------|---------------------|---------------------|
| **Definition** | Clearly defined groups | Discovered through analysis |
| **Awareness** | Members know they belong | Members may not know |
| **Formation** | Self-joined or assigned | Detected algorithmically |
| **Examples** | Facebook Groups, LinkedIn Groups, College class | People with same interests detected via interaction patterns |

---

## 2. Overlapping vs Disjoint Communities

### Definition 🌟
- **Disjoint Communities:** Each node belongs to **exactly ONE** community
- **Overlapping Communities:** Nodes can belong to **MULTIPLE** communities

### Key Point 🌟
Real-world networks are mostly **overlapping** — jaise aap college friends group mein bhi ho, family group mein bhi, aur tech community mein bhi!

---

## 3. Community Detection Overview

### Goal 🌟
Find groups where:
- **Internal connections** are DENSE (many edges within group)
- **External connections** are SPARSE (few edges between groups)

---

## 4. Cliques & Girvan-Newman Algorithm

### Cliques 🌟

| Term | Definition | Example |
|------|-----------|---------|
| **Clique** | Subset where EVERY pair is connected | 4 friends who all know each other |
| **Maximal Clique** | Not contained in any larger clique | Cannot add more nodes |
| **Maximum Clique** | Largest maximal clique in network | Biggest complete subgraph |

### Girvan-Newman Algorithm 🌟 (IMPORTANT FOR EXAM)

> **"An algorithm that detects communities by progressively removing edges with highest betweenness centrality."**

**Steps:**
```
Step 1: Calculate betweenness centrality for ALL edges
Step 2: Remove the edge with HIGHEST betweenness
Step 3: Recalculate betweenness for remaining edges
Step 4: Repeat until communities emerge
```

**Why it works:** Edges connecting different communities act as bridges — they have the highest betweenness because all inter-community paths pass through them.

### Zachary's Karate Club (Case Study) 🇮🇳
- 34 members, 78 connections
- Club split into 2 factions due to conflict
- Girvan-Newman correctly identified both communities
- Classic example in community detection literature

---

## 5. Modularity

### Definition (YAAD KARO — Exam)
> **"Modularity (Q) measures the quality of a community division by comparing actual edges within communities to expected edges in a random network."**

### Formula 🌟
**Q = (1/2m) × Σ[Aij - (ki × kj)/(2m)] × δ(ci, cj)**

Where:
- Aij = adjacency matrix element (1 if edge, 0 if not)
- ki, kj = degrees of nodes i and j
- m = total number of edges
- δ(ci, cj) = 1 if same community, 0 otherwise

### Interpretation 🌟

| Q Value | Meaning |
|---------|---------|
| Q > 0.3 | Significant community structure |
| Q = 0 | Random network (no communities) |
| Q < 0 | Worse than random |
| Q → 1 | Perfect community structure |

---

## 6. Community Detection Methods

### Label Propagation 🌟
```
Step 1: Give each node a unique label
Step 2: Each node adopts the most common label among neighbors
Step 3: Iterate until labels stabilize
```
- **Fast** but results can vary between runs
- Good for large networks

### Louvain Method 🌟
- **Modularity optimization** approach
- Two phases: **Local Moving** (move nodes to maximize Q) + **Aggregation** (merge communities)
- **Hierarchical** — finds communities within communities
- **Very efficient** for large networks

### Infomap 🌟
- Based on **information theory**
- Minimizes **description length** of random walk on network
- Uses **flow patterns** — how information actually moves
- Good for directed and weighted networks

---

## 7. Advanced Methods

### Clique Percolation Method (CPM) 🌟
- For **overlapping** community detection
- **k-clique:** Complete subgraph of k nodes
- Two k-cliques are **adjacent** if they share k-1 nodes
- **Community = union of adjacent k-cliques**
- Allows nodes in multiple communities

### Spectral Clustering 🌟
- Uses **eigenvalues** of graph Laplacian matrix
- **Laplacian L = D - A** (Degree matrix - Adjacency matrix)
- Find k smallest eigenvectors
- Apply **k-means** on eigenvector space
- Good for **non-convex** community shapes

---

## 8. Community Evaluation Metrics

### Internal Metrics (No Ground Truth) 🌟

| Metric | Formula/Concept | Good Value |
|--------|----------------|-----------|
| **Modularity Q** | Actual - Expected edges within communities | Higher = better (>0.3) |
| **Conductance** | External edges / Total edges of community | Lower = better |
| **Coverage** | Fraction of edges within communities | Higher = better |
| **Internal Density** | Actual edges / Possible edges within | Higher = better |

### External Metrics (Ground Truth Available) 🌟

| Metric | Description |
|--------|-------------|
| **NMI** | Normalized Mutual Information — measures agreement between detected and true communities |
| **ARI** | Adjusted Rand Index — corrected for chance |
| **F1-Score** | Harmonic mean of precision and recall |

---

## 9. Information Diffusion & Herd Behaviour

### Hook 🎯
Oreo ne Super Bowl blackout 2013 mein tweet kiya: "You can still dunk in the dark." Within minutes — millions of retweets! Ye hai Information Diffusion ki power — ek message tezi se pure network mein fail gaya!

### Information Diffusion 🌟
> **"The process by which information, ideas, or behaviors spread through a social network from person to person."**

### Methods of Analysis 🌟
- **Independent Cascade Model (ICM)** — each activation is independent
- **Linear Threshold Model** — node activates when enough neighbors are active

### Intervention in Diffusion 🌟
- **Seeding:** Select key nodes to start the cascade
- **Goal:** Maximize spread with minimum seeds
- **Application:** Viral marketing, public health campaigns

---

## 10. Herd Behaviour

### Definition (YAAD KARO — Exam)
> **"Herd Behaviour occurs when individuals follow the actions of others rather than using their own private information, even when they are rational."**

### Conditions for Herd Behaviour 🌟
1. **Sequential decision making** — log ek ke baad ek decide karte hain
2. **Limited private information** — apni knowledge limited hai
3. **Observable actions** — dusron ke actions dikh rahe hain
4. **Rational individuals can still herd** — even smart log follow karte hain!

### Key Case Studies 🌟

| Study | Finding |
|-------|---------|
| **Asch Conformity (1951)** | 75% conformed at least once to wrong group answer |
| **Anderson & Holt (1997)** | Lab experiment proved information cascades |
| **Online Auctions** | Bidders follow previous bids, driving prices up |
| **Restaurant Choice** | People choose crowded restaurants over empty ones |

### Implications 🌟

| Domain | Application |
|--------|-------------|
| **Marketing** | Viral campaigns, influencer seeding, product launches |
| **Public Health** | Vaccination campaigns, health behavior adoption |
| **Financial Markets** | Stock market bubbles, bank runs, crashes |
| **Social Movements** | Rapid mobilization, hashtag movements |

---

## 11. Information Cascades

### Definition (YAAD KARO — Exam)
> **"An Information Cascade occurs when individuals, despite having private information, choose to follow the actions of predecessors, creating a chain of similar decisions."**

### Independent Cascade Model (ICM) 🌟

| Feature | Description |
|---------|-------------|
| **Activation** | Each newly activated node gets ONE chance to activate each inactive neighbor |
| **Probability** | Activation probability p(u,v) for edge (u,v) |
| **Process** | Starts with seed set, spreads step by step |
| **Independence** | Each activation attempt is independent |

### Key Assumptions of ICM 🌟
1. Each node has one chance to activate each neighbor
2. Activation probability is independent
3. Process is progressive (once activated, stays active)
4. Cascade eventually stops

---

## 12. Diffusion of Innovation

### Definition 🌟
> **"Diffusion of Innovation is the process by which a new idea, product, or practice spreads through a social system over time."**

### Adopter Categories 🌟

| Category | % of Population | Characteristics |
|----------|----------------|----------------|
| **Innovators** | 2.5% | Risk-takers, first to try |
| **Early Adopters** | 13.5% | Opinion leaders, respected |
| **Early Majority** | 34% | Deliberate, follow leaders |
| **Late Majority** | 34% | Skeptical, adopt under pressure |
| **Laggards** | 16% | Traditional, last to adopt |

### S-Curve of Adoption 🌟
- Slow start (innovators) → Rapid growth (early/late majority) → Plateau (laggards)

---

## 13. Epidemics & SIR Model

### Hook 🎯
COVID-19 kaise faila? Ek infected person ne 2-3 logon ko infect kiya, unhone aur logon ko — ye SIR model hai! Social media mein bhi memes aur viral content ISI pattern mein failte hain!

### SIR Model 🌟 (IMPORTANT FOR EXAM)

> **"The SIR model divides a population into three compartments: Susceptible (S), Infected (I), and Recovered (R)."**

### Compartments 🌟

| Compartment | Meaning | Example (Social Media) |
|-------------|---------|----------------------|
| **S (Susceptible)** | Can be infected | Users who haven't seen the meme |
| **I (Infected)** | Currently infected/spreading | Users actively sharing the meme |
| **R (Recovered)** | Immune, can't be re-infected | Users who saw it and won't share again |

### SIR Equations 🌟

```
dS/dt = -β × S × I / N
dI/dt = β × S × I / N - γ × I
dR/dt = γ × I
```

Where:
- **β (beta)** = infection rate (how easily it spreads)
- **γ (gamma)** = recovery rate (how quickly people stop sharing)
- **N** = total population (S + I + R = N)

### Basic Reproduction Number 🌟
**R₀ = β / γ**
- R₀ > 1 → Epidemic spreads (viral!)
- R₀ < 1 → Epidemic dies out
- R₀ = 1 → Endemic (steady state)

### Application to Social Media 🇮🇳
- **S** = Users who haven't seen a viral tweet
- **I** = Users currently retweeting it
- **R** = Users who saw it but stopped sharing
- **β** = How easily the content spreads (shareability)
- **γ** = How quickly interest fades

---

## 14. Exam-Ready Recap

### Key Definitions:
1. **Community** → Dense internal, sparse external connections
2. **Clique** → Every pair connected subset
3. **Modularity Q** → Quality measure of community division
4. **Girvan-Newman** → Remove highest betweenness edges iteratively
5. **Herd Behaviour** → Following others despite own information
6. **Information Cascade** → Chain of decisions based on predecessors
7. **SIR Model** → Susceptible → Infected → Recovered

### Key Formulas:
- **Modularity:** Q = (1/2m) × Σ[Aij - ki×kj/2m] × δ(ci,cj)
- **SIR:** dI/dt = βSI/N - γI
- **R₀ = β/γ** (R₀ > 1 = viral)

### 5-Mark Answer Framework:
1. Definition → 2. Types/Components → 3. Algorithm/Process → 4. Example → 5. Application

---

## 15. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Community Detection Methods
**"GN-LP-L-IM-CP-SC"** → Girvan-Newman, Label Propagation, Louvain, Infomap, Clique Percolation, Spectral Clustering
→ *"Guru Nanak Loved Peace In My Country Society"*

### Trick 2: Herd Behaviour Conditions
**"SLO-R"** → Sequential, Limited info, Observable, Rational can herd
→ *"Sheep Like Others — Really!"*

### Trick 3: SIR Model
**"S→I→R"** → Susceptible → Infected → Recovered
→ *"Pehle Bimaro, Phir Theek Ho"*

### Trick 4: Adopter Categories
**"IE-ELL"** → Innovators, Early Adopters, Early Majority, Late Majority, Laggards
→ *"I Eat Every Last Ladoo"*

---

## 16. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Modularity Q > 1 possible | Q ranges from -0.5 to 1 |
| Girvan-Newman adds edges | It REMOVES edges (highest betweenness) |
| All communities are disjoint | Real networks mostly overlapping |
| Herd Behaviour = irrational | Even rational individuals can herd |
| R₀ < 1 means epidemic | R₀ > 1 means epidemic spreads |

---

## 17. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_WSMA_W5_Study_Material.pdf | Week 5 notes — Community Analysis, Detection methods |
| VIT_MSc_Ds_WSMA_W6_Study_Material.pdf | Week 6 notes — Information Diffusion, Herd Behaviour, SIR |
| W6 WSA.pdf | Week 6 PPT — Visual references |
| Syllabus OLMCA620 | Module 4 scope |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 18. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 4) | Status | Section |
|---------------------------|--------|---------|
| Community Detection | ✅ | Sections 1-8 |
| Herd Behaviour | ✅ | Section 10 |
| Information Cascades | ✅ | Section 11 |
| Epidemics (SIR Model) | ✅ | Section 13 |
| Explicit/Implicit Communities | ✅ | Section 1 |
| Overlapping/Disjoint | ✅ | Section 2 |
| Cliques & Girvan-Newman | ✅ | Section 4 |
| Modularity | ✅ | Section 5 |
| Label Propagation, Louvain, Infomap | ✅ | Section 6 |
| Clique Percolation, Spectral Clustering | ✅ | Section 7 |
| Community Evaluation Metrics | ✅ | Section 8 |
| Information Diffusion | ✅ | Section 9 |
| Diffusion of Innovation | ✅ | Section 12 |

### Coverage: 13/13 topics = 100% ✅

---

*Subject: Web and Social Media Analytics (OLMCA620)*
*Unit 4 — Module 4: Community Analysis & Information Diffusion*
*Last Updated: November 2025 | VIT MCA Semester 3*
