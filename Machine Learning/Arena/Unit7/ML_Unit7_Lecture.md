# ML Unit 7 — Reinforcement Learning
## Complete Lecture Notes (Hinglish) | OLMCA602 | Week 11 + Week 12

---

## 1. Reinforcement Learning Kya Hai?

**Definition:**
> Reinforcement Learning trains an agent to select actions through interaction with an environment to maximize cumulative reward.

**Simple matlab:** Agent trial and error se seekhta hai. Galat action → negative reward (saza). Sahi action → positive reward (inaam). Dheere-dheere agent seekh jaata hai kaunse actions best hain!

**💡 Real Example:** Warehouse robot — position aur obstacles state hain, move/turn action hai, destination pe pahunchne pe reward milta hai.

### 6 Components

| Component | Symbol | Matlab |
|-----------|--------|--------|
| **Agent** | — | Learner/decision-maker |
| **Environment** | — | System agent interact karta hai |
| **State** | s | Current situation |
| **Action** | a | Agent ka decision |
| **Reward** | r | Feedback signal |
| **Policy** | π | Strategy for selecting actions |

---

## 2. MDP — Markov Decision Process

**Definition:**
> MDP is a mathematical framework for RL, defined by tuple (S, A, P, R, γ).

### 5 Components

| Component | Symbol | Description |
|-----------|--------|-------------|
| **States** | S | All possible situations |
| **Actions** | A | Choices available in each state |
| **Transition Probabilities** | P(s'\|s,a) | Probability of reaching s' from s via a |
| **Reward Function** | R(s,a,s') | Reward for transition s→s' via a |
| **Discount Factor** | γ (0 to 1) | Future rewards ka importance |

**Markov Property:** Future depends ONLY on current state — history nahi dekhta!

**💡 γ (gamma) trick:** γ = 0 → sirf immediate reward important. γ = 1 → future rewards bhi equally important. Usually 0.9 ya 0.99 use hota hai.

---

## 3. Policies aur Value Functions

### Policy (π)
State se action ka mapping. Do types:
- **Deterministic:** π(s) = a — har state mein same action
- **Stochastic:** π(a|s) = probability — actions ki probability distribution

### Value Functions

| Function | Notation | Matlab |
|----------|----------|--------|
| **State Value** | Vπ(s) | Expected return from state s, following π |
| **Action Value** | Qπ(s,a) | Expected return from s, taking a, then following π |
| **Optimal Value** | V*(s) | Best possible value for state s |
| **Optimal Q** | Q*(s,a) | Best possible Q-value for (s,a) pair |

**Key Relationship:** Vπ(s) = max over a of Qπ(s,a) under optimal policy

---

## 4. Bellman Equations — RL Ki Backbone!

**Definition:**
> Recursive equations expressing value of a state in terms of values of successor states.

### Bellman for Vπ
```
Vπ(s) = Σ π(a|s) Σ P(s'|s,a) [R(s,a,s') + γVπ(s')]
```

### Bellman for Qπ
```
Qπ(s,a) = Σ P(s'|s,a) [R(s,a,s') + γ Σ π(a'|s') Qπ(s',a')]
```

**💡 Key Idea:** Current state ki value = immediate reward + discounted future value. Ye recursive hai — V(s) depend karta hai V(s') pe!

---

## 5. Value Iteration

**Definition:**
> Iteratively updates state values using Bellman optimality until convergence.

### Algorithm
1. Initialize V(s) = 0 for all states
2. For each state: **V(s) = max_a Σ P(s'|s,a) [R + γV(s')]**
3. Repeat step 2 until values stop changing (convergence)
4. Extract optimal policy: **π*(s) = argmax_a Q(s,a)**

### Grid World Example (3×3)
- Goal at (2,2) with reward +10
- Each move costs -1
- Values propagate from goal outward — jaise paani mein ripples!
- Converged values se optimal policy nikalo — arrows goal ki taraf

---

## 6. Q-Learning — Most Famous RL Algorithm!

**Definition:**
> Off-policy TD learning — learns optimal Q-values without following optimal policy.

### Update Rule — RAT LO!
```
Q(s,a) ← Q(s,a) + α [R + γ max_a' Q(s',a') - Q(s,a)]
```

| Symbol | Name | Matlab |
|--------|------|--------|
| α | Learning rate | Kitna naya seekha accept karo |
| R | Reward | Mila kya? |
| γ | Discount factor | Future importance |
| max Q(s',a') | Best future Q | Aage best kya milega? |
| Q(s,a) | Current Q | Pehle kya socha tha |

**Off-policy:** Optimal policy seekh raha hai lekin explore bhi kar raha hai randomly.

**Tabular:** Q-values ek table mein store hote hain — rows = states, columns = actions.

---

## 7. Exploration vs Exploitation

**Dilemma:** Explore karo (naye actions try — shayad better mile) ya Exploit karo (jo best pata hai wahi karo — safe)?

### 4 Strategies

| Strategy | How | Use Case |
|----------|-----|----------|
| **ε-greedy** | With prob ε: random action. Else: best action | Most common, simple |
| **Softmax** | Probability ∝ e^(Q/τ) | When want smooth exploration |
| **UCB** | Action with highest Q + exploration bonus | Theoretical guarantees |
| **Thompson Sampling** | Sample from posterior distribution | Bayesian approach |

**ε Decay:** Start with high ε (zyada explore) → decrease over time → eventually exploit only.

**💡 Trick:** "Start brave (explore), end wise (exploit)!"

---

## 8. SARSA vs Q-Learning

### SARSA (On-Policy)
```
Q(s,a) ← Q(s,a) + α [R + γQ(s',a') - Q(s,a)]
```
- a' = ACTUAL action taken by current policy
- Conservative — policy jo follow kar raha hai wahi seekhta hai

### Q-Learning (Off-Policy)
```
Q(s,a) ← Q(s,a) + α [R + γ max_a' Q(s',a') - Q(s,a)]
```
- max = BEST possible next action
- Aggressive — directly optimal policy seekhta hai

| Aspect | SARSA | Q-Learning |
|--------|-------|------------|
| **Policy** | On-policy | Off-policy |
| **Update uses** | Actual a' | Best max a' |
| **Behavior** | Conservative | Aggressive |
| **Risk** | Safer (avoids cliffs) | Risk-taking (finds optimal) |

---

## 9. Policy Iteration

**Algorithm:** Two steps alternate until convergence:

### Step 1: Policy Evaluation
- Given policy π, compute Vπ(s) for all states
- Use Bellman equation iteratively
- Repeat until V values converge

### Step 2: Policy Improvement
- For each state: π'(s) = argmax_a Q(s,a)
- If policy changed → go back to Step 1
- If no change → **Optimal policy π* found!** ✅

**Guaranteed to converge** to optimal policy!

---

## 10. Advanced RL Methods

| Method | Type | Key Idea |
|--------|------|----------|
| **Policy Iteration** | Classic | Evaluate + Improve alternate |
| **Value Iteration** | Classic | Direct V update, extract policy |
| **Q-Learning** | TD (off-policy) | Tabular Q-value updates |
| **SARSA** | TD (on-policy) | Actual action updates |
| **REINFORCE** | Policy Gradient | Directly optimize policy via gradient ascent |
| **Actor-Critic** | Hybrid | Actor=policy, Critic=value function |
| **DQN** | Deep RL | Neural network for Q-values + experience replay + target network |

**💡 DQN breakthrough:** DeepMind ne Atari games mein human-level performance achieve kiya — neural network + Q-learning!

---

## 11. Exam-Ready Recap

### Must-Remember Formulas
```
Bellman V:    Vπ(s) = Σ π(a|s) Σ P(s'|s,a)[R + γVπ(s')]
Q-Learning:   Q(s,a) ← Q(s,a) + α[R + γ max Q(s',a') - Q(s,a)]
SARSA:        Q(s,a) ← Q(s,a) + α[R + γ Q(s',a') - Q(s,a)]
```

### 5-Mark Answer Structure
**Definition → Components → Algorithm/Steps → Advantages → Disadvantages → Applications**

### Common Exam Questions
- RL components + agent-environment loop
- MDP formulation (S, A, P, R, γ)
- Bellman equations for V and Q
- Value Iteration algorithm + grid world example
- Q-Learning update rule + numerical example
- SARSA vs Q-Learning comparison
- Exploration vs Exploitation strategies
- Policy Iteration steps

---

## 🎉 ML SUBJECT COMPLETE!

All 7 units done — Introduction se leke Reinforcement Learning tak! 🏆

---

*End of Unit 7 — Reinforcement Learning* 🎯
