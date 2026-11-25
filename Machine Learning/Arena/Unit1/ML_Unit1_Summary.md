# ML Unit 1 — Quick Summary Notes
## Introduction to Machine Learning | One-Page Revision

---

### 🔑 Key Definitions (RAT LO!)

| Term | Definition |
|------|-----------|
| **Machine Learning** | Branch of AI — systems learn from data without explicit programming |
| **Supervised Learning** | Learns from labelled data (inputs + known outputs) |
| **Unsupervised Learning** | Finds hidden patterns in unlabelled data |
| **Reinforcement Learning** | Agent learns by trial & error, maximising reward |
| **Formal Model** | Mathematical framework for ML processes |
| **PAC Learning** | Studies feasibility of learning under uncertainty |

---

### 🏛️ Three Pillars of ML
**Data → Algorithm → Model**

---

### 📊 Types of ML — Quick Table

| Type | Data | Goal | Algorithms |
|------|------|------|-----------|
| **Supervised** | Labelled | Predict output | Linear/Logistic Regression, SVM, DT, NN |
| **Unsupervised** | Unlabelled | Find patterns | K-Means, PCA, DBSCAN, Autoencoders |
| **Reinforcement** | Environment | Maximise reward | Q-Learning, DQN |
| **Self-Supervised** | Unlabelled | Create own signals | Masked prediction |
| **Transfer** | Pre-trained | Reuse knowledge | Fine-tuning |

---

### 🔄 12-Step ML Pipeline (sequence yaad rakho!)
1. Problem Definition → 2. Data Collection → 3. Preprocessing → 4. EDA → 5. Feature Engineering → 6. Model Selection → 7. Training → 8. Evaluation → 9. Hyperparameter Tuning → 10. Deployment → 11. Monitoring → 12. Documentation

---

### 🧮 Key Formulas

```
Supervised:  y = f(x)

PAC:  P(err_D(h) ≤ ε) ≥ 1 − δ
```

---

### 📐 Formal Model Components
- **Instance Space (X)** — all possible inputs
- **Label Space (Y)** — all possible outputs
- **Hypothesis Space (H)** — all functions algorithm considers
- **Target Function (f)** — unknown true mapping X→Y
- **Loss Function L(h(x),y)** — prediction error
- **Generalisation** — performing well on unseen data ✅ REAL GOAL

---

### 📐 PAC Learning Key Elements
- **Sample Complexity** — examples needed; depends on ε, 1-δ, |H|
- **VC Dimension** — measures H capacity; higher = more expressive but needs more data
- **Efficient Learnability** — polynomial-time algorithm exists for PAC criterion

---

### ✅ vs ⚠️ PAC Learning

| Advantages | Limitations |
|-----------|-------------|
| Rigorous mathematical foundation | Assumes i.i.d. data |
| Quantifies trade-offs | Requires h close to c (may not exist) |
| Defines learnability conditions | |

---

### ⚡ Last-Minute Recap (60 seconds before exam)
1. ML = AI branch, learns without programming
2. 3 Pillars: Data + Algorithm = Model
3. Supervised → labelled; Unsupervised → unlabelled; RL → reward
4. 12-step pipeline: Problem → Documentation
5. Formal Model: X, Y, H, f, L, Generalisation
6. PAC: P(err ≤ ε) ≥ 1 − δ, Sample Complexity, VC Dimension

---

*Quick revision complete! All the best!* 🎯
