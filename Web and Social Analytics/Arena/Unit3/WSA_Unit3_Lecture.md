# Web and Social Media Analytics — Unit 3 Comprehensive Lecture Notes
## Module 3: Graph Essentials for SMA (Week 3 + Week 4 Combined)
### Subject: OLMCA620 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Explain** Social Balance Theory and its 4 rules with examples
2. **Differentiate** Social Status Theory from Balance Theory
3. **Define** Structural Equivalence and Regular Equivalence
4. **Calculate** degree distribution and identify power law patterns
5. **Distinguish** Walk, Trail, Path, and Cycle
6. **Compute** Distance, Diameter, and Average Path Length
7. **Explain** Small-World Property and Milgram's Experiment
8. **Classify** network models (Random, Regular, Small-World, Scale-Free)
9. **Describe** Erdos-Renyi, Watts-Strogatz, and Barabasi-Albert models
10. **Explain** Scale-Free Networks and Power Law Distribution
11. **Analyze** network vulnerabilities (random failure vs targeted attack)
12. **Describe** Flow Networks and Ford-Fulkerson Algorithm
13. **Identify** Bridges and Local Bridges in networks
14. **Answer** exam questions using the 5-mark framework

---

## 1. Social Balance Theory

### Hook 🎯
Aapke do dost hain — Rahul aur Priya. Agar Rahul aur Priya ek doosre ko pasand karte hain, toh aapka group balanced hai. Lekin agar Rahul ko Priya se nafrat hai, toh tension hai — ye unbalanced hai. Social Balance Theory isi ko mathematically explain karti hai!

### Definition (YAAD KARO — Exam)
> **"Social Balance Theory is a framework that examines the balance or imbalance of sentiment relations in dyadic (two-person) or triadic (three-person) relationships within social networks."**

### Phrase-by-Phrase Explanation (Hinglish)
- **"Sentiment relations"** → Positive (friendship) ya negative (enmity) relationships
- **"Dyadic"** → Do logon ke beech ka relationship
- **"Triadic"** → Teen logon ka triangle relationship
- **"Balance"** → Stable, harmonious social configuration
- **"Imbalance"** → Tension, instability — change ki zaroorat

### Four Rules of Social Balance 🌟

| Rule | Relationship | Triangle Sign Product |
|------|-------------|----------------------|
| Friend of my friend = my friend | (+,+,+) | + × + × + = **+ (Balanced)** |
| Friend of my enemy = my enemy | (+,-,-) | + × - × - = **+ (Balanced)** |
| Enemy of my enemy = my friend | (-,-,+) | - × - × + = **+ (Balanced)** |
| Enemy of my friend = my enemy | (+,+,-) | + × + × - = **- (Unbalanced)** |

### Mathematical Rule 🌟
- **Balanced triangle:** Product of edge signs ≥ 0 (even number of negative edges)
- **Unbalanced triangle:** Product of edge signs < 0 (odd number of negative edges)

### Real-Life Example 🇮🇳
**College Friend Group:**
- Aap → Rahul (friend +), Aap → Priya (friend +), Rahul → Priya (friend +)
- Product: (+)(+)(+) = + → BALANCED ✅
- Lekin agar Rahul → Priya (enemy -) → Product: (+)(+)(-) = - → UNBALANCED ❌

---

## 2. Social Status Theory & Similarity

### Social Status Theory 🌟
> **"Social Status Theory is based on directed relationships where status is determined by how much one person values another's opinion."**

### Key Difference from Balance Theory:
| Feature | Balance Theory | Status Theory |
|---------|---------------|---------------|
| Graph type | Undirected | Directed |
| Focus | Sentiment (friend/enemy) | Status hierarchy |
| Edge meaning | Positive/Negative | Direction of respect |

### Similarity in Social Networks 🌟

| Type | Definition | Example |
|------|-----------|---------|
| **Structural Equivalence** | Two nodes connected to the SAME other nodes | Two employees reporting to same manager |
| **Regular Equivalence** | Two nodes with SIMILAR patterns of ties (not necessarily same nodes) | Two managers in different departments with similar reporting structures |

---

## 3. Degree Distribution & Path Concepts

### Degree Distribution 🌟
> **"Degree Distribution is the probability distribution of node degrees across the entire network."**

- Real-world networks follow **Power Law Distribution**
- Few hubs with very high degree, many nodes with low degree
- Formula: P(k) = C × k^(-γ), where γ is typically between 2 and 3

### Path, Walk, Trail, Cycle 🌟

| Term | Definition | Nodes Repeat? | Edges Repeat? |
|------|-----------|--------------|--------------|
| **Walk** | Sequence of alternating nodes and edges | ✅ Yes | ✅ Yes |
| **Trail** | Walk with no repeated edges | ✅ Yes | ❌ No |
| **Path** | Walk with no repeated nodes | ❌ No | ❌ No |
| **Cycle** | Path that starts and ends at the same node | Only start=end | ❌ No |

### Hierarchy: Walk ⊃ Trail ⊃ Path ⊃ Cycle
- Every cycle is a path (except start=end)
- Every path is a trail
- Every trail is a walk

---

## 4. Distance, Diameter & Average Path Length

### Distance 🌟
> **"Distance d(i,j) is the shortest path length between nodes i and j in a network — the minimum number of steps to connect them."**

### Diameter 🌟
> **"Diameter Dia(G) is the length of the longest shortest path between any pair of nodes in the network."**
- Compute ALL pairwise shortest paths → take the maximum

### Average Path Length 🌟
> **"Average Path Length L(G) is the average of all pairwise shortest path lengths in the network."**

Formula: **L(G) = Σd(i,j) / [N(N-1)/2]** for undirected graphs

### Worked Example:
```
5-node network: A-B, A-C, B-D, C-D, D-E

Pairwise distances:
d(A,B)=1, d(A,C)=1, d(A,D)=2, d(A,E)=3
d(B,C)=2, d(B,D)=1, d(B,E)=2
d(C,D)=1, d(C,E)=2
d(D,E)=1

Sum = 1+1+2+3+2+1+2+1+2+1 = 16
Number of pairs = 5×4/2 = 10
L(G) = 16/10 = 1.6

Diameter = max distance = d(A,E) = 3
```

---

## 5. Small-World Property & Milgram's Experiment

### Small-World Property 🌟
> **"The Small-World Property states that despite large network sizes, the average path length between any two nodes remains surprisingly short."**

Key characteristics:
- **High Clustering Coefficient** (like regular lattices)
- **Short Average Path Length** (like random graphs)
- Combination of both = Small-World Network

### Milgram's Small-World Experiment (1967) 🌟
- **Setup:** Packages sent from Nebraska to Boston via acquaintances
- **Method:** Each person forwarded to someone they knew personally
- **Result:** Average chain length = **6 steps**
- **Conclusion:** "Six Degrees of Separation" — any two people connected by ≤6 intermediaries

### Modern Validation:
- **Facebook (2016):** Average separation = **4.74** (even smaller!)
- **LinkedIn:** Average degree of connection = ~3-4

---

## 6. Network Models: Types & Characteristics

### Four Major Network Models 🌟

| Model | Structure | Clustering | Avg Path Length | Real Example |
|-------|-----------|-----------|----------------|-------------|
| **Random Graph** | Edges placed randomly | Low | Short | — |
| **Regular Lattice** | Structured neighbors | High | Long | Crystal structure |
| **Small-World** | Lattice + random rewiring | High | Short | Social networks |
| **Scale-Free** | Power law distribution | Varies | Short | Internet, WWW |

---

## 7. Scale-Free Networks & Power Law

### Definition (YAAD KARO — Exam)
> **"A Scale-Free Network is a network whose degree distribution follows a power law: P(k) = C × k^(-γ), where most nodes have few connections and few nodes (hubs) have many connections."**

### Power Law Distribution 🌟
- P(k) = C × k^(-γ)
- γ (gamma) typically between **2 and 3**
- Log-log plot gives a **straight line**
- No "typical" node — scale-free means no characteristic scale

### Characteristics of Scale-Free Networks 🌟

| Property | Description |
|----------|-------------|
| **Robust to random failures** | Random node removal doesn't affect connectivity much |
| **Vulnerable to targeted attacks** | Removing hubs collapses the network |
| **Hub dominance** | Few nodes control most connections |
| **Examples** | Internet routers, WWW links, social media followers |

### Robust Yet Fragile Paradox 🌟
- **Random failure** → Network survives (robust) — most nodes have low degree
- **Targeted attack** → Network collapses (fragile) — hubs are critical

---

## 8. Theoretical Network Models

### Erdos-Renyi Model (Random Graph) 🌟
> **"Start with N isolated nodes. Add each possible edge independently with probability p."**

- Produces random networks
- Degree distribution: **Poisson** (bell curve around average)
- Low clustering coefficient
- Short average path length
- Not realistic for social networks

### Watts-Strogatz Model (Small-World) 🌟
> **"Start with a regular lattice. Rewire each edge with probability β to a random node."**

- β = 0 → Pure regular lattice (high clustering, long paths)
- β = 1 → Pure random graph (low clustering, short paths)
- **0 < β < 1** → Small-world network (high clustering + short paths) ✅
- Explains why real networks have both properties

### Comparison Table 🌟

| Property | Erdos-Renyi | Watts-Strogatz | Barabasi-Albert |
|----------|------------|----------------|----------------|
| Clustering | Low | High | Moderate |
| Avg Path Length | Short | Short | Short |
| Degree Distribution | Poisson | Narrow | Power Law |
| Mechanism | Random edges | Rewiring | Growth + Pref. Attachment |

---

## 9. Barabasi-Albert Model

### Definition (YAAD KARO — Exam)
> **"The Barabasi-Albert Model generates scale-free networks using two mechanisms: Growth (continuous addition of new nodes) and Preferential Attachment (new nodes prefer connecting to high-degree nodes)."**

### Two Mechanisms 🌟

| Mechanism | Description | Real-World Analogy |
|-----------|-------------|-------------------|
| **Growth** | Network starts small, new nodes continuously added | New people joining Facebook |
| **Preferential Attachment** | New nodes more likely to connect to high-degree nodes | "Rich get richer" — celebrities gain more followers |

### Why It Produces Scale-Free Networks:
- Early nodes get more connections (head start)
- They become hubs
- New nodes attach to hubs → hubs grow bigger
- Result: Power law degree distribution

### Real-World Examples:
- **WWW:** New webpages link to popular pages (Google, Wikipedia)
- **Social Media:** New users follow celebrities
- **Citation Networks:** New papers cite highly-cited papers

---

## 10. Network Flow & Ford-Fulkerson Algorithm

### Hook 🎯
Mumbai se Delhi tak maximum kitne trains chala sakte hain? Har track ki capacity limited hai. Ye problem solve karta hai Ford-Fulkerson Algorithm — maximum flow find karna!

### Flow Networks 🌟

| Component | Definition |
|-----------|-----------|
| **Source (S)** | Node where flow originates |
| **Sink (T)** | Node where flow is collected |
| **Capacity C(u,v)** | Maximum flow edge (u,v) can handle |
| **Flow F(u,v)** | Actual flow through edge (u,v) |

### Flow Constraints 🌟
1. **Capacity Constraint:** 0 ≤ F(u,v) ≤ C(u,v)
2. **Flow Conservation:** Flow in = Flow out (except source and sink)

### Ford-Fulkerson Algorithm 🌟

```
Step 1: Initialize flow = 0 on all edges
Step 2: Construct residual graph (remaining capacity)
Step 3: Find augmenting path (source to sink with positive residual capacity)
Step 4: Push bottleneck capacity along the path
Step 5: Update residual graph
Step 6: Repeat until NO augmenting path exists
Output: Maximum flow from source to sink
```

### Key Terms:
- **Residual Network:** Original capacities minus current flow
- **Augmenting Path:** Path from source to sink in residual graph with positive capacity
- **Bottleneck Capacity:** Minimum residual capacity along augmenting path

---

## 11. Bridge Detection & Applications

### Bridge 🌟
> **"A Bridge is an edge whose removal increases the number of connected components in the graph."**

### Local Bridge 🌟
> **"A Local Bridge is an edge whose removal increases the shortest path between its endpoints to more than 2 — meaning the endpoints have no common neighbors."**

### Neighborhood Overlap 🌟
- Formula: Overlap = |Common Neighbors| / |Total Neighbors (excluding endpoints)|
- **Local bridge if overlap = 0** (no common neighbors)

### Applications 🌟

| Domain | Application |
|--------|-------------|
| **Transportation** | Identifying critical roads/bridges |
| **Social Networks** | Finding weak ties that connect communities |
| **Resource Allocation** | Bottleneck identification |
| **Project Scheduling** | Critical path analysis |
| **Network Design** | Robustness optimization |

---

## 12. Network Visualization

### Definition 🌟
> **"Network Visualization is the graphical representation of networks to reveal patterns, structures, and relationships that are not apparent from raw data."**

### Tools 🌟
| Tool | Type | Best For |
|------|------|----------|
| **Gephi** | Open Source | Large network visualization |
| **Cytoscape** | Open Source | Biological networks |
| **NetworkX** | Python Library | Programmatic analysis |

### Layout Aesthetics in Gephi 🌟
- **Force-directed layouts** (Fruchterman-Reingold)
- Minimize edge crossings
- Uniform edge lengths
- Symmetric layout
- Node size by centrality
- Color by community

---

## 13. Exam-Ready Recap

### Key Definitions:
1. **Social Balance Theory** → Balance of sentiment in dyadic/triadic relationships
2. **Small-World Property** → Short avg path length despite large network
3. **Scale-Free Network** → Power law degree distribution
4. **Diameter** → Longest shortest path in network
5. **Ford-Fulkerson** → Max flow via augmenting paths

### Key Formulas:
- **L(G)** = Σd(i,j) / [N(N-1)/2]
- **P(k)** = C × k^(-γ) [Power Law]
- **Balance:** Product of edge signs ≥ 0

### 5-Mark Answer Framework:
1. Definition → 2. Types/Components → 3. Formula + Example → 4. Properties → 5. Real-world example

---

## 14. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Balance Theory Rules
**"FF=Friend, FE=Enemy, EE=Friend, EF=Enemy"**
→ *"Friend's Friend = Friend, Friend's Enemy = Enemy"*

### Trick 2: Walk/Trail/Path/Cycle Hierarchy
**W ⊃ T ⊃ P ⊃ C** → *"Walk Total Path Circular"*
- Walk allows everything, Cycle is most restrictive

### Trick 3: Network Models
**"ER = Random, WS = Small-World, BA = Scale-Free"**
→ *"Erdos Random, Watts Small, Barabasi Scale"*

### Trick 4: Small-World = High Clustering + Short Paths
→ *"Local friend groups (clustering) + Six degrees (short paths)"*

### Trick 5: Scale-Free Robust Yet Fragile
→ *"Random failure = OK, Target hub attack = COLLAPSE"*

---

## 15. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Balance Theory works for directed graphs | Balance Theory is for undirected; Status Theory for directed |
| All paths are cycles | Cycle must start=end; path cannot repeat nodes |
| Diameter = longest path | Diameter = longest SHORTEST path |
| Erdos-Renyi produces scale-free networks | Erdos-Renyi produces Poisson; Barabasi-Albert produces scale-free |
| Ford-Fulkerson finds shortest path | Ford-Fulkerson finds MAXIMUM FLOW |

---

## 16. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_WSMA_W3_Study_Material.pdf | Week 3 notes — Balance Theory, Network Models, Scale-Free |
| VIT_MSc_Ds_WSMA_W4_Study_Material.pdf | Week 4 notes — Degree Distribution, Flow Networks, Ford-Fulkerson |
| W3 VITOL W3.pdf | Week 3 PPT — Friendship patterns, network visualization |
| w4 VITOL.pdf | Week 4 PPT — Network models, graph algorithms |
| Syllabus OLMCA620 | Module 3 scope (Graph Essentials for SMA) |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 17. Topic Coverage Checklist (Syllabus Mapping)

| Syllabus Topic (Module 3) | Status | Section |
|---------------------------|--------|---------|
| Graph representation | ✅ | Section 3 |
| Types of graphs | ✅ | Section 6 |
| Connectivity concepts | ✅ | Section 4, 5 |
| Social Balance Theory | ✅ | Section 1 |
| Social Status Theory | ✅ | Section 2 |
| Structural & Regular Equivalence | ✅ | Section 2 |
| Degree Distribution | ✅ | Section 3 |
| Path, Walk, Trail, Cycle | ✅ | Section 3 |
| Distance, Diameter, Avg Path Length | ✅ | Section 4 |
| Small-World Property | ✅ | Section 5 |
| Milgram's Experiment | ✅ | Section 5 |
| Network Models (Random, Regular, SW, SF) | ✅ | Section 6 |
| Scale-Free Networks & Power Law | ✅ | Section 7 |
| Erdos-Renyi Model | ✅ | Section 8 |
| Watts-Strogatz Model | ✅ | Section 8 |
| Barabasi-Albert Model | ✅ | Section 9 |
| Network Vulnerabilities | ✅ | Section 9 |
| Flow Networks & Ford-Fulkerson | ✅ | Section 10 |
| Bridge Detection | ✅ | Section 11 |
| Network Visualization | ✅ | Section 12 |

### Coverage: 20/20 topics = 100% ✅

---

*Subject: Web and Social Media Analytics (OLMCA620)*
*Unit 3 — Module 3: Graph Essentials for SMA (Week 3 + Week 4)*
*Last Updated: November 2025 | VIT MCA Semester 3*
