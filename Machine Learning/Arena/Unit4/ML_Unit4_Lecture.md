# ML Unit 4 — Advanced Supervised Learning
## Complete Lecture Notes (Hinglish) | OLMCA602 | Week 5 + Week 6

---

## 1. Neural Networks Kya Hain?

**Definition:**
> Neural Networks (NNs) are machine learning algorithms inspired by the structure and functioning of the human brain. They are composed of layers of interconnected nodes (neurons) that process data and learn patterns.

**Simple matlab:** Hamara brain neurons se bana hai — ek neuron signal leta hai, process karta hai, aur output deta hai. Neural Network bhi waise hi kaam karta hai — artificial neurons layers mein connected hote hain aur data se patterns seekhte hain.

**💡 Real Example:** Phone face recognition — pehle layers edges detect karti hain, middle layers eyes, nose, jawline combine karti hain, final layer decide karti hai — owner hai ya nahi!

### Four Building Blocks

| Block | Kya Hai | Matlab |
|-------|---------|--------|
| **Neurons** | Basic computing unit | Weighted sum + activation calculate karta hai |
| **Weights** | Learnable parameters | Training mein adjust hote hain — ye hi "learning" hai |
| **Layers** | Input → Hidden → Output | Data ka flow direction |
| **Activation Functions** | Non-linearity introduce karte hain | Decide karta hai neuron fire karega ya nahi |

---

## 2. Activation Functions — Bahut Important!

**Definition:**
> Functions that introduce non-linearity into the network, deciding whether a neuron should fire (activate) or not.

**💡 Kyun zaroori?** Bina activation function ke, neural network sirf linear combinations kar sakta hai — koi complex pattern nahi seekh sakta. Non-linearity hi usko powerful banati hai!

### 4 Types

| Function | Formula | Range | Kab Use Karein |
|----------|---------|-------|----------------|
| **Sigmoid** | σ(z) = 1/(1+e^(-z)) | 0 to 1 | Binary output layer |
| **Tanh** | tanh(z) | -1 to 1 | Hidden layers (zero-centered) |
| **ReLU** | max(0, z) | 0 to ∞ | **Most popular** for hidden layers |
| **Softmax** | e^zi / Σe^zj | 0 to 1 (sums to 1) | Multi-class output layer |

**💡 Learning Trick:** "ReLU hidden mein, Sigmoid binary mein, Softmax multi-class mein" — ye ek line mein yaad rakho!

**ReLU sabse popular kyun?**
- Vanishing gradient problem solve karta hai (Sigmoid mein gradient bahut chota ho jata tha deep networks mein)
- Computationally fast — sirf max(0, z) — koi expensive operation nahi
- Sparse activation — negative inputs ko 0 kar deta hai

---

## 3. Feedforward Neural Network

**Definition:**
> The simplest neural network architecture where data flows in one direction — from input layer through hidden layers to output layer. No loops, no cycles.

**Kaise kaam karta hai:**

**Step 1:** Weighted sum compute karo
```
z = w₁x₁ + w₂x₂ + ... + wₙxₙ + bias
```

**Step 2:** Activation function apply karo
```
a = f(z)   (e.g., ReLU, Sigmoid)
```

**Step 3:** Output prediction ŷ

**Step 4:** Loss compute karo — ŷ aur actual y ke beech

**💡 Key Point:** No feedback loops — data sirf aage ja raha hai. Isliye "feedforward" kehte hain. Jaise paani pipe mein ek direction mein beh raha hai.

---

## 4. Backpropagation — Network Kaise Seekhta Hai?

**Definition:**
> Backpropagation computes the gradient of the loss function with respect to each weight by propagating the error backward through the network — enabling the network to learn from its mistakes.

**Real example:** Socho student ne exam mein galat answer diya. Teacher ne bataya kahan galti hui. Student ne apni understanding adjust ki. Next baar better karega. Yahi backpropagation karta hai — loss batata hai kahan galti hui, gradients batate hain kitna adjust karna hai.

### 4 Steps

| Step | Action | Simple Matlab |
|------|--------|---------------|
| **1** | **Forward Pass** | Input se output ŷ compute karo |
| **2** | **Compute Loss** | L(ŷ, y) — prediction aur actual ka difference |
| **3** | **Backward Pass** | Chain rule se har weight ka gradient nikalo: ∂L/∂w |
| **4** | **Update Weights** | w = w - α × gradient |

### Update Rule — Formula RAT LO!
```
w_new = w_old - α × (∂L/∂w)
```

**💡 Chain Rule:** Ye backpropagation ka mathematical engine hai. Har layer ka gradient pichle layer ke gradient se calculate hota hai — peeche se aage tak propagate hota hai.

---

## 5. Backpropagation — Numerical Example (Exam Important!)

**Network:** 2 inputs (x₁=1, x₂=0), 1 hidden neuron, 1 output neuron
**Weights:** w₁=0.5, w₂=0.3, bias=0.1, target y=1, learning rate α=0.1

### Step 1: Forward Pass
```
z = w₁x₁ + w₂x₂ + bias = 0.5(1) + 0.3(0) + 0.1 = 0.6
ŷ = sigmoid(0.6) = 1/(1+e^(-0.6)) = 0.646
```

### Step 2: Compute Loss
```
L = 0.5 × (y - ŷ)² = 0.5 × (1 - 0.646)² = 0.5 × 0.125 = 0.063
```

### Step 3: Backward Pass (Chain Rule)
```
∂L/∂w₁ = (ŷ - y) × sigmoid'(z) × x₁
       = (0.646 - 1) × 0.646×(1-0.646) × 1
       = -0.354 × 0.229 = -0.081
```

### Step 4: Update Weight
```
w₁_new = 0.5 - 0.1 × (-0.081) = 0.5 + 0.0081 = 0.5081
```

**💡 Ek iteration ho gaya!** Aise hazaron iterations ke baad network achha predict karne lagta hai.

---

## 6. Support Vector Machines (SVM)

**Definition:**
> SVM is a powerful supervised learning algorithm that finds the optimal hyperplane with maximum margin between classes.

**💡 Best Example:** Do housing colonies ke beech road banana hai. Road dono colonies se jitna door ho utna achha — truck safely nikal sake. Road = hyperplane, Road ki width = margin, Nearest ghar = support vectors.

### 5 Key Concepts

| Concept | Kya Hai | Simple Matlab |
|---------|---------|---------------|
| **Hyperplane** | Decision boundary | 2D mein line, 3D mein plane |
| **Margin** | Distance between hyperplane and nearest points | Road ki width — jitni badi utni achhi |
| **Support Vectors** | Nearest data points to hyperplane | Sirf ye boundary decide karte hain! |
| **Hard Margin** | No misclassification allowed | Linearly separable data chahiye |
| **Soft Margin** | Allows some errors using slack variables | Real-world noisy data ke liye better |

---

## 7. SVM Optimization Problem

**Goal:**
```
Minimize: ||w||² / 2
Subject to: yᵢ(w·xᵢ + b) ≥ 1   for all i
```

**Matlab:** w aur b find karo jo:
- Margin maximize kare (||w|| minimize kare)
- Aur sab points correctly classify kare (constraint satisfy ho)

**💡 Support Vectors kyun important?** Sirf support vectors hi optimization ko affect karte hain. Door ke points ka gradient zero hota hai — unka koi role nahi boundary mein!

---

## 8. Kernel Trick — SVM ka Superpower

**Problem:** Jab data linearly separable nahi — seedhi line se alag nahi kar sakte.

**Solution:** Kernel trick data ko higher dimension mein map karta hai jahan wo separable ho jaata hai — **bina explicitly transform kiye!**

**Formula:**
```
K(xᵢ, xⱼ) = φ(xᵢ) · φ(xⱼ)
```

Matlab high-dimension mein dot product directly compute karo — pehle map karne ki zaroorat nahi!

**💡 Example:** 2D mein red-blue dots circle pattern mein hain — koi straight line nahi jo separate kar sake. Kernel trick se 3D mein transform — ab ek plane easily separate kar deta hai!

---

## 9. Kernel Functions — 4 Types

### Linear Kernel
```
K(x,y) = x · y
```
- Koi transformation nahi — simple dot product
- Use jab data already separable ho

### Polynomial Kernel
```
K(x,y) = (γx·y + r)^d
```
- d = degree of polynomial
- Feature interactions capture karta hai up to degree d

### RBF (Gaussian) Kernel — MOST POPULAR!
```
K(x,y) = exp(-γ||x-y||²)
```
- Sabse popular — most cases mein kaam karta hai
- γ controls influence radius — chota γ = wide influence

### Sigmoid Kernel
```
K(x,y) = tanh(γx·y + r)
```
- Neural network activation jaisa
- Less commonly used

**💡 Exam tip:** "RBF most popular kernel hai" — ye direct MCQ aata hai!

---

## 10. One-Class Kernel SVM — Anomaly Detection

**Definition:** Learns what "normal" data looks like, then detects anomalies — points far from normal.

**Kaise kaam karta hai:**
1. Sirf **normal data** se training karo
2. High-dimensional space mein smallest sphere/hyperplane find karo jo normal data enclose kare
3. Naya point aaye → Sphere ke andar = Normal, Bahar = **Anomaly!**

### Applications
| Domain | Use |
|--------|-----|
| **Fraud Detection** | Normal transactions seekho, unusual flag karo |
| **Network Security** | Normal traffic pattern, intrusion detect karo |
| **Medical** | Normal cells, abnormal cells dhundho |
| **Manufacturing** | Normal products, defects detect karo |

---

## 11. Neural Networks vs SVM — Comparison

| Aspect | Neural Networks | SVM |
|--------|----------------|-----|
| **Inspiration** | Human brain | Maximum margin geometry |
| **Architecture** | Layers of neurons | Hyperplane + Support vectors |
| **Data needed** | Lots of data | Works with less data |
| **Computation** | Heavy (GPU often needed) | Moderate |
| **Best for** | Images, text, speech, deep learning | Text, bioinformatics, smaller datasets |
| **Training** | Backpropagation + GD | Quadratic optimization |
| **Non-linearity** | Via activation functions | Via kernel trick |
| **Interpretability** | Low (black box) | Moderate |

---

## 12. Exam-Ready Recap

### Must-Remember Formulas
```
Sigmoid:     σ(z) = 1/(1+e^-z)
ReLU:        max(0, z)
BP Update:   w = w - α × ∂L/∂w
SVM:         Minimize ||w||²/2, s.t. yᵢ(w·xᵢ+b) ≥ 1
RBF Kernel:  K(x,y) = exp(-γ||x-y||²)
```

### 5-Mark Answer Structure
**Definition → Types/Components → Features → Advantages → Disadvantages → Challenges**

### Common Exam Questions
- Neural Network components + activation functions
- Backpropagation numerical example (step by step)
- SVM optimization problem + support vectors explain
- Kernel trick — why needed, how it works
- Kernel types with formulas
- NN vs SVM comparison
- One-Class SVM for anomaly detection

---

*End of Unit 4 — Advanced Supervised Learning* 🎯
