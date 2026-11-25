# ML Unit 4 — Quick Summary Notes
## Advanced Supervised Learning | One-Page Revision

---

### 🔑 Key Definitions

| Term | Definition |
|------|-----------|
| **Neural Network** | Brain-inspired algorithm with layers of neurons learning patterns |
| **Activation Function** | Introduces non-linearity — decides if neuron fires |
| **Backpropagation** | Computes gradients by propagating error backward |
| **SVM** | Finds optimal hyperplane with maximum margin |
| **Support Vectors** | Nearest points that define the decision boundary |
| **Kernel Trick** | Maps data to higher dimension without explicit transform |
| **One-Class SVM** | Learns "normal" to detect anomalies |

---

### 📊 Activation Functions
| Sigmoid (0,1, binary) | Tanh (-1,1, zero-centered) | ReLU (hidden layers, popular) | Softmax (multi-class) |

**💡 Trick:** "ReLU hidden mein, Sigmoid binary mein, Softmax multi-class mein"

---

### 📊 Backpropagation — 4 Steps
Forward Pass → Compute Loss → Backward Pass (Chain Rule) → Update Weights
**Formula:** w = w - α × ∂L/∂w

---

### 📊 SVM — 5 Key Concepts
Hyperplane | Margin | Support Vectors | Hard Margin | Soft Margin

---

### 📊 Kernel Functions
| Linear (x·y) | Polynomial ((γx·y+r)^d) | RBF (exp(-γ‖x-y‖²), most popular!) | Sigmoid (tanh) |

---

### 📐 All Formulas (RAT LO!)
```
Sigmoid:     σ(z) = 1/(1+e^-z)
BP Update:   w = w - α × ∂L/∂w
SVM:         Min ||w||²/2, s.t. yᵢ(w·xᵢ+b) ≥ 1
RBF:         K(x,y) = exp(-γ||x-y||²)
```

---

### ⚡ Last-Minute Recap
1. NN: Neurons + Weights + Layers + Activation Functions
2. Activation: Sigmoid, Tanh, ReLU (popular!), Softmax
3. Feedforward: One direction flow, no loops
4. Backprop: Chain rule → gradients → weight update
5. SVM: Maximum margin hyperplane
6. Support Vectors: Only they matter!
7. Kernel Trick: Higher dim, no explicit mapping
8. RBF = most popular kernel
9. One-Class SVM = anomaly detection

---

*Quick revision complete!* 🎯
