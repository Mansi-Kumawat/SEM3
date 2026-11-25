# Web and Social Media Analytics — Unit 5 Comprehensive Lecture Notes
## Module 5: Influence & Homophily, Behaviour Analytics (Week 7 + Week 8)
### Subject: OLMCA620 | Programme: MCA | VIT Online Education

---

## Learning Objectives
By the end of this unit, you will be able to:
1. **Define** Influence, Homophily, and Confounding in social networks
2. **Explain** Assortativity and calculate Assortativity Coefficient (r)
3. **Differentiate** Influence from Homophily with examples
4. **Describe** types of Homophily (Base, Induced, Status, Value)
5. **Calculate** Homophily Index (H) with formula
6. **Apply** Shuffle Test, Edge Reversal Test, and Randomisation Test
7. **Explain** Behaviour Analytics and Collective Behaviour
8. **Answer** exam questions using the 5-mark framework

---

## 1. Social Forces: Influence, Homophily & Confounding

### Hook 🎯
Do dost ek saath smoking shuru karte hain. Kya reason hai? (a) Ek ne dusre ko influence kiya? (b) Dono similar the isliye dost bane (homophily)? (c) Dono ek hi environment mein the (confounding)? Ye teen forces distinguish karna hi Unit 5 ka core hai!

### Three Social Forces 🌟

| Force | Definition | Example |
|-------|-----------|---------|
| **Influence** | Friends affect each other's behaviour through network ties | Friend starts smoking → you start too |
| **Homophily** | Similar people form connections ("birds of a feather flock together") | Both like cricket → become friends |
| **Confounding** | External factor affects both individuals | Same college environment, same choices |

### Key Challenge 🌟
All three forces produce **similar network patterns** — friends who are similar. Statistical tests needed to distinguish which force is actually at work!

---

## 2. Assortativity in Social Networks

### Definition (YAAD KARO — Exam)
> **"Assortativity is the tendency of nodes to connect with similar nodes. Positive assortativity means similar nodes connect more; negative means dissimilar nodes connect."**

### Types of Mixing 🌟

| Type | Description | Coefficient | Example |
|------|-------------|-------------|---------|
| **Assortative** | Similar nodes connect | r > 0 | Age, interests in social networks |
| **Disassortative** | Different nodes connect | r < 0 | Supplier-buyer networks |
| **Neutral** | Random mixing | r ≈ 0 | Random networks |

---

## 3. Measuring Assortativity

### Assortativity Coefficient (r) 🌟
> **"The assortativity coefficient r measures the correlation of node attributes across edges in the network."**

### Formula 🌟
**r = (1/σ²_q) × Σᵢⱼ [Aᵢⱼ - (kᵢ × kⱼ)/(2m)] × xᵢ × xⱼ**

Where:
- Aᵢⱼ = adjacency matrix element
- kᵢ, kⱼ = degrees of nodes i and j
- m = total number of edges
- xᵢ = attribute value of node i
- σ²_q = variance of attribute distribution

### Interpretation 🌟

| r Value | Meaning |
|---------|---------|
| **r = 1** | Perfect assortative (all similar nodes connected) |
| **r = 0** | Random mixing |
| **r = -1** | Perfect disassortative (all different nodes connected) |
| **r > 0** | Social networks typically assortative |

---

## 4. Influence in Social Networks

### Definition (YAAD KARO — Exam)
> **"Influence occurs when one node's behaviour or state affects another node's behaviour through network ties."**

### Types of Influence 🌟

| Type | Description | Example |
|------|-------------|---------|
| **Direct Influence** | Friend directly affects your decision | Friend recommends a movie |
| **Indirect Influence** | Friend of friend affects you | FOFO recommends a product |
| **Normative Influence** | Conformity to group norms | Dress like your group |
| **Informational Influence** | Learning from others' information | Follow expert's advice |

### Measuring Influence 🌟
- Compare behaviour **before** and **after** connection forms
- **Temporal data required** — multiple time points
- Must **control for homophily and confounding**

---

## 5. Homophily — Definition & Types

### Definition (YAAD KARO — Exam)
> **"Homophily is the tendency of individuals to associate and bond with similar others — birds of a feather flock together."**

### Types of Homophily 🌟

| Type | Description | Example |
|------|-------------|---------|
| **Base Homophily** | From population distribution | Age, gender, race |
| **Induced Homophily** | From network structure and preferences | Friend-of-friend connections |
| **Status Homophily** | Similar socioeconomic status | Same income group friends |
| **Value Homophily** | Similar beliefs and attitudes | Same political views |

### Factors Influencing Homophily 🌟
- Demographics (age, gender, location)
- Beliefs and attitudes
- Behaviours (smoking, exercise)
- Geographic proximity

---

## 6. Measuring Homophily

### Homophily Index (H) 🌟

**H = (Observed same-type edges - Expected same-type edges) / (Total edges - Expected same-type edges)**

### Interpretation 🌟

| H Value | Meaning |
|---------|---------|
| **H = 1** | Complete homophily (all connections within same type) |
| **H = 0** | Random mixing |
| **H < 0** | Heterophily (prefer different types) |

### Algorithm for Homophily Modelling 🌟
```
Step 1: Identify node attributes (age, gender, etc.)
Step 2: Count same-type and cross-type edges
Step 3: Calculate expected edges under random mixing
Step 4: Compute Homophily Index H
Step 5: Compare with significance threshold
```

---

## 7. Distinguishing Influence vs Homophily

### The Core Problem 🌟
Both produce **similar network patterns**:
- **Influence pattern:** Friends become similar **over time** — behaviour changes AFTER connection
- **Homophily pattern:** Friends are similar **from the start** — no temporal change needed

### Visual Comparison 🌟

| Aspect | Influence | Homophily |
|--------|-----------|-----------|
| **Timing** | Change happens AFTER connection | Similar from BEGINNING |
| **Mechanism** | Behaviour spreads through ties | Similar people self-select |
| **Temporal pattern** | Convergence over time | Stable similarity |
| **Example** | Friend exercises → you exercise | Both like sports → become friends |

---

## 8. Shuffle Test & Edge Reversal Test

### Shuffle Test (for Homophily) 🌟
```
Step 1: Randomly shuffle node attributes across the network
Step 2: Recalculate assortativity with shuffled attributes
Step 3: Compare observed vs shuffled assortativity
Step 4: If observed >> shuffled → significant homophily exists
```
- Breaks the link between attributes and network structure
- Tests if observed assortativity is more than chance

### Edge Reversal Test (for Influence) 🌟
```
Step 1: Reverse the direction of ALL edges in the network
Step 2: Re-measure influence with reversed edges
Step 3: Real influence should DISAPPEAR with reversed edges
Step 4: If influence persists → likely homophily, not influence
```
- Influence is directional — reversing should eliminate it
- Homophily is non-directional — persists after reversal

---

## 9. Randomisation Test & Significance Tests

### Randomisation Test 🌟
```
Step 1: Generate random networks preserving degree distribution
Step 2: Measure influence/homophily on random networks
Step 3: Build distribution of random values
Step 4: Compare observed value with random distribution
Step 5: Calculate p-value
```

### Significance Tests Requirements 🌟
- **Temporal data required** — behaviour at multiple time points
- **Control confounding variables**
- **Statistical significance:** p < 0.05
- **Longitudinal network data** is essential

---

## 10. Behaviour Analytics

### Definition 🌟
> **"Behaviour Analytics is the study of user behaviour patterns in social networks using data analysis to understand, predict, and optimize user actions."**

### Key Aspects 🌟

| Aspect | Description | Example |
|--------|-------------|---------|
| **User Activity Patterns** | Posting frequency, timing, engagement | Peak hours analysis |
| **Content Preferences** | Types of content consumed and shared | Video vs text preference |
| **Social Interaction Patterns** | Who interacts with whom and how | Comment patterns |
| **Behavioural Segmentation** | Grouping users by behaviour | Active vs passive users |

### Applications 🌟
- Personalized recommendations
- Anomaly detection (bots, fake accounts)
- User experience optimization
- Targeted marketing campaigns

---

## 11. Collective Behaviour

### Definition 🌟
> **"Collective Behaviour refers to emergent patterns that arise from the interactions of many individuals in a network, without central coordination."**

### Examples 🌟

| Example | Description |
|---------|-------------|
| **Trending Topics** | Hashtags going viral on Twitter |
| **Flash Mobs** | Rapid social mobilization |
| **Crowd Behaviour** | Collective response during events |
| **Social Movements** | #MeToo, Climate strikes |

### Key Concepts 🌟
- **Emergence:** Complex patterns from simple individual rules
- **Self-organization:** No central control needed
- **Tipping point:** Critical mass for cascade effect
- **Network effects:** Amplify collective behaviour

---

## 12. Case Study: Smoking Behaviour (Christakis & Fowler)

### Key Findings 🌟
- Smoking spreads through social networks **like a contagion**
- If a friend quits smoking → your chance of quitting **increases by 36%**
- Effect **stronger in close mutual friendships**
- Demonstrates **both influence AND homophily** at work

### Network Effects 🌟
- **Central nodes** influence more people
- **Three degrees of influence:** friend → friend of friend → friend of friend of friend
- Behaviour change can **cascade** through networks
- Implications for **public health interventions**

---

## 13. Exam-Ready Recap

### Key Definitions:
1. **Influence** → Behaviour spreads through network ties over time
2. **Homophily** → Similar people connect (birds of a feather)
3. **Confounding** → External factor affecting both nodes
4. **Assortativity Coefficient r** → Correlation of attributes across edges
5. **Homophily Index H** → Observed vs expected same-type edges

### Key Formulas:
- **r** = (1/σ²_q) × Σ[Aᵢⱼ - kᵢkⱼ/2m] × xᵢ × xⱼ
- **H** = (Observed - Expected) / (Total - Expected) same-type edges
- **p < 0.05** → statistically significant

### Tests to Distinguish:
- **Shuffle Test** → tests homophily significance
- **Edge Reversal** → tests if influence is real
- **Randomisation** → generates null distribution

### 5-Mark Answer Framework:
1. Definition → 2. Types → 3. Formula → 4. Example → 5. Test/Application

---

## 14. Learning Tricks (Yaad Rakhne Ke Tarike)

### Trick 1: Three Forces
**"I-H-C"** → Influence, Homophily, Confounding
→ *"I Have Confusion!"* (distinguishing them is the challenge)

### Trick 2: Assortativity Values
**r = 1** → Same, **r = 0** → Random, **r = -1** → Different
→ *"Positive = Partner, Zero = Zero clue, Negative = No-way"*

### Trick 3: Influence vs Homophily
**Influence:** Connection → Change (temporal)
**Homophily:** Similar → Connection (instant)
→ *"Influence = Imitate Later, Homophily = Happen Initially"*

### Trick 4: Tests
**Shuffle** = Homophily, **Edge Reversal** = Influence, **Randomisation** = Both
→ *"SHuffle for Same-type, REverse for Real influence, RAndom for both"*

---

## 15. Common Mistakes to Avoid ❌

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Influence = Homophily | Different mechanisms — influence is temporal, homophily is selection |
| r can be > 1 | r ranges from -1 to 1 |
| Edge reversal proves influence | Edge reversal DISPROVES influence (if persists = homophily) |
| H < 0 means strong homophily | H < 0 means HETEROPHILY (prefer different) |
| No temporal data needed | Temporal data IS required for distinguishing influence from homophily |

---

## 16. Sources Used

| Source | Content Used |
|--------|-------------|
| VIT_MSc_Ds_WSMA_W7_Study_Material.pdf | Week 7 notes — Influence, Homophily, Assortativity |
| VIT_MSc_Ds_WSMA_W8_Study_Material.pdf | Week 8 notes — Distinguishing tests, Behaviour Analytics |
| W7_Influence_and_Homophily.pdf | Week 7 PPT — Visual references |
| W8 WSA.pdf | Week 8 PPT — Behaviour analytics content |
| Syllabus OLMCA620 | Module 5 scope |
| VIT MCA FAT Pattern (PYQ) | Exam structure: 10×1 + 15×2 + 6×5 = 70 marks |

---

## 17. Topic Coverage Checklist

| Syllabus Topic (Module 5) | Status | Section |
|---------------------------|--------|---------|
| Influence in Social Networks | ✅ | Section 4 |
| Homophily — definition & types | ✅ | Section 5 |
| Confounding | ✅ | Section 1 |
| Assortativity | ✅ | Section 2, 3 |
| Measuring Assortativity (r) | ✅ | Section 3 |
| Measuring Homophily (H) | ✅ | Section 6 |
| Distinguishing Influence vs Homophily | ✅ | Section 7 |
| Shuffle Test | ✅ | Section 8 |
| Edge Reversal Test | ✅ | Section 8 |
| Randomisation Test | ✅ | Section 9 |
| Behaviour Analytics | ✅ | Section 10 |
| Collective Behaviour | ✅ | Section 11 |
| Case Study (Smoking) | ✅ | Section 12 |

### Coverage: 13/13 topics = 100% ✅

---

*Subject: Web and Social Media Analytics (OLMCA620)*
*Unit 5 — Module 5: Influence & Homophily, Behaviour Analytics*
*Last Updated: November 2025 | VIT MCA Semester 3*
