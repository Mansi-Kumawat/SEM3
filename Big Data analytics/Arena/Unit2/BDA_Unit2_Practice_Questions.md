# BDA – Unit 2: Practice Questions & Active Recall Quiz

---

## Part A: 1-Mark MCQs

**Q1.** Who created Hadoop and in which company?
- (A) Doug Cutting at Google
- (B) Doug Cutting at Yahoo!
- (C) Jeff Dean at Google
- (D) Jimmy Wales at Yahoo!

**Q2.** What is the default block size in HDFS?
- (A) 64 MB
- (B) 128 MB
- (C) 256 MB
- (D) 512 MB

**Q3.** Which HDFS component manages metadata?
- (A) DataNode
- (B) Secondary NameNode
- (C) NameNode
- (D) ResourceManager

**Q4.** What is the default replication factor in HDFS?
- (A) 1
- (B) 2
- (C) 3
- (D) 4

**Q5.** The Secondary NameNode is:
- (A) A backup NameNode
- (B) A failover NameNode
- (C) A checkpointing node
- (D) A DataNode replica

**Q6.** Which command uploads a local file to HDFS?
- (A) hdfs dfs -get
- (B) hdfs dfs -put
- (C) hdfs dfs -copy
- (D) hdfs dfs -upload

**Q7.** DataNode sends heartbeats to NameNode every:
- (A) 1 second
- (B) 3 seconds
- (C) 5 seconds
- (D) 10 seconds

**Q8.** Which ecosystem tool is used for SQL-like querying on Hadoop?
- (A) Pig
- (B) Sqoop
- (C) Hive
- (D) Flume

**Q9.** In HDFS write operation, data flows through:
- (A) NameNode → DataNode
- (B) Client → NameNode → DataNode
- (C) Client → DN1 → DN2 → DN3 (pipeline)
- (D) NameNode → DN1 → DN2 → DN3

**Q10.** Hadoop follows which data locality principle?
- (A) Move data to computation
- (B) Move computation to data
- (C) Move both to central server
- (D) No specific principle

---

## Part B: 2-Mark Questions

**Q11.** Differentiate between NameNode and DataNode.

**Q12.** What is the difference between FsImage and EditLog?

**Q13.** Explain the replica placement policy in HDFS.

**Q14.** What is the role of YARN in Hadoop? How is it different from MapReduce?

**Q15.** Differentiate between read and write operations in HDFS.

---

## Part C: 5-Mark Descriptive Questions

**Q16.** Explain the HDFS architecture with a neat diagram. Describe the role of NameNode, DataNode, and Secondary NameNode.

**Q17.** Describe the write operation in HDFS step by step. Explain the pipeline mechanism and replica placement policy.

**Q18.** Explain the read operation in HDFS. How does HDFS handle read failures?

**Q19.** What is the Hadoop ecosystem? Describe any five ecosystem tools with their purposes.

**Q20.** Explain the characteristics of Hadoop. Discuss its advantages and limitations.

---

## 📝 ANSWER KEY

### Part A Answers
1. **(B)** Doug Cutting at Yahoo!
2. **(B)** 128 MB
3. **(C)** NameNode
4. **(C)** 3
5. **(C)** A checkpointing node (NOT backup!)
6. **(B)** hdfs dfs -put
7. **(B)** 3 seconds
8. **(C)** Hive
9. **(C)** Client → DN1 → DN2 → DN3 (pipeline)
10. **(B)** Move computation to data

### Part B — Model Answers

**Q11. NameNode vs DataNode:**

| Feature | NameNode | DataNode |
|---------|----------|----------|
| **Role** | Master node — manages metadata | Worker node — stores actual data |
| **Stores** | Metadata only (namespace, block locations) | Actual data blocks |
| **Operations** | Handles open, close, rename requests | Handles read/write data requests |
| **Communication** | Receives heartbeats and block reports | Sends heartbeats every 3 sec and block reports |
| **Failure impact** | Critical — single point of failure | Cluster survives individual DataNode failures |

**Q12. FsImage vs EditLog:**

**FsImage** is a persistent snapshot of the entire HDFS file system namespace and block mappings. It represents the complete state of the file system at a point in time.

**EditLog** is a transaction log that records every change (create, delete, rename) made to the file system metadata since the last FsImage checkpoint.

The Secondary NameNode periodically merges FsImage + EditLog to create an updated FsImage, preventing the EditLog from growing too large.

**Q13. Replica Placement Policy:**

HDFS uses a rack-aware replica placement strategy with default replication factor of 3:
- **1st replica:** Placed on the same node as the client (or random node if writing externally)
- **2nd replica:** Placed on a DataNode in a **different rack** (protects against rack-level failure)
- **3rd replica:** Placed on a different node in the **same rack** as the 2nd replica (reduces network cost)

This strategy balances fault tolerance (rack-level protection) with network efficiency.

**Q14. YARN vs MapReduce:**

**YARN (Yet Another Resource Negotiator)** is the resource management layer of Hadoop. It manages CPU and memory resources across the cluster and coordinates application execution. It separates resource management from data processing.

**MapReduce** is a processing framework that divides computation into Map and Reduce stages for batch processing.

**Key difference:** YARN decides WHO gets resources; MapReduce decides HOW to process data. YARN allows multiple frameworks (Spark, Hive, etc.) to share the same cluster.

**Q15. Read vs Write in HDFS:**

| Aspect | Write | Read |
|--------|-------|------|
| **Step 1** | Client requests NameNode to create file | Client requests NameNode to open file |
| **Step 2** | NameNode allocates blocks + DataNodes | NameNode returns block locations |
| **Step 3** | Pipeline write: DN1→DN2→DN3 | Direct read from nearest DataNode |
| **Step 4** | ACKs flow back, metadata finalized | Blocks concatenated, stream closed |
| **Data through NameNode?** | No | No |

### Part C — Answer Outlines

**Q16. HDFS Architecture (5 Marks)**
- Define HDFS
- Draw architecture diagram (Client, NameNode, DataNodes, Secondary NameNode)
- NameNode: role, metadata, FsImage/EditLog
- DataNode: role, heartbeat, block reports
- Secondary NameNode: checkpointing, NOT backup
- Conclusion

**Q17. Write Operation (5 Marks)**
- Define write operation
- 4 steps with diagram
- Pipeline mechanism explanation
- Replica placement policy
- Failure handling
- Conclusion

**Q18. Read Operation (5 Marks)**
- Define read operation
- 4 steps with diagram
- Direct read from DataNodes (not through NameNode)
- Failure handling: fallback to next replica, checksum verification
- Block report role
- Conclusion

**Q19. Hadoop Ecosystem (5 Marks)**
- Define Hadoop ecosystem
- List all tools
- Describe 5 tools in detail: purpose, key feature, use case
- Tool matching table
- Conclusion

**Q20. Characteristics + Advantages/Limitations (5 Marks)**
- Define Hadoop
- 6 characteristics with brief explanation
- 4-5 advantages
- 4-5 limitations
- Conclusion
