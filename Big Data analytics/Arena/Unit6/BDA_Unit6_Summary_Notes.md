# BDA – Unit 6: Streaming Data & Cassandra
## Summary Notes | OLMCA606

---

## 1. Important Definitions

**Streaming Data:** Continuously generated records arriving over time (sensors, transactions, logs).

**Cassandra:** Open-source distributed NoSQL database for high availability and large-scale workloads.

**CQL:** Cassandra Query Language — SQL-like syntax for distributed data model.

**Replication Factor (RF):** Number of replicas for each partition.

**Consistency Level:** How many replicas must respond (ONE, QUORUM, ALL).

**SSTable:** Immutable on-disk storage file in Cassandra.

**Memtable:** In-memory structure holding recent writes before flush to SSTable.

**Bloom Filter:** Probabilistic structure to quickly check if key exists in SSTable.

**Keyspace:** Top-level namespace in Cassandra (like database in RDBMS).

---

## 2. Streaming Data Pipeline

```
Source → Ingestion → Processing → Storage → Analytics → Action
```
Tools: Kafka (ingestion), Flink (processing), Cassandra (storage)

### Batch vs Stream
| Feature | Batch | Stream |
|---------|-------|--------|
| Data | Accumulated | Arriving events |
| Timing | Scheduled | Continuous |
| Use | Reports | Alerts |

---

## 3. Cassandra Architecture

### Node Components
| Component | Role |
|-----------|------|
| Commit Log | Recovery records |
| Memtable | In-memory writes |
| SSTable | On-disk immutable files |
| Bloom Filter | Fast key lookup |
| Compaction | Merge SSTables |

**Write Path:** Write → Commit Log → Memtable → SSTable

---

## 4. Replication & Consistency

| RF | Copies | Storage (100GB data) |
|----|--------|---------------------|
| 1 | 1 | ~100 GB |
| 2 | 2 | ~200 GB |
| 3 | 3 | ~300 GB |

| Consistency | Requirement |
|-------------|-------------|
| ONE | 1 replica |
| QUORUM | Majority |
| ALL | All replicas |

**Strategies:** SimpleStrategy (single DC), NetworkTopologyStrategy (multi-DC)

---

## 5. CQL Commands

```sql
CREATE KEYSPACE ks WITH replication = {'class':'SimpleStrategy','replication_factor':3};
CREATE TABLE t (id int PRIMARY KEY, name text, val double);
INSERT INTO t (id,name,val) VALUES (1,'Ravi',8.5);
SELECT name,val FROM t WHERE id=1;
UPDATE t SET val=9.0 WHERE id=1;
DELETE FROM t WHERE id=1;
```

---

## 6. Collections

| Type | Feature | Example |
|------|---------|---------|
| Set | Unique, unordered | `set<text>` |
| List | Ordered, indexed | `list<int>` |
| Map | Key-value | `map<text,text>` |

---

## 7. Last-Minute Revision

```
Streaming: continuous, pipeline (6 stages), Kafka+Flink+Cassandra
Cassandra: distributed NoSQL, peer-to-peer, CQL
Node: Commit Log→Memtable→SSTable, Bloom Filter
RF: copies count, Simple/NetworkTopology strategy
Consistency: ONE/QUORUM/ALL
CQL: CREATE KEYSPACE/TABLE, INSERT/SELECT/UPDATE/DELETE
Collections: Set(unique), List(ordered), Map(k-v)
```
