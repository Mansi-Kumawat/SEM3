# ML Unit 7 — Quick Summary Notes
## Reinforcement Learning | One-Page Revision

---

### 🔑 Key Definitions

| Term | Definition |
|------|-----------|
| **RL** | Agent learns by trial, error, reward to maximize cumulative return |
| **MDP** | (S, A, P, R, γ) — mathematical framework for RL |
| **Policy π** | Mapping from states to actions |
| **Vπ(s)** | Expected return from state s following π |
| **Qπ(s,a)** | Expected return from (s,a) then following π |
| **Bellman** | V(s) = immediate reward + γ × future value (recursive) |
| **Q-Learning** | Off-policy TD: Q ← Q + α[R + γmaxQ' - Q] |
| **SARSA** | On-policy TD: Q ← Q + α[R + γQ(s',a') - Q] |

---

### 📊 MDP Components
S (States) | A (Actions) | P (Transitions) | R (Rewards) | γ (Discount)

---

### 📐 Formulas (RAT LO!)
```
Q-Learning:  Q(s,a) ← Q(s,a) + α[R + γ max Q(s',a') - Q(s,a)]
SARSA:       Q(s,a) ← Q(s,a) + α[R + γ Q(s',a') - Q(s,a)]
Bellman:     Vπ(s) = Σ π(a|s) Σ P(s'|s,a)[R + γVπ(s')]
```

---

### 📊 Exploration Strategies
ε-greedy | Softmax | UCB | Thompson Sampling

---

### 📊 Q-Learning vs SARSA
| Q-Learning (off-policy, aggressive, max) | SARSA (on-policy, conservative, actual a') |

---

### ⚡ Last-Minute Recap
1. RL: Agent + Environment + Reward loop
2. MDP: S,A,P,R,γ
3. Bellman: Recursive value equations
4. Value Iteration: Update V → converge → extract π*
5. Q-Learning: Off-policy, max update
6. SARSA: On-policy, actual action update
7. Exploration: ε-greedy most common
8. Policy Iteration: Evaluate + Improve
9. Advanced: REINFORCE, Actor-Critic, DQN

---

*ML SUBJECT COMPLETE — All 7 Units Done!* 🎉🎯
