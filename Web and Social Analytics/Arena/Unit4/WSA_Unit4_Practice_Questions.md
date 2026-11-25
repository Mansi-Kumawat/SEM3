# WSA Unit 4 — Practice Questions (VIT MCA FAT Pattern)
## Module 4: Community Analysis & Information Diffusion (W5 + W6)
## Exam Pattern: 70 Marks | 2h 30min | Section 1 (10×1) + Section 2 (15×2) + Section 3 (6×5)

---

## Section 1: MCQs — Answer ALL (10 × 1 = 10 Marks)

**Q1.** A community in a social network is characterized by:
- (A) Sparse internal connections and dense external connections
- (B) Dense internal connections and sparse external connections ✅
- (C) Equal internal and external connections
- (D) No connections at all

**Q2.** In a clique:
- (A) Only some pairs of nodes are connected
- (B) Every pair of nodes is directly connected ✅
- (C) No nodes are connected
- (D) Only adjacent nodes are connected

**Q3.** Girvan-Newman algorithm detects communities by:
- (A) Adding edges with highest weight
- (B) Removing edges with highest betweenness centrality ✅
- (C) Merging nodes with similar attributes
- (D) Random edge deletion

**Q4.** Modularity Q value of 0 indicates:
- (A) Perfect community structure
- (B) Random network with no community structure ✅
- (C) Overlapping communities
- (D) Single community

**Q5.** Which method uses modularity optimization with local moving and aggregation phases?
- (A) Label Propagation
- (B) Girvan-Newman
- (C) Louvain Method ✅
- (D) Infomap

**Q6.** Herd Behaviour occurs when individuals:
- (A) Always use their own private information
- (B) Follow actions of others rather than own information ✅
- (C) Make completely random decisions
- (D) Never observe others' actions

**Q7.** In the SIR model, 'R' stands for:
- (A) Random
- (B) Repeated
- (C) Recovered ✅
- (D) Removed permanently

**Q8.** The basic reproduction number R₀ > 1 indicates:
- (A) Epidemic will die out
- (B) Epidemic will spread (viral) ✅
- (C) Steady state
- (D) No infection possible

**Q9.** Asch's Conformity Experiment found that what percentage conformed at least once?
- (A) 25%
- (B) 50%
- (C) 75% ✅
- (D) 100%

**Q10.** In the Independent Cascade Model:
- (A) Each node can activate neighbors multiple times
- (B) Each newly activated node gets one chance per neighbor ✅
- (C) All nodes activate simultaneously
- (D) Activation is deterministic

---

## Section 2: MCQs — Answer ALL (15 × 2 = 30 Marks)

**Q11.** Which statements about Explicit and Implicit Communities are correct?
i) Explicit communities are clearly defined groups
ii) Implicit communities are discovered through network analysis
iii) Members of implicit communities always know they belong
iv) Facebook Groups are examples of explicit communities
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q12.** Overlapping vs Disjoint Communities:
i) Disjoint: each node in exactly one community
ii) Overlapping: nodes can belong to multiple communities
iii) Real-world networks are mostly disjoint
iv) Overlapping is more common in real networks
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q13.** Clique concepts:
i) Clique: every pair of nodes connected
ii) Maximal clique: not contained in larger clique
iii) Maximum clique: smallest maximal clique
iv) Maximum clique: largest maximal clique
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q14.** Girvan-Newman Algorithm steps:
i) Calculate betweenness centrality for all edges
ii) Remove edge with highest betweenness
iii) Recalculate betweenness
iv) Repeat until communities emerge
- (A) i, ii, iii & iv all correct ✅
- (B) i & ii only
- (C) i, ii & iii only
- (D) ii & iv only

**Q15.** Modularity (Q) properties:
i) Q ranges from -0.5 to 1
ii) Q > 0.3 indicates significant community structure
iii) Higher Q = better community division
iv) Q = 0 means perfect communities
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q16.** Label Propagation method:
i) Each node starts with unique label
ii) Nodes adopt most common neighbor label
iii) Results are always deterministic
iv) Fast but results can vary
- (A) i, ii & iv only ✅
- (B) i & iii only
- (C) ii & iii only
- (D) All of the above

**Q17.** Louvain Method features:
i) Modularity optimization approach
ii) Two phases: local moving and aggregation
iii) Produces hierarchical communities
iv) Only works for small networks
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q18.** Conditions for Herd Behaviour:
i) Sequential decision making
ii) Limited private information
iii) Observable actions of others
iv) Only irrational individuals herd
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q19.** SIR Model components:
i) S = Susceptible (can be infected)
ii) I = Infected (currently spreading)
iii) R = Recovered (immune)
iv) S + I + R = N (total population)
- (A) i, ii, iii & iv all correct ✅
- (B) i & ii only
- (C) i, ii & iii only
- (D) ii & iv only

**Q20.** Information Cascade characteristics:
i) Individuals follow predecessors' actions
ii) Can occur even with private information
iii) Creates chain of similar decisions
iv) Always leads to correct outcomes
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q21.** Clique Percolation Method:
i) For overlapping community detection
ii) Based on k-clique communities
iii) Two k-cliques adjacent if share k-1 nodes
iv) Only detects disjoint communities
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q22.** Spectral Clustering:
i) Uses eigenvalues of Laplacian matrix
ii) Laplacian L = D - A
iii) Apply k-means on eigenvector space
iv) Only works for convex shapes
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q23.** Internal Community Evaluation Metrics:
i) Modularity Q (higher = better)
ii) Conductance (lower = better)
iii) Coverage (higher = better)
iv) NMI (requires ground truth)
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q24.** Diffusion of Innovation adopter categories:
i) Innovators: 2.5%, risk-takers
ii) Early Adopters: 13.5%, opinion leaders
iii) Late Majority: 34%, skeptical
iv) Laggards: 16%, first to adopt
- (A) i, ii & iii only ✅
- (B) i & iv only
- (C) ii & iii only
- (D) All of the above

**Q25.** Implications of Herd Behaviour:
i) Marketing: viral campaigns and influencer seeding
ii) Public Health: vaccination campaigns
iii) Financial Markets: bubbles and crashes
iv) Social Movements: rapid mobilization
- (A) i, ii, iii & iv all correct ✅
- (B) i & ii only
- (C) i, ii & iii only
- (D) iii & iv only

---

## Section 3: Descriptive — Answer any 6 (6 × 5 = 30 Marks)

**Q26.** Define Social Communities. Differentiate between Explicit and Implicit communities with examples. Explain Overlapping vs Disjoint communities.

**Q27.** What is a Clique? Define Maximal Clique and Maximum Clique. Explain the Girvan-Newman algorithm with its steps. Use Zachary's Karate Club as a case study.

**Q28.** Define Modularity (Q). Write its formula and explain each term. What does Q > 0.3 indicate? Compare with Conductance and Coverage metrics.

**Q29.** Compare Label Propagation, Louvain Method, and Infomap for community detection. Include mechanism, advantages, and best use cases for each.

**Q30.** Explain Information Diffusion with the Oreo viral tweet case study. Define Herd Behaviour and list four conditions for it. Describe the Asch Conformity Experiment.

**Q31.** What is an Information Cascade? Explain the Independent Cascade Model (ICM) with its key assumptions. How does it differ from the Linear Threshold Model?

**Q32.** Explain the SIR Epidemic Model. Define S, I, R compartments with social media examples. Write the differential equations. What does R₀ = β/γ tell us about viral spread?

---

## Answer Key — Section 1
Q1-B, Q2-B, Q3-B, Q4-B, Q5-C, Q6-B, Q7-C, Q8-B, Q9-C, Q10-B

## Answer Key — Section 2
Q11-A, Q12-A, Q13-A, Q14-A, Q15-A, Q16-A, Q17-A, Q18-A, Q19-A, Q20-A
Q21-A, Q22-A, Q23-A, Q24-A, Q25-A

---

*VIT MCA FAT Pattern: 70 Marks | Section 1: 10×1 | Section 2: 15×2 | Section 3: 6×5*
