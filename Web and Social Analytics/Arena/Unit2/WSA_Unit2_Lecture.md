# Web and Social Media Analytics — Unit 2 Comprehensive Lecture Notes
## Module 2: Network Essentials
### Subject: OLMCA620 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Define** Social Network, SNA, and network components with academic accuracy
2. **Classify** networks into types (directed/undirected, weighted/unweighted, star/ring/random)
3. **Represent** networks using adjacency matrices
4. **Calculate** degree, in-degree, out-degree for any node
5. **Compute** centrality measures: Degree, Betweenness, Closeness, Eigenvector, Katz, PageRank
6. **Calculate** Degree Centralization and Network Density with formulas
7. **Explain** Clustering Coefficient (global & local), Transitivity, Reciprocity
8. **Differentiate** between bridges, articulation points, connected components
9. **Answer** exam questions using the 5-mark answer framework with examples

---

## 1. What is a Social Network?

### Hook 🎯
Aapke phone mein 200 WhatsApp contacts hain. Har contact ek "node" hai. Aap jo bhi kisi ko message karte ho, wo ek "edge" hai. Ye 200 log aur unke beech ke connections milkar ek pura SOCIAL NETWORK banate hain. Ab socho ye network million users pe ho — Facebook, Instagram — yehi Social Network Analysis ka topic hai!

### Definition (YAAD KARO — Exam)
> **"A Social Network is a social structure made up of a set of social actors (nodes) and patterns of connections (edges) between them."**

### Phrase-by-Phrase Explanation (Hinglish)
- **"Social structure"** → Logon ke beech organized relationships ka pattern
- **"Social actors (nodes)"** → Individual log, organizations, ya entities
- **"Patterns of connections (edges)"** → Rishte ya relationships jo actors ko connect karte hain
- **"Between them"** → Ye connections actors ke beech exist karte hain

### Core Concept
Social network = **Actors (Nodes) + Relationships (Edges)**
- Node = Person, Organization, Computer
- Edge = Friendship, Communication, Transaction, Link

### Real-Life Example 🇮🇳
**IRCTC ka network:**
- Nodes = Railway stations (Mumbai, Delhi, Jaipur)
- Edges = Train routes between stations
- Ye ek transportation social network hai!

---

## 2. Social Network Analysis (SNA)

### Hook 🎯
Police ne notice kiya ki ek criminal network mein "Raju" sabse zyada logon se connected hai. Raju ko arrest kiya toh pura network collapse ho gaya. Ye SNA ka power hai — network se sabse important node identify karna!

### Definition (YAAD KARO — Exam)
> **"Social Network Analysis (SNA) is the process of studying social structures through network and graph theory to analyze relationships between entities and identify patterns."**

### Phrase-by-Phrase Explanation (Hinglish)
- **"Studying social structures"** → Social relationships ko systematically analyze karna
- **"Network and graph theory"** → Mathematics ka wo branch jo nodes aur edges study karta hai
- **"Relationships between entities"** → Log, organizations ke beech ka connection
- **"Identify patterns"** → Repeated structures dhundna jaise clusters, hubs, bridges

### Interdisciplinary Nature 🌟

| Field | Contribution to SNA |
|-------|-------------------|
| **Sociology** | Social behavior, group dynamics |
| **Mathematics** | Graph theory, statistics |
| **Computer Science** | Algorithms, data structures |
| **Economics** | Market networks, trade flows |
| **Psychology** | Individual behavior in networks |

---

## 3. Network Components (Nodes, Edges, Attributes, Metadata)

### Hook 🎯
Jaise ek building ke components hain — foundation, walls, windows, blueprint — waise hi network ke components hain: Nodes (foundation), Edges (walls), Attributes (windows), Metadata (blueprint).

### Components Explained 🌟

| Component | Definition | Example | Exam Keyword |
|-----------|-----------|---------|-------------|
| **Nodes** | Social actors — people, organizations | Person in Facebook | Actors/Entities |
| **Edges** | Relationships between nodes | Friendship link | Connections/Links |
| **Attributes** | Properties of nodes or edges | Age, gender, timestamp | Properties/Features |
| **Metadata** | Data about the network itself | Network size, density | Descriptive info |

### Node Attributes
- Demographic details (age, gender, location)
- Geographic positions
- Functional roles
- Behavioural traits

### Edge Attributes
- Timestamps (kab connect hua)
- Interaction types (message, like, comment)
- Edge weights (relationship strength)

### Metadata
- Network size (total nodes)
- Density (how connected)
- Modularity (community structure)
- Centrality measures (important nodes)
- Topological properties

---

## 4. Classification of Networks

### Definition (YAAD KARO — Exam)
> **"Networks are classified based on edge direction (directed/undirected), edge weight (weighted/unweighted), and structural pattern (star/ring/random/scale-free)."**

### Types of Networks 🌟

| Type | Definition | Example | Diagram |
|------|-----------|---------|---------|
| **Undirected** | Edges have no direction | Facebook friendship | A — B |
| **Directed** | Edges have direction | Twitter follow | A → B |
| **Unweighted** | All edges equal weight | Simple friendship | A — B |
| **Weighted** | Edges have different weights | Call frequency | A —5— B |
| **Star** | One central node, all others connect to it | Manager-team | Center + spokes |
| **Ring/Lattice** | Each node connects to neighbors only | Circular chain | A-B-C-D-A |
| **Random** | Edges placed randomly | Random connections | Scattered |
| **Scale-Free** | Few hubs with many connections | Internet, WWW | Power law distribution |

### Directed vs Undirected — Key Difference
- **Undirected:** A-B = B-A (friendship mutual)
- **Directed:** A→B ≠ B→A (Twitter follow one-way)
- **Degree in undirected:** in-degree = out-degree
- **Degree in directed:** in-degree ≠ out-degree

---

## 5. Network Representation: Adjacency Matrix

### Hook 🎯
Socho aapko 100 logon ka network draw karna hai. Paper pe 100 circles aur unke beech lines — messy ho jayega! Isliye hum Adjacency Matrix use karte hain — ek simple grid jo pura network describe karti hai.

### Definition (YAAD KARO — Exam)
> **"An Adjacency Matrix is an N×N square matrix used to represent a network, where N is the number of nodes. Element A[i][j] = 1 if there is an edge between node i and node j, otherwise 0."**

### Example: 5-Node Network

```
Nodes: A, B, C, D, E
Edges: A-B, A-C, B-D, C-D, D-E

Adjacency Matrix:
    A  B  C  D  E
A [ 0  1  1  0  0 ]
B [ 1  0  0  1  0 ]
C [ 1  0  0  1  0 ]
D [ 0  1  1  0  1 ]
E [ 0  0  0  1  0 ]
```

### Key Properties 🌟
- **Undirected graph** → Matrix is symmetric (A[i][j] = A[j][i])
- **Directed graph** → Matrix may NOT be symmetric
- **No self-loops** → Diagonal elements are 0
- **Maximum possible edges** = N(N-1)/2 for undirected

---

## 6. Degree Distribution & Connectedness

### Hook 🎯
Instagram pe ek celebrity ke 10 million followers hain (high degree), aur aapke sirf 200 (low degree). Ye difference "degree distribution" batata hai — network mein power kiske paas hai!

### Degree — Definition 🌟
> **Degree of a node = Number of edges connected to that node.**

### Example Calculation
```
Graph: A-B, A-C, B-D, C-D, D-E

Node A: connected to B, C → Degree = 2
Node B: connected to A, D → Degree = 2
Node C: connected to A, D → Degree = 2
Node D: connected to B, C, E → Degree = 3 (highest!)
Node E: connected to D → Degree = 1 (lowest)
```

### Degree in Directed Graphs 🌟

| Term | Definition | Example |
|------|-----------|---------|
| **In-degree** | Number of incoming edges | Twitter pe kitne log follow karte hain |
| **Out-degree** | Number of outgoing edges | Twitter pe kitne log ko follow karte ho |

### Connectedness Concepts 🌟

| Term | Definition | Example |
|------|-----------|---------|
| **Connected Component** | Subgraph where all nodes are reachable from each other | Island of connected people |
| **Bridge** | Edge whose removal disconnects the network | Only road between two cities |
| **Articulation Point** | Node whose removal disconnects the network | Hub airport — remove it, cities disconnected |
| **Hamiltonian Path** | Path visiting every node exactly once | Travel salesman problem |
| **Eulerian Path** | Path using every edge exactly once | Seven Bridges of Königsberg |

---

## 7. Centrality Measures (Part 1)

### Hook 🎯
Network mein har node equal important nahi hota. Kuch nodes "VIP" hote hain — unko identify karne ke tools ko Centrality Measures kehte hain. Jaise college mein kuch students sabse zyada popular hote hain — wo "central" nodes hain!

### Definition (YAAD KARO — Exam)
> **"Centrality measures quantify the relative importance or influence of nodes within a network."**

### Three Main Types 🌟

| Measure | What It Counts | Identifies | Formula |
|---------|---------------|-----------|---------|
| **Degree Centrality** | Edges connected to node | Well-connected hubs | Cd(v) = degree of v |
| **Betweenness Centrality** | Shortest paths through node | Brokers/Gatekeepers | Cb(v) = σst(v)/σst |
| **Closeness Centrality** | Avg shortest path to all nodes | Efficient spreaders | Cc(v) = 1/Σd(v,j) |

### Worked Example 🌟
```
Graph: A-B, A-C, B-D, C-D, D-E

Degree Centrality:
  A=2, B=2, C=2, D=3, E=1
  → Node D is the hub (highest degree)

Closeness Centrality for A:
  d(A,A)=0, d(A,B)=1, d(A,C)=1, d(A,D)=2, d(A,E)=3
  Sum = 0+1+1+2+3 = 7
  Cc(A) = 1/7 ≈ 0.1429

Betweenness for A:
  A lies on paths: A-B, A-C, A→D(via C), A→E(via C-D)
  Cb(A) = 4 (lies on 4 shortest paths)
```

---

## 8. Centrality Measures (Part 2) — Advanced

### Eigenvector Centrality 🌟
> **"A node's centrality is proportional to the sum of centralities of its neighbors."**

- Important nodes are connected to other important nodes
- Formula: Ci(Vi) = (1/λ) × Σ Cj (where λ is a constant)
- Uses eigenvalue decomposition
- Google's PageRank is based on this concept

### Katz Centrality 🌟
> **"Considers both direct and indirect connections with a decay factor α for longer paths."**

- Addresses limitations of eigenvector centrality in directed graphs
- Formula: C = β(I - αA^T)^(-1) · 1
- α (alpha) = decay factor (longer paths less influential)
- β (beta) = bias term

### PageRank 🌟
> **"A node is important if it is linked to by other important nodes. Originally developed by Google to rank web pages."**

- Formula: PR(U) = Σ [PR(V) / Out(V)] for all V linking to U
- Damping factor d = 0.85 (controls distant neighbor influence)
- Iterative algorithm until convergence
- Used for: Web page ranking, social influence measurement

### Worked Example — All Measures for Node A:
```
Graph: A-B, A-C, B-D, C-D, D-E

Degree Centrality: Cd(A) = 2
Betweenness Centrality: Cb(A) = 4
Closeness Centrality: Cc(A) = 1/7 ≈ 0.1429
Eigenvector Centrality: Ce(A) ≈ 0.5774
Katz Centrality: Ck(A) ≈ 0.6885
PageRank: PR(A) ≈ 0.2211
```

---

## 9. Degree Centralization & Network Density

### Degree Centralization 🌟
> **"Degree Centralization measures how much a network is dominated by one or a few central nodes."**

Formula: **CDC = Σ(CDmax - CDi) / [(N-1)(N-2)]**

### Worked Example 🌟
```
Graph: A-B, A-C, B-D, C-D, D-E
N = 5 nodes
Degrees: A=2, B=2, C=2, D=3, E=1
Max degree (Dmax) = 3

Differences: (3-2)+(3-2)+(3-2)+(3-3)+(3-1) = 1+1+1+0+2 = 5
CDC = 5 / [(5-1)(5-2)] = 5 / (4×3) = 5/12 ≈ 0.4167

Interpretation: Network is moderately centralized (0.4167 out of 1.0)
```

### Extreme Cases:
| Network Type | Centralization Value | Meaning |
|-------------|---------------------|---------|
| **Star Network** | 1.0 | Fully centralized (one hub dominates) |
| **Ring/Lattice** | 0.0 | No dominance (all equal) |

### Network Density 🌟
> **"Density measures the ratio of actual edges to maximum possible edges in a network."**

Formula: **Density = E / [N(N-1)/2]** for undirected graphs

### Worked Example 🌟
```
Graph: A-B, A-C, B-D, C-D, D-E
N = 5 nodes, E = 5 edges
Max possible edges = 5(5-1)/2 = 10
Density = 5/10 = 0.5 (50% connected)
```

### Density Interpretation:
| Density Value | Meaning |
|--------------|---------|
| 1.0 (100%) | Complete graph — everyone connected |
| 0.5 (50%) | Half connections present |
| 0.0 (0%) | No connections at all |

---

## 10. Clustering Coefficient & Connectivity Patterns

### Hook 🎯
Aapke do dost hain — Rahul aur Priya. Agar Rahul aur Priya bhi ek doosre ko jaante hain, toh aap teeno milkar ek "triangle" banate ho. Ye triangle formation hi clustering hai!

### Ego-Centric Network 🌟
> **"An ego-centric network focuses on one node (ego) and its direct connections (alters), measuring the density of ties among the alters."**

Formula: **C = m / [n(n-1)/2]**
- m = number of edges between alters
- n = number of alters (ego's connections)

### Transitivity 🌟
> **"Transitivity is the tendency for friendships to form triangles — if A-B and B-C, then likely A-C."**

- "Friend of my friend is my friend"
- Measured using clustering coefficient
- High transitivity = tight-knit communities

### Clustering Coefficients 🌟

| Type | Definition | Formula |
|------|-----------|---------|
| **Global Clustering Coefficient** | Ratio of triangles to all paths of length 2 | (3 × Triangles) / (Paths of length 2) |
| **Local Clustering Coefficient** | Transitivity at individual node level | (Edges between neighbors) / (Max possible edges between neighbors) |

### Reciprocity 🌟
> **"Reciprocity is the mutual recognition of friendships — if A considers B a friend, B also considers A a friend."**

- Important in directed networks
- High reciprocity = strong mutual relationships
- Low reciprocity = one-sided relationships (celebrity fans)

### Real-Life Example 🇮🇳
**College Friend Group:**
- Aap, Rahul, Priya, Aman — 4 dost
- Agar sab ek doosre ko jaante hain → Complete cluster (CC = 1.0)
- Agar sirf kuch jaante hain → Partial cluster (CC < 1.0)

---

## 11. Six Degrees of Kevin Bacon

### Concept 🌟
> **"The Six Degrees of Kevin Bacon is a popular game suggesting that any actor can be connected to Kevin Bacon through no more than six movie roles."**

### Example:
- Tom Hanks worked with Kevin Bacon in Apollo 13 → **Bacon Number = 1**
- Actor A worked with Actor B → Actor B worked with Kevin Bacon → **Bacon Number = 2**

### Significance for SNA:
- Shows that real-world networks have **small-world property**
- Average path length between any two nodes is surprisingly small
- Related concept: **Six Degrees of Separation** (any two people connected by ≤6 steps)

---

## 12. Exam-Ready Recap (Keywords to Remember)

### Definitions to Memorize:
1. **Social Network** → Social actors (nodes) + connections (edges)
2. **SNA** → Studying social structures through graph theory
3. **Adjacency Matrix** → N×N matrix, A[i][j]=1 if edge exists
4. **Degree Centrality** → Count of edges connected to node
5. **Betweenness Centrality** → Shortest paths through node
6. **Closeness Centrality** → 1/sum of shortest path distances
7. **Eigenvector Centrality** → Proportional to neighbors' centrality
8. **Katz Centrality** → Direct + indirect connections with decay factor
9. **PageRank** → Important nodes linked by other important nodes
10. **Degree Centralization** → Σ(CDmax-CDi)/[(N-1)(N-2)]
11. **Network Density** → E/[N(N-1)/2]
12. **Clustering Coefficient** → Triangles / paths of length 2

### Key Formulas:
- **Density (undirected)** = E / [N(N-1)/2]
- **Density (directed)** = E / [N(N-1)]
- **Degree Centralization** = Σ(CDmax - CDi) / [(N-1)(N-2)]
- **Closeness Centrality** = 1 / Σd(i,j)
- **PageRank** = PR(U) = Σ [PR(V)/Out(V)]
- **Clustering Coefficient** = m / [n(n-1)/2]

### 5-Mark Answer Framework:
1. Definition (2 lines)
2. Types/Components (list)
3. Formula with worked example
4. Advantages/Limitations
5. Real-life example
6. Diagram (adjacency matrix / graph)

---

## 13. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Degree Centrality = Betweenness Centrality | Degree counts edges, Betweenness counts shortest paths |
| Density formula same for directed & undirected | Undirected: N(N-1)/2, Directed: N(N-1) |
| Adjacency matrix always symmetric | Only symmetric for undirected graphs |
| High degree = high betweenness | Not always — degree counts edges, betweenness counts paths through node |
| Eigenvector = Katz Centrality | Katz adds decay factor and bias term |
| PageRank only for web pages | PageRank measures importance in ANY network |

---

## 14. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: 6 Centrality Measures — "DB-CEKP"
**D**egree | **B**etweenness | **C**loseness | **E**igenvector | **K**atz | **P**ageRank
→ *"Do Bache Close Examination Karke Pass"*

### Trick 2: Centrality Purpose
- **Degree** → "Kitne friends?" (popularity)
- **Betweenness** → "Kitne logon ka bridge?" (broker)
- **Closeness** → "Kitni jaldi sab tak pahunch sakta?" (speed)
- **Eigenvector** → "Important logon ka dost?" (influence)

### Trick 3: Density Formula
Undirected: N(N-1)/2 → "N times N-1, divide by 2"
Directed: N(N-1) → "N times N-1, no division"
→ *"Directed mein double connections, isliye no /2"*

### Trick 4: Centralization Extremes
Star = 1.0 (sab kuch ek node ke paas)
Ring = 0.0 (sab barabar)
→ *"Star = 1, Ring = 0"*

---

## 15. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_WSMA_W2_Study_Material.pdf | Week 2 notes — all network concepts |
| W2 Calculation WSA W2.pdf | Week 2 PPT1 — centrality calculations, formulas |
| W2 VITOL W2.pdf | Week 2 PPT2 — agenda, Six Degrees of Kevin Bacon |
| Syllabus OLMCA620 | Module 2 scope (Network Essentials) |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 16. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 2) | Covered? | Section |
|---------------------------|----------|---------|
| Social Networks — meaning & components | ✅ | Section 1, 3 |
| Social Network Analysis — definition & interdisciplinary nature | ✅ | Section 2 |
| Network Theory Representation | ✅ | Section 5 |
| Classification of Networks | ✅ | Section 4 |
| Adjacency Matrix representation | ✅ | Section 5 |
| Weighted vs Unweighted Networks | ✅ | Section 4 |
| Network Roles | ✅ | Section 3 |
| Node & Edge Attributes, Metadata | ✅ | Section 3 |
| Degree Distribution | ✅ | Section 6 |
| Connectedness in Networks | ✅ | Section 6 |
| Centrality Measures (Degree, Betweenness, Closeness) | ✅ | Section 7 |
| Advanced Centrality (Eigenvector, Katz, PageRank) | ✅ | Section 8 |
| Degree Centralization | ✅ | Section 9 |
| Network Density | ✅ | Section 9 |
| Clustering Coefficient | ✅ | Section 10 |
| Six Degrees of Kevin Bacon | ✅ | Section 11 |
| Bridges & Articulation Points | ✅ | Section 6 |

### Coverage: 17/17 topics = 100% ✅

---

*Subject: Web and Social Media Analytics (OLMCA620)*
*Unit 2 — Module 2: Network Essentials*
*Last Updated: November 2025 | VIT MCA Semester 3*
