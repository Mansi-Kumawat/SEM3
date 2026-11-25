# BDA – Unit 3: MapReduce Programming
## Complete Lecture Notes | OLMCA606

---

## 📋 Topics Covered (Week 3 + Week 4)

1. Introduction to MapReduce
2. MapReduce Phases (Input, Split, Map, Shuffle, Sort, Reduce, Output)
3. Combiner
4. Partitioner
5. Classic Framework vs YARN
6. MapReduce Daemons
7. Word Count Example
8. PageRank Algorithm using MapReduce
9. Matrix Multiplication using MapReduce
10. SQL Join using MapReduce

---

## 📖 1. Introduction to MapReduce

### Official Definition

> **MapReduce** is a distributed programming model designed to process very large datasets across multiple machines. It divides computation into Map, Shuffle and Sort, and Reduce stages. Processing tasks execute in parallel, improving the throughput of large-scale batch jobs.

### Hinglish Explanation

MapReduce basically ek programming model hai jo bahut bade data ko chhote tasks mein tod kar parallel process karta hai. Originally Google ne banaya tha large-scale data processing ke liye. Hadoop mein iska open-source implementation hai. Input key-value pairs mein hota hai — Mapper har pair ko process karta hai aur intermediate pairs emit karta hai — framework unhe group by key karta hai — aur Reducer final output produce karta hai.

---

## 📖 2. MapReduce Phases

### The 6 Phases

```
Input → Split → Map → Shuffle & Sort → Reduce → Output
```

| Phase | Description | Example |
|-------|-------------|---------|
| **1. Input** | Large file from HDFS | 512 MB web log data |
| **2. Split** | File divided into logical splits (≈block size) | 512 MB → 4 splits of 128 MB → 4 Mappers |
| **3. Map** | Each Mapper processes one split, emits <key,value> | (Hadoop,1), (Spark,1) |
| **4. Shuffle & Sort** | Groups by key, transfers to Reducers | Hadoop→[1,1], Spark→[1] |
| **5. Reduce** | Aggregates grouped values | Hadoop→2, Spark→1 |
| **6. Output** | Final result written to HDFS | Output files |

### Input Splitting
- Large files divided into logical input splits
- Splits generally aligned with HDFS blocks
- Each Mapper processes one split
- Multiple splits → parallel processing → enables parallelism

### Mapper Stage
- Receives <key, value> pairs
- Applies user-defined logic
- Generates intermediate key-value pairs
- Multiple Mappers run in parallel
- Output stored locally before Shuffle

---

## 📖 3. Combiner

### Official Definition

> **Combiner** performs local aggregation of Mapper output on the same node. It reduces the amount of intermediate data transferred across the network during the Shuffle phase. It is sometimes called a "mini-reducer."

### Key Points
- **Optional** — not required
- Executes after Mapper, before Shuffle
- Reduces network traffic, disk I/O, and Shuffle workload
- Runs locally on the Mapper node
- May execute zero, one, or multiple times
- Should only be used for **associative and commutative** operations (sum, count, max, min)

### Example
- Without Combiner: Hadoop→1, Hadoop→1, Hadoop→1 (3 records transferred)
- With Combiner: Hadoop→3 (1 record transferred)
- Real scale: 10 million Mapper records → 1 million after Combiner

### Combiner vs Reducer

| Feature | Combiner | Reducer |
|---------|----------|---------|
| Scope | Local (per Mapper node) | Distributed (across cluster) |
| Optional? | Yes | No |
| When | After Mapper, before Shuffle | After Shuffle |
| Output | Intermediate | Final |
| Execution | May run multiple times | Runs as per reducer tasks |

---

## 📖 4. Partitioner

### Official Definition

> **Partitioner** determines which Reducer receives each Mapper output record. It operates on intermediate key-value pairs. The same key must go to the same Reducer. Default implementation is HashPartitioner.

### Formula
```
partition = hash(key) % number_of_reducers
```

### Example
- 3 Reducers, Key = "Hadoop"
- hash("Hadoop") % 3 = 1 → goes to Reducer 1

### Custom Partitioner
- User can create custom Partitioner for business logic
- Extends Hadoop's Partitioner class
- Can partition by: Country, Department, Region, Product category, Customer type

### Example with Sales Data
- India,1000 → hash("India") % 3 = 1 → Reducer 1
- USA,2500 → hash("USA") % 3 = 2 → Reducer 2
- India,1500 → hash("India") % 3 = 1 → Reducer 1 (same as above!)

---

## 📖 5. Shuffle & Sort

### Shuffle
- Transfers Mapper output to appropriate Reducers
- Mapper output is partitioned
- Each Reducer retrieves its partition
- Data may travel across network
- Critical for performance

### Sorting
- Intermediate keys sorted before reaching Reducer
- Same-key records grouped together
- Makes reduction easier
- Hadoop performs sorting automatically

---

## 📖 6. Reducer Stage

- Receives grouped key-value pairs
- Applies aggregation or transformation logic
- Each key processed with its associated values
- Produces final output
- Multiple Reducers execute in parallel

---

## 📖 7. Classic Framework vs YARN

### Classic MapReduce (Hadoop 1.x)
- **JobTracker:** Master daemon — handles BOTH scheduling AND resource management (single point of failure, bottleneck)
- **TaskTracker:** Worker daemon — executes tasks on each node

### YARN (Hadoop 2.x+)
- Separates resource management from processing
- Multiple frameworks can share same cluster

| Component | Role |
|-----------|------|
| **ResourceManager** | Master — global resource management (Scheduler + ApplicationsManager) |
| **NodeManager** | Per worker node — manages local resources and containers |
| **ApplicationMaster** | Per application — negotiates resources, coordinates tasks |
| **Container** | Resource bundle (CPU + memory) where tasks execute |

### Classic vs YARN Comparison

| Feature | Classic | YARN |
|---------|---------|------|
| Resource Mgmt | JobTracker | ResourceManager |
| Scheduling | JobTracker | Scheduler |
| Worker | TaskTracker | NodeManager |
| Per-app coord | None | ApplicationMaster |
| Multi-framework | No | Yes |
| Scalability | Limited | High |

---

## 📖 8. MapReduce Daemons

| Daemon | Framework | Role |
|--------|-----------|------|
| **JobTracker** | Classic | Master — scheduling + resource mgmt (bottleneck) |
| **TaskTracker** | Classic | Worker — executes map/reduce tasks |
| **ResourceManager** | YARN | Global resource allocation |
| ↳ Scheduler | YARN | Allocates resources (FIFO, Capacity, Fair) |
| ↳ ApplicationsManager | YARN | Handles app submission, starts AppMaster |
| **NodeManager** | YARN | Per-node container management |
| **ApplicationMaster** | YARN | Per-app resource negotiation |

---

## 📖 9. Word Count Example

### Step by Step

```
Input: "Hadoop Hadoop Spark"

MAP (per word):
  (Hadoop, 1)
  (Hadoop, 1)
  (Spark,  1)

SHUFFLE & SORT (group by key):
  Hadoop → [1, 1]
  Spark  → [1]

REDUCE (sum values):
  Hadoop → 2
  Spark  → 1

OUTPUT:
  Hadoop  2
  Spark   1
```

---

## 📖 10. PageRank Algorithm (Week 4)

### Concept
- Algorithm behind early Google Search (Larry Page & Sergey Brin, 1998)
- A page is important if important pages link to it
- Recursive — computed iteratively, not in one pass

### Formula
```
PR(A) = (1-d)/N + d × Σ PR(Ti)/C(Ti)
```

| Variable | Meaning |
|----------|---------|
| d | Damping factor = 0.85 (85% follow links, 15% random jump) |
| N | Total number of pages |
| Ti | Pages linking to page A |
| C(Ti) | Number of outgoing links from Ti |

### Teleport
- (1-d)/N = baseline rank every page gets from random surfer
- Guarantees minimum rank for every page

### Example: 3 Pages (A→B,C; B→C; C→A)
- Initial: PR(A)=PR(B)=PR(C) = 1/3 = 0.333

**Iteration 1:**
| Page | Contributions | New Rank = 0.05 + 0.85×sum |
|------|--------------|---------------------------|
| A | 0.33 (from C) | 0.05 + 0.85×0.33 = 0.33 |
| B | 0.165 (from A) | 0.05 + 0.85×0.165 = 0.19 |
| C | 0.165+0.33 (from A,B) | 0.05 + 0.85×0.495 = 0.475 |

### MapReduce Implementation
- **Mapper:** Divides page rank among outgoing links, emits adjacency list + rank contributions
- **Shuffle:** Groups by target page
- **Reducer:** Sums contributions, applies formula
- **Iterates** until convergence: |PR_new - PR_old| < ε (e.g., 0.0001)

---

## 📖 11. Matrix Multiplication using MapReduce

### Formula
```
C[i][j] = Σ A[i][k] × B[k][j]
```
For A(m×n) × B(n×p) = C(m×p)

### Input Format
Each element stored as: `Matrix,Row,Col,Value`
- A,0,0,1  A,0,1,2  A,1,0,3  A,1,1,4
- B,0,0,5  B,0,1,6  B,1,0,7  B,1,1,8

### Example: 2×2 matrices
```
A = [1, 2]    B = [5, 6]
    [3, 4]        [7, 8]

C = A × B = [19, 22]
            [43, 50]
```

### MapReduce Strategy
**Mapper:** For each A[i][k] and B[k][j], emit partial product with key (i,j)

**Phase 1 Reduce (grouped by k):**
| k | Partial Products |
|---|-----------------|
| k=0 | (0,0)=1×5=5, (0,1)=1×6=6, (1,0)=3×5=15, (1,1)=3×6=18 |
| k=1 | (0,0)=2×7=14, (0,1)=2×8=16, (1,0)=4×7=28, (1,1)=4×8=32 |

**Phase 2 Reduce (sum partial products):**
| Cell | Sum | Final |
|------|-----|-------|
| C[0][0] | 5 + 14 | **19** |
| C[0][1] | 6 + 16 | **22** |
| C[1][0] | 15 + 28 | **43** |
| C[1][1] | 18 + 32 | **50** |

---

## 📖 12. SQL Join using MapReduce

### Concept
JOIN combines records from two tables using a common attribute.

### Example Tables
- **Employees:** (1,Alice,10), (2,Bob,20), (3,Carol,10), (4,Dan,99)
- **Departments:** (10,Engineering), (20,Sales)

### MapReduce Implementation

**Map:** Tagged records with DeptID as key
| Key | Value |
|-----|-------|
| 10 | ("EMP", Alice) |
| 20 | ("EMP", Bob) |
| 10 | ("EMP", Carol) |
| 99 | ("EMP", Dan) |
| 10 | ("DEPT", Engineering) |
| 20 | ("DEPT", Sales) |

**Shuffle:** Group by DeptID
| Key | Values |
|-----|--------|
| 10 | EMP(Alice), EMP(Carol), DEPT(Engineering) |
| 20 | EMP(Bob), DEPT(Sales) |
| 99 | EMP(Dan) — no DEPT match |

**Reduce Output:**
| Join Type | Result |
|-----------|--------|
| INNER JOIN | (Alice,10,Eng), (Carol,10,Eng), (Bob,20,Sales) |
| LEFT OUTER | + (Dan,99,NULL) — Dan kept without match |

---

## 🎯 EXAMINATION PERSPECTIVE

### Important Definitions
1. MapReduce, Mapper, Reducer, Combiner, Partitioner
2. YARN, ResourceManager, NodeManager, ApplicationMaster, Container
3. Input Split, Shuffle, JobTracker, TaskTracker

### Formulas
- Partitioner: `hash(key) % num_reducers`
- PageRank: `PR(A) = (1-d)/N + d × Σ PR(Ti)/C(Ti)`, d=0.85
- Matrix: `C[i][j] = Σ A[i][k] × B[k][j]`

### Potential 5-Mark Questions
1. Explain 6 phases of MapReduce with example
2. YARN architecture vs Classic framework
3. Word Count with key-value pairs at each phase
4. Matrix Multiplication using MapReduce (2×2 example)
5. SQL Join using MapReduce (INNER + LEFT OUTER)
6. PageRank algorithm with MapReduce implementation
