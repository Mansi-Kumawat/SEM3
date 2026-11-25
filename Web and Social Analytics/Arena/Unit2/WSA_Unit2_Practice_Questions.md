# WSA Unit 2 — Practice Questions (VIT MCA FAT Pattern)
## Module 2: Network Essentials
## Exam Pattern: 70 Marks | 2h 30min | Section 1 (10×1) + Section 2 (15×2) + Section 3 (6×5)

---

## Section 1: MCQs — Answer ALL (10 × 1 = 10 Marks)

**Q1.** In a social network, nodes represent:
- (A) Connections between people
- (B) Social actors such as people or organizations ✅
- (C) The total number of edges
- (D) The density of the network

**Q2.** An adjacency matrix for a network with 5 nodes will be of size:
- (A) 5×1
- (B) 5×5 ✅
- (C) 5×10
- (D) 10×10

**Q3.** Which centrality measure counts the number of edges connected to a node?
- (A) Betweenness Centrality
- (B) Closeness Centrality
- (C) Degree Centrality ✅
- (D) Eigenvector Centrality

**Q4.** In an undirected graph, the adjacency matrix is:
- (A) Asymmetric
- (B) Symmetric ✅
- (C) Always zero
- (D) Always diagonal

**Q5.** Network Density formula for an undirected graph is:
- (A) E / N
- (B) E / [N(N-1)]
- (C) E / [N(N-1)/2] ✅
- (D) E / (N-1)

**Q6.** Betweenness Centrality identifies:
- (A) Well-connected hubs
- (B) Brokers or gatekeepers in a network ✅
- (C) Nodes closest to all others
- (D) Nodes with highest degree

**Q7.** PageRank was originally developed by:
- (A) Facebook
- (B) Microsoft
- (C) Google ✅
- (D) Twitter

**Q8.** The damping factor in PageRank is typically set to:
- (A) 0.5
- (B) 0.75
- (C) 0.85 ✅
- (D) 0.95

**Q9.** A Star network has a degree centralization value of:
- (A) 0.0
- (B) 0.5
- (C) 0.75
- (D) 1.0 ✅

**Q10.** The Six Degrees of Kevin Bacon concept illustrates:
- (A) Network density
- (B) Small-world property of networks ✅
- (C) Centrality measures
- (D) Adjacency matrices

---

## Section 2: MCQs — Answer ALL (15 × 2 = 30 Marks)

**Q11.** Which of the following are components of a network?
i) Nodes (social actors)
ii) Edges (relationships)
iii) Attributes (properties)
iv) Metadata (descriptive information)
- (A) i & ii only
- (B) i, ii & iii only
- (C) i, ii, iii & iv ✅
- (D) ii & iv only

**Q12.** Which statements about directed and undirected networks are correct?
i) Directed networks have edges with direction
ii) Undirected network adjacency matrix is symmetric
iii) In directed networks, in-degree = out-degree always
iv) Maximum edges in directed graph = N(N-1)
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q13.** Identify the correct match between centrality measure and what it identifies:
- (A) Degree Centrality — Brokers/Gatekeepers
- (B) Betweenness Centrality — Well-connected hubs
- (C) Closeness Centrality — Efficient information spreaders ✅
- (D) Eigenvector Centrality — Shortest path counters

**Q14.** Which of the following are centrality measures?
i) Degree Centrality
ii) Betweenness Centrality
iii) Closeness Centrality
iv) Network Density
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q15.** For a graph with nodes A,B,C,D,E and edges A-B, A-C, B-D, C-D, D-E, which statements are correct?
i) Node D has the highest degree (3)
ii) Node E has the lowest degree (1)
iii) The adjacency matrix is 5×5
iv) The graph is a star network
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q16.** Which statements about Katz Centrality are correct?
i) It considers both direct and indirect connections
ii) It uses a decay factor α for path length
iii) It addresses limitations of eigenvector centrality in directed graphs
iv) It was developed by Google for web page ranking
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q17.** Which statements correctly describe PageRank?
i) A node is important if linked by other important nodes
ii) Damping factor controls distant neighbor influence
iii) It only works for web pages, not social networks
iv) It uses iterative computation until convergence
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q18.** The correct differences between Degree Centrality and Betweenness Centrality are:
i) Degree counts edges, Betweenness counts shortest paths
ii) Degree identifies hubs, Betweenness identifies brokers
iii) Both always give the same ranking for nodes
iv) Betweenness is more complex to compute than Degree
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q19.** Which statements about Network Density are correct?
i) Density ranges from 0 to 1
ii) Complete graph has density = 1.0
iii) Density for directed graph uses N(N-1) not N(N-1)/2
iv) Higher density means fewer connections
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q20.** Which of the following are types of network classification?
i) Star Network
ii) Ring/Lattice Network
iii) Random Network
iv) Circular Network
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q21.** For the graph A-B, A-C, B-D, C-D, D-E, closeness centrality of A involves:
i) Distance A to B = 1
ii) Distance A to C = 1
iii) Distance A to D = 2
iv) Distance A to E = 3
- (A) i, ii, iii & iv all correct ✅
- (B) i & ii only
- (C) i, ii & iii only
- (D) iii & iv only

**Q22.** Which statements about Clustering Coefficient are correct?
i) Global CC measures triangles in the whole network
ii) Local CC measures transitivity at node level
iii) Ego-centric network focuses on one node and its connections
iv) Transitivity means if A-B and B-C, then A-C is likely
- (A) i, ii, iii & iv all correct ✅
- (B) i & ii only
- (C) i, ii & iii only
- (D) iii & iv only

**Q23.** Bridges and Articulation Points:
i) Bridge is an edge whose removal disconnects the network
ii) Articulation Point is a node whose removal disconnects the network
iii) Both identify critical network elements
iv) Bridges are always nodes, not edges
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q24.** Degree Centralization formula CDC = Σ(CDmax - CDi) / [(N-1)(N-2)]. For a star network with 6 nodes:
i) N = 6
ii) Maximum degree = 5
iii) CDC = 1.0
iv) CDC = 0.0
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q25.** Six Degrees of Kevin Bacon illustrates:
i) Any actor can be connected to Kevin Bacon in ≤6 steps
ii) Real-world networks have small-world property
iii) Average path length in social networks is small
iv) All networks are fully connected
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

---

## Section 3: Descriptive — Answer any 6 (6 × 5 = 30 Marks)

**Q26.** Define Social Network and Social Network Analysis (SNA). Explain the interdisciplinary nature of SNA with contributions from at least 4 fields.

**Q27.** Explain the four components of a network — Nodes, Edges, Attributes, and Metadata — with examples from a social media platform.

**Q28.** What is an Adjacency Matrix? Construct the adjacency matrix for a network with 5 nodes (A,B,C,D,E) and edges: A-B, A-C, B-D, C-D, D-E. State whether this matrix would be symmetric or not, and why.

**Q29.** Define and explain any THREE centrality measures (Degree, Betweenness, Closeness, Eigenvector, Katz, PageRank). For each, state what it identifies and give the formula.

**Q30.** Explain PageRank algorithm in detail. Include its formula, damping factor, iterative process, and one real-world application beyond web page ranking.

**Q31.** Define Degree Centralization and Network Density. Calculate both for a star network with 6 nodes where the central node connects to all others. Compare with a ring network of 6 nodes.

**Q32.** Explain Clustering Coefficient (global and local), Transitivity, and Reciprocity. How do these concepts help in understanding friendship patterns in social networks?

---

## Answer Key — Section 1
Q1-B, Q2-B, Q3-C, Q4-B, Q5-C, Q6-B, Q7-C, Q8-C, Q9-D, Q10-B

## Answer Key — Section 2
Q11-C, Q12-A, Q13-C, Q14-A, Q15-A, Q16-A, Q17-A, Q18-A, Q19-A, Q20-A
Q21-A, Q22-A, Q23-A, Q24-A, Q25-A

## 5-Mark Answer Framework (Section 3)
**Structure for every 5-mark answer:**
1. **Definition** (2 lines) — Yaad karna hai
2. **Types/Components** (list with examples)
3. **Formula + Worked Example** (numbers calculate karo)
4. **Advantages & Limitations** (if applicable)
5. **Real-life Example** (Indian/relatable context)
6. **Diagram** (graph + adjacency matrix where relevant)

---

*VIT MCA FAT Pattern: 70 Marks | Section 1: 10×1 | Section 2: 15×2 | Section 3: 6×5*
