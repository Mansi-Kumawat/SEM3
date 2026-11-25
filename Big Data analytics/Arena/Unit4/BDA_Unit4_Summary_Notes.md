# BDA – Unit 4: NoSQL, HBase & Hive
## Summary Notes | OLMCA606

---

## 1. Important Definitions

**NoSQL:** "Not Only SQL" — database systems not relying exclusively on the relational model. Uses flexible data models for distributed environments.

**Key-Value Database:** Stores data as key-value pairs. Fast lookups when key is known.

**Document Database:** Stores data as JSON-like documents. Flexible schema, nested objects.

**Column-Family Database:** Data organized in column groups. Designed for large-scale distributed storage. (HBase, Cassandra)

**Graph Database:** Uses nodes (entities) and edges (relationships). Best when relationships are central.

**HBase:** Distributed, scalable, column-family database on Hadoop/HDFS. Provides random read/write access using row keys.

**Hive:** Data warehouse system for Hadoop with SQL-like interface (HiveQL/HQL). For analytical batch workloads.

---

## 2. NoSQL Types

| Type | Structure | Use Case | Example |
|------|-----------|----------|---------|
| Key-Value | Key → Value | Session storage, caching | Redis |
| Document | JSON documents | Product catalog, CMS | MongoDB |
| Column-Family | Column groups | IoT, distributed data | HBase, Cassandra |
| Graph | Nodes + Edges | Social networks | Neo4j |

---

## 3. SQL vs NoSQL (7 Points)

| Feature | SQL | NoSQL |
|---------|-----|-------|
| Model | Relational (tables) | Multiple models |
| Schema | Fixed | Flexible |
| Scaling | Vertical | Horizontal |
| Joins | Strong | Minimized |
| Transactions | Strong ACID | Varies |
| Query | Standard SQL | Product-specific |
| Use | Transactions | Distributed data |

---

## 4. HBase

### Data Model
- **Row Key:** Unique row identifier
- **Column Family:** Groups related columns (defined at creation)
- **Column Qualifier:** Specific column name
- **Cell:** Individual value (Row Key + CF + CQ + Timestamp)
- **Versioning:** Multiple timestamps per cell

### Architecture
| Component | Role |
|-----------|------|
| HMaster | Admin — assigns regions, load balancing, recovery |
| RegionServer | Worker — handles read/write, MemStore + HFiles |
| Region | Row key range subset, distributed across servers |

### Advantages: Large-scale, random access, HDFS integration, sparse data
### Disadvantages: Complex joins hard, row-key design critical, complex admin

---

## 5. Hive

### Architecture Components
| Component | Role |
|-----------|------|
| User Interface | Accepts HQL (CLI, JDBC, ODBC) |
| Driver | Manages execution lifecycle |
| Compiler | Parses, semantic analysis, logical plan |
| Optimizer | Improves plan, partition pruning |
| Metastore | Metadata — tables, columns, types, locations |
| Execution Engine | Executes via MapReduce/Tez/Spark |

### Hive vs RDBMS
| Feature | RDBMS | Hive |
|---------|-------|------|
| Orientation | Transaction | Analytics |
| Latency | Low | High (batch) |
| Language | SQL | HQL |

---

## 6. HBase vs Hive

| Feature | HBase | Hive |
|---------|-------|------|
| Purpose | Random read/write | Analytical querying |
| Latency | Low | High |
| Best for | Real-time access | Batch analytics |
| Query | HBase API | HiveQL |

---

## 7. Last-Minute Revision

```
NOSQL = Not Only SQL, flexible, horizontal scaling
4 TYPES: KV(fast lookup), Document(JSON), Column-family(HBase), Graph(Neo4j)
SQL vs NoSQL: Fixed↔Flexible, Vertical↔Horizontal, ACID↔Varies

HBASE: Column-family, RowKey+CF+CQ+Timestamp=Cell
  HMaster(admin) → RegionServer(worker) → Regions(row ranges) → HDFS
  Low-latency random access

HIVE: Data warehouse, HiveQL
  UI → Driver → Compiler → Optimizer → Execution Engine
  Metastore = metadata, Engine = MapReduce/Tez/Spark
  Batch analytics, NOT real-time
```
