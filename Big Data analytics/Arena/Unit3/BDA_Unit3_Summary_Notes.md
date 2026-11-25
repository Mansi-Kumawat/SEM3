# BDA – Unit 3: MapReduce Programming
## Summary Notes | OLMCA606

---

## 1. Important Definitions

**MapReduce:** A distributed programming model for processing very large datasets in parallel. It divides computation into Map and Reduce stages, processing data across multiple machines using key-value pairs.

**Mapper:** Processes input key-value pairs and emits intermediate key-value pairs by applying user-defined logic. Multiple mappers run in parallel.

**Reducer:** Receives grouped key-value pairs (same key together) and applies aggregation/transformation to produce final output.

**Combiner:** An optional "mini-reducer" that performs local aggregation of Mapper output to reduce network traffic during Shuffle.

**Partitioner:** Determines which Reducer receives each Mapper output record. Default: HashPartitioner using `partition = hash(key) % num_reducers`.

**Shuffle:** The phase that transfers Mapper output to appropriate Reducers, grouping by key.

**YARN (Yet Another Resource Negotiator):** The resource management layer of Hadoop 2.x. Separates resource management from data processing, allowing multiple frameworks to share a cluster.

**JobTracker (Classic):** Single daemon handling both scheduling and resource management (bottleneck in Hadoop 1.x).

**TaskTracker (Classic):** Worker daemon executing tasks on each node (Hadoop 1.x).

**Input Split:** Logical division of input data. Each Mapper processes one split. Generally aligned with HDFS block size.

---

## 2. MapReduce Architecture & Phases

```
HDFS → Input Splits → Map (parallel) → Shuffle & Sort → Reduce (parallel) → HDFS
```

| Phase | Description | Example |
|-------|-------------|---------|
| **1. Input** | Large file from HDFS | 512 MB log file |
| **2. Split** | File divided into logical splits (≈block size) | 512 MB → 4 splits of 128 MB |
| **3. Map** | Each Mapper processes one split, emits <key,value> | (word, 1) for each word |
| **4. Shuffle & Sort** | Groups by key, transfers to Reducers | Hadoop→[1,1], Spark→[1] |
| **5. Reduce** | Aggregates grouped values | Hadoop→2, Spark→1 |
| **6. Output** | Final result written to HDFS | Output files |

---

## 3. Combiner vs Partitioner

| Feature | Combiner | Partitioner |
|---------|----------|-------------|
| **Role** | Local aggregation of Mapper output | Routes data to specific Reducer |
| **When** | After Mapper, before Shuffle | During Shuffle phase |
| **Optional?** | Yes | No (default: HashPartitioner) |
| **Formula** | N/A | `hash(key) % num_reducers` |
| **Benefit** | Reduces network traffic | Ensures same key → same Reducer |
| **Example** | Hadoop→1,1,1 becomes Hadoop→3 | India→Reducer 1, USA→Reducer 2 |

**When to use Combiner:** Only for associative and commutative operations (sum, count, max, min).

---

## 4. YARN Architecture

### Components

| Component | Role |
|-----------|------|
| **ResourceManager** | Master — global resource management |
| ↳ Scheduler | Allocates resources based on policies (FIFO, Capacity, Fair) |
| ↳ ApplicationsManager | Handles app submission, starts AppMaster |
| **NodeManager** | Per worker node — manages local resources and containers |
| **ApplicationMaster** | Per application — negotiates resources, coordinates tasks |
| **Container** | Resource bundle (CPU + memory) where tasks execute |

### Classic vs YARN

| Feature | Classic (1.x) | YARN (2.x+) |
|---------|---------------|-------------|
| Resource Mgmt | JobTracker | ResourceManager |
| Scheduling | JobTracker | Scheduler |
| Worker | TaskTracker | NodeManager |
| Per-app coord | None | ApplicationMaster |
| Multi-framework | No | Yes (Spark, Hive, etc.) |
| Scalability | Limited | High |

---

## 5. MapReduce Daemons

| Daemon | Framework | Role |
|--------|-----------|------|
| **JobTracker** | Classic | Master — scheduling + resource mgmt (single point of failure) |
| **TaskTracker** | Classic | Worker — executes map/reduce tasks |
| **ResourceManager** | YARN | Global resource allocation |
| **NodeManager** | YARN | Per-node container management |
| **ApplicationMaster** | YARN | Per-app resource negotiation |

---

## 6. Word Count Example (Step by Step)

```
Input: "Hadoop Hadoop Spark"

Map:    (Hadoop,1) (Hadoop,1) (Spark,1)

Shuffle: Hadoop → [1,1]    Spark → [1]

Reduce:  Hadoop → 2        Spark → 1

Output:  Hadoop  2
         Spark   1
```

---

## 7. Matrix Multiplication using MapReduce

**Formula:** C[i][j] = Σ A[i][k] × B[k][j]

**Input format:** Matrix,Row,Col,Value
- A,0,0,1  A,0,1,2  A,1,0,3  A,1,1,4
- B,0,0,5  B,0,1,6  B,1,0,7  B,1,1,8

**Map:** For each element A[i][k] and B[k][j], emit partial product with key (i,j)

**Reduce:** Sum all partial products for each (i,j)

**Result:** C = [19,22; 43,50]

| Cell | Calculation | Result |
|------|-------------|--------|
| C[0][0] | (1×5) + (2×7) = 5+14 | **19** |
| C[0][1] | (1×6) + (2×8) = 6+16 | **22** |
| C[1][0] | (3×5) + (4×7) = 15+28 | **43** |
| C[1][1] | (3×6) + (4×8) = 18+32 | **50** |

---

## 8. PageRank Algorithm

**Formula:** PR(A) = (1-d)/N + d × Σ PR(Ti)/C(Ti)

- **d** = damping factor = 0.85 (85% follow links, 15% random jump)
- **N** = total number of pages
- **Ti** = pages linking to A
- **C(Ti)** = outgoing links from Ti
- **Teleport** = (1-d)/N = baseline rank every page gets

**MapReduce Implementation:**
- **Mapper:** Divides page's rank among outgoing links, preserves adjacency list
- **Reducer:** Sums incoming contributions, applies formula for new rank
- **Iterates** until convergence (|PR_new - PR_old| < ε)

---

## 9. SQL Join using MapReduce

**Approach:** Tagged records with join key

- **Map:** Emit (join_key, tagged_record) — tag as EMP or DEPT
- **Shuffle:** Group by join key
- **Reduce:** Match EMP and DEPT records, produce joined output

| Join Type | Result |
|-----------|--------|
| INNER JOIN | Only matching records |
| LEFT OUTER JOIN | All left records + matching right (NULL if no match) |

---

## 10. Last-Minute Revision

```
MAPREDUCE PHASES: Input → Split → Map → Shuffle&Sort → Reduce → Output

COMBINER: Mini-reducer, local aggregation, optional, reduces network traffic
PARTITIONER: hash(key) % n, routes data to reducers

YARN: RM(Scheduler+AppMgr) → NM → AppMaster → Containers
Classic: JobTracker + TaskTracker (coupled, bottleneck)

WORD COUNT: Map(word,1) → Shuffle → Reduce(sum)
MATRIX: Partial products by k, sum for C[i][j]
PAGERANK: PR = (1-d)/N + d*sum(PR/C), iterative, d=0.85
SQL JOIN: Tagged records, group by key, match in reducer
```

---

## 11. Common Mistakes

| Mistake | Correct |
|---------|---------|
| "Combiner = Reducer" | Combiner is optional local aggregation; Reducer is required global |
| "Partitioner runs after Reducer" | Partitioner runs BEFORE/during Shuffle |
| "YARN = MapReduce" | YARN is resource mgmt; MapReduce is processing |
| "JobTracker in YARN" | JobTracker is Classic only; YARN uses ResourceManager |
| "PageRank = 1 pass" | PageRank is iterative, converges over multiple iterations |
