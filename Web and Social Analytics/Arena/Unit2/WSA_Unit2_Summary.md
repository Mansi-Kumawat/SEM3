# WSA Unit 2 — Quick Revision Summary (One-Page)
## Module 2: Network Essentials | OLMCA620 | MCA Sem 3 | VIT

---

## 🔑 KEY DEFINITIONS (RAT LO)

| Term | Definition |
|------|-----------|
| **Social Network** | Social structure of actors (nodes) and connections (edges) between them |
| **SNA** | Studying social structures through network and graph theory |
| **Adjacency Matrix** | N×N matrix: A[i][j]=1 if edge exists between i and j |
| **Degree Centrality** | Count of edges connected to a node |
| **Betweenness Centrality** | Number of shortest paths passing through a node |
| **Closeness Centrality** | Inverse of average shortest path distance to all nodes |
| **PageRank** | Node importance based on links from other important nodes |
| **Network Density** | Ratio of actual edges to maximum possible edges |

---

## 📊 NETWORK TYPES

| Type | Description | Example |
|------|-------------|---------|
| Directed | Edges have direction (A→B) | Twitter follow |
| Undirected | No direction (A—B) | Facebook friendship |
| Weighted | Edges have weights | Call frequency |
| Star | One central hub | Manager-team |
| Ring | Each connects to neighbors | Circular chain |

---

## 🧮 KEY FORMULAS (RAT LO)

| Formula | Expression |
|---------|-----------|
| **Degree Centrality** | Cd(v) = number of edges connected to v |
| **Betweenness Centrality** | Cb(v) = σst(v) / σst |
| **Closeness Centrality** | Cc(v) = 1 / Σd(v,j) |
| **PageRank** | PR(U) = Σ [PR(V) / Out(V)] |
| **Network Density (undirected)** | E / [N(N-1)/2] |
| **Network Density (directed)** | E / [N(N-1)] |
| **Degree Centralization** | Σ(CDmax - CDi) / [(N-1)(N-2)] |
| **Clustering Coefficient** | C = m / [n(n-1)/2] |

---

## 🎯 6 CENTRALITY MEASURES — "DB-CEKP"

| # | Measure | What It Finds |
|---|---------|--------------|
| 1 | **D**egree | Well-connected hubs |
| 2 | **B**etweenness | Brokers/Gatekeepers |
| 3 | **C**loseness | Efficient information spreaders |
| 4 | **E**igenvector | Nodes connected to important nodes |
| 5 | **K**atz | Direct + indirect connections |
| 6 | **P**ageRank | Google's importance ranking |

---

## ⚖️ KEY COMPARISONS

### Star vs Ring Network:
| Property | Star | Ring |
|----------|------|------|
| Centralization | 1.0 (max) | 0.0 (min) |
| Vulnerable node | Center node | No single point |
| Path length | Short | Longer |

### Undirected vs Directed:
| Property | Undirected | Directed |
|----------|-----------|----------|
| Symmetric matrix | Yes | No |
| Max edges | N(N-1)/2 | N(N-1) |
| Degree | Single | In + Out |

---

## 🧠 MNEMONICS

| Concept | Mnemonic |
|---------|----------|
| 6 Centrality Measures | **"DB-CEKP"** → "Do Bache Close Examination Karke Pass" |
| Centrality Purpose | Degree=Popularity, Betweenness=Broker, Closeness=Speed, Eigenvector=Influence |
| Density | Undirected /2, Directed no /2 → *"Directed mein double"* |
| Centralization extremes | Star=1, Ring=0 |

---

## 📝 5-MARK ANSWER FRAMEWORK
1. **Definition** (2 lines) — English mein yaad karo
2. **Types/Components** (list with examples)
3. **Formula + Worked Example** (numbers calculate karo)
4. **Advantages & Limitations**
5. **Real-life Example** (Indian context)
6. **Diagram** (graph + adjacency matrix)

---

## ⚠️ COMMON MISTAKES
- Degree Centrality ≠ Betweenness Centrality
- Density formula: undirected mein /2, directed mein nahi
- Adjacency matrix: undirected mein symmetric, directed mein nahi
- PageRank ≠ sirf web pages ke liye — kisi bhi network mein kaam karta hai

---

*For detailed notes: See WSA_Unit2_Lecture.md*
*VIT MCA FAT Pattern: 70 Marks | 10×1 + 15×2 + 6×5*
