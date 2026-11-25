# BDA – Unit 4: Practice Questions & Active Recall Quiz

---

## Part A: 1-Mark MCQs

**Q1.** NoSQL stands for:
- (A) No SQL  (B) Not Only SQL  (C) New SQL  (D) Non-Sequential SQL

**Q2.** Which NoSQL type is best for social network relationships?
- (A) Key-Value  (B) Document  (C) Column-Family  (D) Graph

**Q3.** HBase stores data in which model?
- (A) Key-Value  (B) Document  (C) Column-Family  (D) Graph

**Q4.** Which component in HBase handles administrative functions?
- (A) RegionServer  (B) HMaster  (C) DataNode  (D) NodeManager

**Q5.** Hive Query Language is called:
- (A) HQL/HiveQL  (B) HiveSQL  (C) H-SQL  (D) QueryHive

**Q6.** Which scaling approach does NoSQL typically use?
- (A) Vertical  (B) Horizontal  (C) Diagonal  (D) Circular

**Q7.** HBase cell is identified by:
- (A) Row Key only
- (B) Row Key + Column Family
- (C) Row Key + Column Family + Column Qualifier + Timestamp
- (D) Table Name + Row Key

**Q8.** Which Hive component stores metadata about tables?
- (A) Driver  (B) Compiler  (C) Metastore  (D) Execution Engine

**Q9.** HBase writes are first stored in:
- (A) HFile  (B) MemStore  (C) HDFS directly  (D) NameNode

**Q10.** Hive is best suited for:
- (A) Real-time transactions  (B) Low-latency queries
- (C) Analytical batch workloads  (D) Random record access

---

## Part B: 2-Mark Questions

**Q11.** Differentiate between Key-Value and Document databases.

**Q12.** What is the difference between HBase and Hive?

**Q13.** List the four types of NoSQL databases with one example each.

**Q14.** What are the components of HBase architecture? Briefly describe each.

**Q15.** Explain the role of Metastore in Hive.

---

## Part C: 5-Mark Descriptive Questions

**Q16.** Explain the four types of NoSQL databases with examples and use cases.

**Q17.** Compare SQL and NoSQL databases on at least seven parameters.

**Q18.** Describe the HBase data model and architecture with a neat diagram.

**Q19.** Explain the Apache Hive architecture with all its components.

**Q20.** When would you choose HBase over Hive and vice versa? Explain with examples.

---

## 📝 ANSWER KEY

### Part A
1. (B) Not Only SQL  2. (D) Graph  3. (C) Column-Family  4. (B) HMaster
5. (A) HQL/HiveQL  6. (B) Horizontal  7. (C) Row Key+CF+CQ+Timestamp
8. (C) Metastore  9. (B) MemStore  10. (C) Analytical batch workloads

### Part B — Model Answers

**Q11. Key-Value vs Document:**
- Key-Value stores simple key→value pairs. Fast lookups. Value is opaque. Example: Redis for session storage.
- Document stores JSON-like documents. Supports nested objects, arrays, different fields per document. Example: MongoDB for product catalog.

**Q12. HBase vs Hive:**
- HBase: Column-family DB, low-latency random read/write, row-key access, real-time. Hive: Data warehouse, HiveQL, batch analytics, high-latency.

**Q13. Four NoSQL types:**
- Key-Value (Redis, session storage), Document (MongoDB, product catalog), Column-Family (HBase/Cassandra, IoT), Graph (Neo4j, social networks)

**Q14. HBase Components:**
- HMaster: Admin/coordination, assigns regions
- RegionServer: Worker, handles read/write, MemStore+HFiles
- Region: Row key range, distributed across servers

**Q15. Metastore in Hive:**
- Stores metadata about Hive tables — table names, column names, data types, partition info, storage locations. Actual data is in HDFS. Helps Compiler understand data structure.

### Part C — Answer Outlines

**Q16. NoSQL Types (5 Marks):** Define NoSQL → 4 types with definition, structure, example, use case → Comparison table → Conclusion

**Q17. SQL vs NoSQL (5 Marks):** Define both → 7-point comparison table → When to use each → Examples → Conclusion

**Q18. HBase Model & Architecture (5 Marks):** Data model (Row Key, CF, CQ, Cell, Timestamp) → Architecture diagram → HMaster, RegionServer, Regions → Read operation → Advantages/disadvantages → Conclusion

**Q19. Hive Architecture (5 Marks):** Define Hive → Query flow → 6 components with roles → Execution engines → Comparison with RDBMS → Conclusion

**Q20. HBase vs Hive choice (5 Marks):** Define both → Comparison table → When to use HBase (real-time, row-key access) → When to use Hive (analytics, SQL-like) → Examples → Conclusion
