# WSA Unit 3 — Practice Questions (VIT MCA FAT Pattern)
## Module 3: Graph Essentials for SMA (Week 3 + Week 4)
## Exam Pattern: 70 Marks | 2h 30min | Section 1 (10×1) + Section 2 (15×2) + Section 3 (6×5)

---

## Section 1: MCQs — Answer ALL (10 × 1 = 10 Marks)

**Q1.** According to Social Balance Theory, a triangle with signs (+, +, -) is:
- (A) Balanced
- (B) Unbalanced ✅
- (C) Neutral
- (D) Complete

**Q2.** In a network, a Path is defined as:
- (A) A walk with repeated edges allowed
- (B) A walk with no repeated nodes ✅
- (C) A walk that returns to the starting node
- (D) Any sequence of edges

**Q3.** The Diameter of a network is:
- (A) Average shortest path length
- (B) Longest shortest path between any pair of nodes ✅
- (C) Total number of edges
- (D) Maximum degree of any node

**Q4.** Milgram's Small-World Experiment (1967) found average chain length of:
- (A) 3 steps
- (B) 4 steps
- (C) 6 steps ✅
- (D) 10 steps

**Q5.** The Erdos-Renyi model produces networks with which degree distribution?
- (A) Power Law
- (B) Poisson ✅
- (C) Uniform
- (D) Exponential

**Q6.** Scale-Free Networks follow which distribution?
- (A) Normal Distribution
- (B) Poisson Distribution
- (C) Power Law Distribution ✅
- (D) Uniform Distribution

**Q7.** The Barabasi-Albert Model uses which two mechanisms?
- (A) Random placement and Deletion
- (B) Growth and Preferential Attachment ✅
- (C) Rewiring and Clustering
- (D) Lattice and Random

**Q8.** In the Watts-Strogatz model, β = 0 produces:
- (A) Random graph
- (B) Regular lattice ✅
- (C) Scale-free network
- (D) Complete graph

**Q9.** Ford-Fulkerson algorithm is used to find:
- (A) Shortest path
- (B) Maximum flow in a network ✅
- (C) Minimum spanning tree
- (D) Network diameter

**Q10.** A Bridge in a graph is:
- (A) A node with highest degree
- (B) An edge whose removal disconnects the graph ✅
- (C) The shortest path between two nodes
- (D) A cycle in the network

---

## Section 2: MCQs — Answer ALL (15 × 2 = 30 Marks)

**Q11.** Which of the following represent balanced triangles in Social Balance Theory?
i) (+, +, +) — all friends
ii) (+, +, -) — one enemy
iii) (+, -, -) — two enemies
iv) (-, -, -) — all enemies
- (A) i & iii only ✅
- (B) i & ii only
- (C) ii & iv only
- (D) All of the above

**Q12.** Which statements about Structural and Regular Equivalence are correct?
i) Structural equivalence: nodes connected to same others
ii) Regular equivalence: nodes with similar tie patterns
iii) Both measure the same concept
iv) Structural equivalence is stricter than regular equivalence
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q13.** The correct hierarchy of path concepts is:
i) Every cycle is a path (except start=end)
ii) Every path is a trail
iii) Every trail is a walk
iv) Every walk is a path
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q14.** Small-World Property characteristics include:
i) Short average path length
ii) High clustering coefficient
iii) Only found in small networks
iv) Demonstrated by Six Degrees of Separation
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q15.** Which statements about Scale-Free Networks are correct?
i) Degree distribution follows power law P(k) = C × k^(-γ)
ii) γ is typically between 2 and 3
iii) Robust to random node failures
iv) Vulnerable to targeted hub attacks
- (A) i, ii, iii & iv all correct ✅
- (B) i & ii only
- (C) i, ii & iii only
- (D) iii & iv only

**Q16.** The correct differences between Erdos-Renyi and Watts-Strogatz models:
i) ER has low clustering, WS has high clustering
ii) Both have short average path lengths
iii) ER uses rewiring, WS uses random edge placement
iv) WS can produce small-world networks
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q17.** Barabasi-Albert Model features:
i) Growth mechanism — new nodes continuously added
ii) Preferential attachment — new nodes connect to high-degree nodes
iii) Produces Poisson degree distribution
iv) "Rich get richer" phenomenon
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q18.** Flow Network constraints include:
i) Capacity constraint: 0 ≤ F(u,v) ≤ C(u,v)
ii) Flow conservation: flow in = flow out at intermediate nodes
iii) Negative flow is allowed
iv) Source has no incoming flow requirement
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q19.** Ford-Fulkerson Algorithm steps include:
i) Initialize flow = 0
ii) Find augmenting path in residual graph
iii) Push bottleneck capacity along path
iv) Stop when shortest path is found
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q20.** Bridge Detection concepts:
i) Bridge removal increases connected components
ii) Local bridge has neighborhood overlap = 0
iii) All bridges are local bridges
iv) Bridge detection helps in network robustness analysis
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q21.** Power Law Distribution characteristics:
i) P(k) = C × k^(-γ)
ii) Few hubs with very high degree
iii) Log-log plot gives straight line
iv) Most nodes have very high degree
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q22.** Network Vulnerability analysis shows:
i) Random failure: network survives (robust)
ii) Targeted attack on hubs: network collapses (fragile)
iii) Scale-free networks are equally vulnerable to both
iv) This is called "robust yet fragile" paradox
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q23.** Facebook's 2016 study on small-world property found:
i) Average separation of 4.74 degrees
ii) Smaller than Milgram's 6 degrees
iii) Social networks are getting more connected
iv) Average separation of 10 degrees
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q24.** Network Visualization tools and features:
i) Gephi is open source
ii) Force-directed layouts minimize edge crossings
iii) Node size can represent centrality
iv) NetworkX is a Java library
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q25.** Applications of Bridge Detection and Flow Algorithms:
i) Transportation network routing
ii) Social network weak tie identification
iii) Resource allocation
iv) Image processing
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

---

## Section 3: Descriptive — Answer any 6 (6 × 5 = 30 Marks)

**Q26.** Explain Social Balance Theory with its four rules. Define balanced and unbalanced triangles with examples. How is balance measured mathematically?

**Q27.** Differentiate between Structural Equivalence and Regular Equivalence. Explain Social Status Theory and how it differs from Social Balance Theory.

**Q28.** Define Walk, Trail, Path, and Cycle with examples. Explain the relationship between these concepts. Calculate the Average Path Length and Diameter for a given 5-node network.

**Q29.** Explain the Small-World Property. Describe Milgram's Small-World Experiment and its findings. How did Facebook's 2016 study validate this concept?

**Q30.** Compare and contrast Erdos-Renyi, Watts-Strogatz, and Barabasi-Albert network models. Include their mechanisms, degree distributions, and real-world applicability.

**Q31.** What are Scale-Free Networks? Explain Power Law Distribution with formula. Discuss the "Robust Yet Fragile" paradox with real-world examples.

**Q32.** Explain Flow Networks and the Ford-Fulkerson Algorithm. Define source, sink, capacity, augmenting path, and residual network. Describe Bridge Detection and its applications.

---

## Answer Key — Section 1
Q1-B, Q2-B, Q3-B, Q4-C, Q5-B, Q6-C, Q7-B, Q8-B, Q9-B, Q10-B

## Answer Key — Section 2
Q11-A, Q12-A, Q13-A, Q14-A, Q15-A, Q16-A, Q17-A, Q18-A, Q19-A, Q20-A
Q21-A, Q22-A, Q23-A, Q24-A, Q25-A

## 5-Mark Answer Framework
1. **Definition** (2 lines) → 2. **Types/Components** → 3. **Formula + Example** → 4. **Properties** → 5. **Real-world Example**

---

*VIT MCA FAT Pattern: 70 Marks | Section 1: 10×1 | Section 2: 15×2 | Section 3: 6×5*
