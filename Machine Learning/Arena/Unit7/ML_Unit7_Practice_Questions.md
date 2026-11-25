# ML Unit 7 — Practice Questions
## Reinforcement Learning (Week 11 + Week 12)

---

## Part A: Multiple Choice (1 Mark)

**Q1.** RL agent maximizes: (A) Immediate reward (B) Cumulative reward (C) Number of actions (D) States visited
**Answer: (B)**

**Q2.** MDP has how many components? (A) 3 (B) 4 (C) 5 (D) 6
**Answer: (C)** — S, A, P, R, γ

**Q3.** γ (gamma) is: (A) Learning rate (B) Discount factor (C) Reward (D) State
**Answer: (B)**

**Q4.** Q-Learning is: (A) On-policy (B) Off-policy (C) Model-based (D) Supervised
**Answer: (B)**

**Q5.** SARSA uses: (A) max Q(s',a') (B) Actual Q(s',a') (C) V(s') (D) Random Q
**Answer: (B)**

**Q6.** ε-greedy with ε=0.1 means: (A) 10% exploit (B) 10% explore (C) Always explore (D) Never explore
**Answer: (B)**

**Q7.** Bellman equation is: (A) Linear (B) Recursive (C) Random (D) Static
**Answer: (B)**

**Q8.** Value Iteration converges when: (A) 1 iteration (B) Values stop changing (C) All rewards equal (D) Policy random
**Answer: (B)**

**Q9.** DQN uses: (A) Decision trees (B) Neural networks (C) SVM (D) K-Means
**Answer: (B)**

**Q10.** Actor-Critic has: (A) Only actor (B) Only critic (C) Actor + Critic (D) Neither
**Answer: (C)**

---

## Part B: Short Answer (2 Marks)

**Q1.** List 5 components of MDP.
**Answer:** S (States), A (Actions), P (Transition probabilities), R (Reward function), γ (Discount factor).

**Q2.** Write Q-Learning update rule.
**Answer:** Q(s,a) ← Q(s,a) + α[R + γ max_a' Q(s',a') - Q(s,a)]

**Q3.** Differentiate SARSA and Q-Learning.
**Answer:** SARSA (on-policy) uses actual next action Q(s',a'). Q-Learning (off-policy) uses best possible max Q(s',a'). SARSA conservative, Q-Learning aggressive.

**Q4.** What is exploration vs exploitation dilemma?
**Answer:** Explore: try new actions (might find better reward). Exploit: use known best action (safe reward). Balance needed — ε-greedy, softmax, UCB, Thompson sampling are strategies.

---

## Part C: Descriptive (5 Marks)

**Q1.** Explain Reinforcement Learning with MDP and Bellman equations.

**Answer Structure:**
**Definition:** RL trains agent to select actions through environment interaction to maximize cumulative reward.
**Components:** Agent, Environment, State, Action, Reward, Policy.
**MDP:** (S,A,P,R,γ) — States, Actions, Transition probs, Rewards, Discount factor. Markov property: future depends only on current state.
**Bellman Equations:** Vπ(s) = Σπ(a|s)ΣP(s'|s,a)[R+γVπ(s')]. Recursive — current value = immediate + discounted future.
**Solution Methods:** Value Iteration, Policy Iteration, Q-Learning.
**Advantages:** Learns without explicit model, handles uncertainty, sequential decisions.
**Disadvantages:** Sample inefficient, reward design hard, convergence not guaranteed always.
**Challenges:** Exploration-exploitation balance, credit assignment, scalability.

**Q2.** Explain Q-Learning algorithm with update rule and exploration strategies.

**Answer Structure:**
**Definition:** Off-policy TD learning that learns optimal Q-values without following optimal policy.
**Update Rule:** Q(s,a) ← Q(s,a) + α[R + γmaxQ(s',a') - Q(s,a)].
**Components:** α=learning rate, R=reward, γ=discount, maxQ=future best.
**Tabular:** Q-values stored in table (states × actions).
**Exploration Strategies:** ε-greedy (random with prob ε), Softmax (probability ∝ Q), UCB (exploration bonus), Thompson (Bayesian).
**ε Decay:** Start high (explore more) → decrease over time → exploit more.
**Advantages:** Model-free, converges to optimal, simple to implement.
**Disadvantages:** Tabular doesn't scale, slow convergence, needs exploration tuning.
**Challenges:** Large state spaces, continuous actions, non-stationary environments.

---

*Practice makes perfect!* 🎯

## 🏆 ML SUBJECT — ALL 7 UNITS COMPLETE! 🏆
