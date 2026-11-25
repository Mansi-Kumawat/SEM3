# WSA Unit 3 — Quick Revision Summary (One-Page)
## Module 3: Graph Essentials for SMA (Week 3 + Week 4) | OLMCA620

---

## 🔑 KEY DEFINITIONS (RAT LO)

| Term | Definition |
|------|-----------|
| **Social Balance Theory** | Balance of sentiment relations in dyadic/triadic relationships |
| **Small-World Property** | Short avg path length despite large network size |
| **Scale-Free Network** | Network with power law degree distribution P(k) = C × k^(-γ) |
| **Diameter Dia(G)** | Longest shortest path between any pair of nodes |
| **Bridge** | Edge whose removal increases connected components |
| **Ford-Fulkerson** | Algorithm for finding maximum flow via augmenting paths |

---

## ⚖️ SOCIAL BALANCE THEORY — 4 Rules

| Rule | Sign Product | Balanced? |
|------|-------------|-----------|
| Friend of friend = friend | (+)(+)(+) = + | ✅ Yes |
| Friend of enemy = enemy | (+)(-)(-) = + | ✅ Yes |
| Enemy of enemy = friend | (-)(-)(+) = + | ✅ Yes |
| Enemy of friend = enemy | (+)(+)(-) = - | ❌ No |

**Rule: Even negative edges = Balanced, Odd = Unbalanced**

---

## 🛤️ PATH CONCEPTS

| Term | Nodes Repeat? | Edges Repeat? |
|------|-------------|--------------|
| Walk | Yes | Yes |
| Trail | Yes | No |
| Path | No | No |
| Cycle | Start=End only | No |

**Hierarchy: Walk ⊃ Trail ⊃ Path ⊃ Cycle**

---

## 📐 KEY FORMULAS (RAT LO)

| Formula | Expression |
|---------|-----------|
| **Avg Path Length** | L(G) = Σd(i,j) / [N(N-1)/2] |
| **Power Law** | P(k) = C × k^(-γ), γ ∈ [2,3] |
| **Erdos-Renyi** | N nodes, edge probability p |
| **Watts-Strogatz** | Lattice + rewire probability β |
| **Barabasi-Albert** | Growth + Preferential Attachment |

---

## 🌐 4 NETWORK MODELS

| Model | Mechanism | Degree Dist | Clustering | Path Length |
|-------|-----------|------------|-----------|-------------|
| **Random (ER)** | Random edges | Poisson | Low | Short |
| **Regular Lattice** | Neighbor connections | Uniform | High | Long |
| **Small-World (WS)** | Lattice + rewire β | Narrow | High | Short |
| **Scale-Free (BA)** | Growth + Pref. Attach. | Power Law | Varies | Short |

---

## 🎯 MNEMONICS

| Concept | Mnemonic |
|---------|----------|
| Balance Rules | **"FF=F, FE=E, EE=F, EF=E"** |
| Path Hierarchy | **"W ⊃ T ⊃ P ⊃ C"** → "Walk Total Path Circular" |
| Models | **"ER=Random, WS=Small-World, BA=Scale-Free"** |
| Scale-Free Property | **"Robust to random, Fragile to targeted"** |
| Ford-Fulkerson | **"Find path → Push flow → Repeat"** |

---

## 📝 5-MARK ANSWER FRAMEWORK
1. **Definition** (2 lines) — English mein
2. **Types/Components** (list)
3. **Formula + Worked Example**
4. **Properties/Characteristics**
5. **Real-world Example**

---

## ⚠️ COMMON MISTAKES
- Balance Theory ≠ Status Theory (undirected vs directed)
- Diameter ≠ longest path (longest SHORTEST path)
- ER model ≠ Scale-Free (Poisson, not Power Law)
- Ford-Fulkerson ≠ shortest path (it's MAXIMUM FLOW)

---

*For detailed notes: See WSA_Unit3_Lecture.md*
*VIT MCA FAT Pattern: 70 Marks | 10×1 + 15×2 + 6×5*
