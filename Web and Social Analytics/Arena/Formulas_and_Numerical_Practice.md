# WSA — Complete Formula Sheet & Numerical Practice
## All Units | VIT MCA FAT Pattern | Step-by-Step Solved Examples

---

## 📐 MASTER FORMULA SHEET (RAT LO)

### Unit 2: Network Essentials
| Formula | Expression |
|---------|-----------|
| Degree Centrality | Cd(v) = number of edges connected to v |
| Closeness Centrality | Cc(v) = 1 / Σd(v,j) |
| Network Density (undirected) | D = E / [N(N-1)/2] |
| Network Density (directed) | D = E / [N(N-1)] |
| Degree Centralization | CDC = Σ(CDmax - CDi) / [(N-1)(N-2)] |
| Avg Path Length | L(G) = Σd(i,j) / [N(N-1)/2] |

### Unit 3: Graph Essentials
| Formula | Expression |
|---------|-----------|
| Power Law Distribution | P(k) = C × k^(-γ) |
| Average Path Length | L(G) = Σd(i,j) / number of pairs |
| Clustering Coefficient | C = m / [n(n-1)/2] |

### Unit 4: Community Analysis
| Formula | Expression |
|---------|-----------|
| Modularity Q | Q = (1/2m) × Σ[Aij - ki·kj/2m] × δ(ci,cj) |
| Homophily Index H | H = (Obs - Exp) / (Total - Exp) |

### Unit 5: Influence & Homophily
| Formula | Expression |
|---------|-----------|
| Assortativity r | r = (1/σ²q) × Σ[Aij - ki·kj/2m] × xi × xj |

### Unit 7: Analyzing Platforms
| Formula | Expression |
|---------|-----------|
| Engagement Rate | ER = (Likes + Comments) / Followers × 100 |
| Conversion Rate | CR = (Conversions / Visitors) × 100 |
| Bounce Rate | BR = (Single-page sessions / Total sessions) × 100 |

---

## 🔢 NUMERICAL PRACTICE — UNIT 2

### Problem 1: Degree Centrality
**Given:** Graph with 5 nodes (A, B, C, D, E) and edges: A-B, A-C, B-D, C-D, D-E

**Solution:**
```
Step 1: Count edges for each node
Node A: connected to B, C → Degree = 2
Node B: connected to A, D → Degree = 2
Node C: connected to A, D → Degree = 2
Node D: connected to B, C, E → Degree = 3 ← HIGHEST (hub!)
Node E: connected to D → Degree = 1 ← LOWEST

Step 2: Identify hub
→ Node D is the hub (highest degree = 3)
```

### Problem 2: Closeness Centrality
**Same graph. Find Cc(A):**
```
Step 1: Find shortest paths from A to all nodes
d(A,A) = 0
d(A,B) = 1 (A-B)
d(A,C) = 1 (A-C)
d(A,D) = 2 (A-C-D)
d(A,E) = 3 (A-C-D-E)

Step 2: Sum all distances
Σd = 0 + 1 + 1 + 2 + 3 = 7

Step 3: Apply formula
Cc(A) = 1 / Σd = 1/7 ≈ 0.1429
```

### Problem 3: Network Density
**Same graph. N=5, E=5:**
```
Step 1: Max possible edges (undirected)
Max = N(N-1)/2 = 5(4)/2 = 10

Step 2: Apply formula
D = E / Max = 5/10 = 0.5

→ Network is 50% connected
```

### Problem 4: Degree Centralization
**Same graph. Degrees: A=2, B=2, C=2, D=3, E=1:**
```
Step 1: Find maximum degree
CDmax = 3 (Node D)

Step 2: Calculate differences
Dmax - A = 3-2 = 1
Dmax - B = 3-2 = 1
Dmax - C = 3-2 = 1
Dmax - D = 3-3 = 0
Dmax - E = 3-1 = 2
Sum = 1+1+1+0+2 = 5

Step 3: Apply formula
CDC = Sum / [(N-1)(N-2)]
CDC = 5 / [(5-1)(5-2)] = 5 / (4×3) = 5/12 ≈ 0.4167

→ Network is moderately centralized (0.4167 out of 1.0)
```

### Problem 5: Star Network Centralization
**Star network with 6 nodes (1 center + 5 outer):**
```
Step 1: Degrees
Center node: degree = 5
Outer nodes: degree = 1 each

Step 2: Max degree = 5
Differences: (5-1)×5 + (5-5) = 20 + 0 = 20

Step 3: CDC = 20 / [(6-1)(6-2)] = 20/20 = 1.0

→ Star network: CDC = 1.0 (fully centralized) ✅
```

### Problem 6: Average Path Length
**Same 5-node graph:**
```
All pairwise distances:
d(A,B)=1, d(A,C)=1, d(A,D)=2, d(A,E)=3
d(B,C)=2, d(B,D)=1, d(B,E)=2
d(C,D)=1, d(C,E)=2
d(D,E)=1

Sum = 1+1+2+3+2+1+2+1+2+1 = 16
Pairs = 5(4)/2 = 10

L(G) = 16/10 = 1.6

→ Average path length = 1.6
```

---

## 🔢 NUMERICAL PRACTICE — UNIT 3

### Problem 7: Diameter
**Same 5-node graph:**
```
From Problem 6, all pairwise distances calculated.
Maximum distance = d(A,E) = 3

→ Diameter = 3
```

---

## 🔢 NUMERICAL PRACTICE — UNIT 4

### Problem 8: Modularity Q (Conceptual)
**Given:** Network with 2 communities. Q = 0.45
```
Q > 0.3 → Significant community structure exists ✅
Q = 0.45 → Good community division
```

### Problem 9: Homophily Index H
**Given:** 100 total edges, 70 same-type observed, 50 same-type expected
```
H = (Obs - Exp) / (Total - Exp)
H = (70 - 50) / (100 - 50)
H = 20 / 50 = 0.4

→ H = 0.4 (moderate homophily, positive value)
```

---

## 🔢 NUMERICAL PRACTICE — UNIT 5

### Problem 10: Assortativity Interpretation
**Given:** r = 0.65 for age-based network
```
r > 0 → Assortative mixing (similar age people connect)
r = 0.65 → Strong positive assortativity
→ People prefer connecting with similar-age individuals
```

---

## 🔢 NUMERICAL PRACTICE — UNIT 7

### Problem 11: Engagement Rate
**Given:** Instagram post with 5000 followers, 200 likes, 50 comments
```
ER = (Likes + Comments) / Followers × 100
ER = (200 + 50) / 5000 × 100
ER = 250 / 5000 × 100 = 5%

→ Engagement Rate = 5%
```

### Problem 12: Bounce Rate
**Given:** 1000 sessions, 350 single-page sessions
```
BR = (Single-page sessions / Total sessions) × 100
BR = 350 / 1000 × 100 = 35%

→ Bounce Rate = 35%
```

### Problem 13: Conversion Rate
**Given:** 2000 visitors, 60 purchases
```
CR = (Conversions / Visitors) × 100
CR = 60 / 2000 × 100 = 3%

→ Conversion Rate = 3%
```

---

## 📝 QUICK REFERENCE: Interpretation Guide

| Value | Meaning |
|-------|---------|
| **Density = 1.0** | Complete graph (all connected) |
| **Density = 0.0** | No connections |
| **CDC = 1.0** | Star network (fully centralized) |
| **CDC = 0.0** | Ring network (no dominance) |
| **Q > 0.3** | Significant community structure |
| **H = 1** | Complete homophily |
| **H = 0** | Random mixing |
| **H < 0** | Heterophily |
| **r = 1** | Perfect assortative |
| **r = 0** | Random mixing |
| **r = -1** | Perfect disassortative |
| **R₀ > 1** | Epidemic spreads (viral) |
| **R₀ < 1** | Epidemic dies out |

---

## 🎯 EXAM TIPS FOR NUMERICALS

1. **Always write the formula first** — even if you can't solve, formula = 1 mark
2. **Show step-by-step calculation** — partial marks for each step
3. **State the interpretation** — what does the number mean?
4. **Draw the graph** if given — helps visualize and avoid errors
5. **Check units** — percentages need ×100
6. **For Density:** undirected mein /2, directed mein nahi
7. **For Centralization:** denominator is always (N-1)(N-2)
8. **For Modularity:** Q > 0.3 is the threshold to remember

---

*All formulas from VIT MCA OLMCA620 Syllabus*
*Practice these 13 problems — numericals cover ho jayenge!*
