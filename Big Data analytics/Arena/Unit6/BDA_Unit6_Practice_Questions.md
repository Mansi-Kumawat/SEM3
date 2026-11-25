# BDA – Unit 6: Practice Questions & Active Recall Quiz

---

## Part A: 1-Mark MCQs

**Q1.** Streaming data differs from batch data because it:
- (A) Is collected as a complete dataset  (B) Arrives continuously over time
- (C) Is always structured  (D) Requires no processing

**Q2.** Which tool is commonly used for event transport in streaming pipelines?
- (A) Cassandra  (B) Apache Kafka  (C) HBase  (D) Hive

**Q3.** In Cassandra, which component records mutations for recovery?
- (A) Memtable  (B) SSTable  (C) Commit Log  (D) Bloom Filter

**Q4.** A Replication Factor of 3 means:
- (A) 3 nodes in cluster  (B) 3 copies of each partition  (C) 3 keyspaces  (D) 3 data centers

**Q5.** Which consistency level requires majority replicas to respond?
- (A) ONE  (B) ALL  (C) QUORUM  (D) ANY

**Q6.** CQL stands for:
- (A) Cassandra Query Language  (B) Common Query Language
- (C) Cluster Query Logic  (D) Column Query Language

**Q7.** Which Cassandra collection type stores unique unordered values?
- (A) List  (B) Map  (C) Set  (D) Array

**Q8.** SSTable in Cassandra is:
- (A) Mutable  (B) Immutable  (C) Temporary  (D) In-memory only

**Q9.** Which replication strategy is recommended for production?
- (A) SimpleStrategy  (B) NetworkTopologyStrategy  (C) RandomStrategy  (D) DefaultStrategy

**Q10.** The Bloom Filter in Cassandra is used to:
- (A) Store data permanently  (B) Identify SSTables unlikely to contain a key
- (C) Manage compaction  (D) Handle replication

---

## Part B: 2-Mark Questions

**Q11.** Differentiate between Batch Processing and Stream Processing.

**Q12.** What is the difference between Memtable and SSTable in Cassandra?

**Q13.** Explain Replication Factor with the storage overhead formula.

**Q14.** What is the difference between ONE, QUORUM, and ALL consistency levels?

**Q15.** Differentiate between SimpleStrategy and NetworkTopologyStrategy.

---

## Part C: 5-Mark Descriptive Questions

**Q16.** Explain streaming data and its 6-stage processing pipeline with examples.

**Q17.** Describe Cassandra architecture with node components and write path.

**Q18.** Explain replication factor, consistency levels, and replication strategies in Cassandra.

**Q19.** Write CQL commands for creating keyspace, table, inserting data, and querying.

**Q20.** Explain collections in Cassandra (Set, List, Map) with CQL examples.

---

## 📝 ANSWER KEY

### Part A
1. (B) Arrives continuously  2. (B) Apache Kafka  3. (C) Commit Log  4. (B) 3 copies
5. (C) QUORUM  6. (A) Cassandra Query Language  7. (C) Set  8. (B) Immutable
9. (B) NetworkTopologyStrategy  10. (B) Identify SSTables unlikely to contain a key

### Part B — Model Answers

**Q11. Batch vs Stream:**
- Batch: accumulated data, scheduled, historical reports (monthly sales).
- Stream: arriving events, continuous, immediate alerts (fraud detection).

**Q12. Memtable vs SSTable:**
- Memtable: in-memory, holds recent writes, mutable.
- SSTable: on-disk, immutable, created when memtable is flushed.

**Q13. Replication Factor:**
RF = number of copies of each partition. Storage overhead = Logical data size × RF. RF=3 for 100GB = ~300GB.

**Q14. Consistency Levels:**
- ONE: 1 replica responds (fastest, least consistent)
- QUORUM: majority respond (balanced)
- ALL: all replicas respond (most consistent, slowest)

**Q15. Replication Strategies:**
- SimpleStrategy: single data center, testing.
- NetworkTopologyStrategy: multi-datacenter, production, per-DC replication factors.

### Part C — Answer Outlines

**Q16. Streaming Pipeline (5 Marks):** Define streaming data → Sources → 5 V's → 6-stage pipeline with description → Batch vs Stream comparison → Tool examples → Conclusion

**Q17. Cassandra Architecture (5 Marks):** Define Cassandra → Features → Node components (6 items with roles) → Write path diagram → Data distribution via partition key → Conclusion

**Q18. Replication & Consistency (5 Marks):** Define RF → Storage formula → Strategies (Simple vs NetworkTopology) → Consistency levels (ONE/QUORUM/ALL) → Node failure example → Conclusion

**Q19. CQL Commands (5 Marks):** CREATE KEYSPACE with replication → CREATE TABLE with PRIMARY KEY → INSERT → SELECT → UPDATE → DELETE → ALTER → Conclusion

**Q20. Collections (5 Marks):** Define collections → Set (unique, unordered) → List (ordered, indexed) → Map (key-value) → CQL syntax for each → Advantages → Conclusion
