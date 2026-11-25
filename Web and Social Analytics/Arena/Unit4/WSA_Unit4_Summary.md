# WSA Unit 4 — Quick Revision Summary (One-Page)
## Module 4: Community Analysis & Information Diffusion | OLMCA620

---

## 🔑 KEY DEFINITIONS (RAT LO)

| Term | Definition |
|------|-----------|
| **Community** | Group with dense internal connections, sparse external connections |
| **Clique** | Subset where every pair is directly connected |
| **Modularity Q** | Quality of community division (actual vs expected edges) |
| **Girvan-Newman** | Remove highest betweenness edges iteratively |
| **Herd Behaviour** | Following others' actions despite own information |
| **Information Cascade** | Chain of decisions following predecessors |
| **SIR Model** | Susceptible → Infected → Recovered compartments |

---

## 🏘️ COMMUNITY TYPES

| Type | Description |
|------|-------------|
| **Explicit** | Clearly defined, members aware (Facebook Groups) |
| **Implicit** | Discovered via analysis, members unaware |
| **Disjoint** | Each node in exactly ONE community |
| **Overlapping** | Nodes can be in MULTIPLE communities |

---

## 🔧 COMMUNITY DETECTION METHODS

| Method | Key Idea | Best For |
|--------|----------|----------|
| **Girvan-Newman** | Remove high betweenness edges | Small networks |
| **Label Propagation** | Adopt neighbor's most common label | Fast, large networks |
| **Louvain** | Modularity optimization, hierarchical | Large networks |
| **Infomap** | Minimize random walk description length | Directed/weighted |
| **Clique Percolation** | k-clique unions | Overlapping communities |
| **Spectral Clustering** | Eigenvectors of Laplacian + k-means | Non-convex shapes |

---

## 📐 KEY FORMULAS (RAT LO)

| Formula | Expression |
|---------|-----------|
| **Modularity Q** | (1/2m) × Σ[Aij - ki·kj/2m] × δ(ci,cj) |
| **Good Q value** | Q > 0.3 = significant community structure |
| **SIR: dI/dt** | βSI/N - γI |
| **R₀** | β/γ (R₀ > 1 = viral spread) |
| **Laplacian** | L = D - A |

---

## 🦠 SIR MODEL

| Compartment | Meaning | Social Media Analogy |
|-------------|---------|---------------------|
| **S** | Susceptible | Haven't seen meme |
| **I** | Infected | Actively sharing |
| **R** | Recovered | Saw it, stopped sharing |

**R₀ = β/γ**: R₀ > 1 → Viral! R₀ < 1 → Dies out

---

## 🐑 HERD BEHAVIOUR

**Conditions: "SLO-R"**
- **S**equential decisions
- **L**imited private info
- **O**bservable actions
- **R**ational can still herd!

**Key Studies:** Asch (75% conformed), Anderson-Holt (lab cascades)

---

## 🧠 MNEMONICS

| Concept | Mnemonic |
|---------|----------|
| Detection Methods | **"GN-LP-L-IM-CP-SC"** → "Guru Nanak Loved Peace In My Country Society" |
| Adopter Categories | **"IE-ELL"** → "I Eat Every Last Ladoo" |
| SIR Flow | **"S→I→R"** → "Pehle Bimaro, Phir Theek Ho" |

---

## 📝 5-MARK ANSWER FRAMEWORK
1. **Definition** → 2. **Types/Components** → 3. **Algorithm/Process** → 4. **Example** → 5. **Application**

---

## ⚠️ COMMON MISTAKES
- Q > 1 possible? NO! Q ranges -0.5 to 1
- Girvan-Newman adds edges? NO! It REMOVES them
- Herd = irrational? NO! Even rational people herd
- R₀ < 1 = epidemic? NO! R₀ > 1 = epidemic

---

*For detailed notes: See WSA_Unit4_Lecture.md*
*VIT MCA FAT Pattern: 70 Marks | 10×1 + 15×2 + 6×5*
