# BDA – Unit 2: Big Data Technologies – Hadoop
## Complete Lecture Notes | OLMCA606

---

## 📋 Topics Covered

1. Introduction to Hadoop
2. Evolution of Hadoop
3. Characteristics of Hadoop
4. HDFS — Introduction & Goals
5. HDFS Architecture (NameNode, DataNode, Secondary NameNode)
6. HDFS Blocks & Replication
7. Write Operation in HDFS
8. Read Operation in HDFS
9. HDFS Commands
10. Hadoop Ecosystem

---

## 📖 1. Introduction to Hadoop

### Official Definition

> **Hadoop** is an open-source framework for distributed storage and processing of large datasets across clusters of commodity hardware. It provides scalability, fault tolerance, and handles any data type — structured, semi-structured, and unstructured — at massive scale.

### Hinglish Explanation

Traditional systems mein problems the — storage limitations, processing bottlenecks, high hardware cost, hardware failures, aur scalability issues. Hadoop ne ye sab solve kiya. Ye saste commodity computers ke clusters par kaam karta hai. Large problems ko chhote tasks mein todta hai, unhe parallel process karta hai multiple machines par, aur scale karna easy hai — bas aur machines add karo.

---

## 📖 2. Evolution of Hadoop

| Year | Milestone |
|------|-----------|
| 2003 | Google File System concepts published |
| 2005 | Google MapReduce concepts published |
| 2006 | **Doug Cutting** created Hadoop at **Yahoo!** |
| 2008 | Apache Hadoop released as open-source |

### Hadoop Versions

| Version | Key Feature |
|---------|-------------|
| **1.x** | HDFS + MapReduce only. JobTracker handled both scheduling and resource management — scalability bottleneck |
| **2.x** | Introduced **YARN** — separated resource management from processing. NameNode HA support |
| **3.x** | Erasure coding, multiple standby NameNodes, improved container support |

**Exam tip:** Founder = Doug Cutting, Company = Yahoo!, Inspired by Google's papers (GFS 2003, MapReduce 2005)

---

## 📖 3. Characteristics of Hadoop

| # | Characteristic | Description |
|---|---------------|-------------|
| 1 | **Scalable** | Add nodes to grow storage and compute capacity linearly |
| 2 | **Fault-Tolerant** | Data is replicated; cluster survives individual node failures |
| 3 | **Cost-Effective** | Runs on inexpensive commodity hardware |
| 4 | **Flexible** | Stores and processes any data format without fixed schema |
| 5 | **High Throughput** | Optimized for reading and writing very large datasets quickly |
| 6 | **Data Locality** | Moves computation to the data instead of moving data across the network |

### Advantages
- Highly scalable with commodity hardware
- Fault-tolerant through data replication
- Cost-effective vs traditional storage
- Open-source with large community
- Flexible — handles any data format

### Limitations
- Inefficient with very large numbers of small files
- Not designed for low-latency, real-time queries
- Complex to set up, tune, and administer
- Not ideal for iterative, in-memory algorithms (MapReduce limitation)
- Historically weaker built-in security

---

## 📖 4. HDFS — Introduction

### Official Definition

> **HDFS (Hadoop Distributed File System)** is a distributed file system specifically designed for storing very large datasets. It divides large files into blocks and distributes them across multiple DataNodes, providing high-throughput data access and fault tolerance through replication.

### HDFS Goals & Assumptions

| # | Goal | Description |
|---|------|-------------|
| 1 | **Hardware Failure is Normal** | Failures expected, not exceptional — auto-detect and recover |
| 2 | **Large Datasets** | Files far larger than a single disk |
| 3 | **Streaming Access** | High-throughput sequential reads (not random access) |
| 4 | **Simple Coherency** | Write-once, read-many model |
| 5 | **Move Computation** | Cheaper to move computation to data than data to computation |
| 6 | **Portability** | Works across heterogeneous hardware and OS |

---

## 📖 5. HDFS Architecture

```
         ┌──────────────┐
         │    Client    │
         └──────┬───────┘
                │ metadata requests
         ┌──────▼───────┐
         │   NameNode   │ ← Master (metadata only)
         │  FsImage +   │
         │   EditLog    │
         └──────┬───────┘
                │
    ┌───────────┼───────────┐
    ▼           ▼           ▼
┌────────┐ ┌────────┐ ┌────────┐
│DataNode│ │DataNode│ │DataNode│ ← Workers (actual data)
│  DN-1  │ │  DN-2  │ │  DN-3  │
└────────┘ └────────┘ └────────┘
   Secondary NameNode (separate machine, checkpointing)
```

### NameNode (Master)
- Central manager of HDFS
- Maintains metadata: file names, permissions, block locations, replication info
- Stores **FsImage** (persistent snapshot) and **EditLog** (transaction log)
- Keeps full metadata in RAM for fast access
- All file operations (open, close, rename) go through NameNode
- Does NOT store actual data

### DataNode (Worker)
- Stores actual data blocks
- Handles client read and write requests
- Sends heartbeats to NameNode every ~3 seconds
- Sends block reports periodically
- 1000s of DataNodes in production cluster

### Secondary NameNode
- NOT a backup or failover NameNode
- Performs periodic **checkpointing** — merges FsImage and EditLog
- Prevents EditLog from growing too large
- Reduces NameNode restart time
- Runs on a separate machine (memory-intensive)

### HDFS Metadata
- **FsImage:** Complete snapshot of file system namespace and block mappings
- **EditLog:** Transaction log of every metadata change
- **In-memory:** Active NameNode keeps full metadata in RAM

---

## 📖 6. HDFS Blocks & Replication

### Blocks
- HDFS divides large files into **fixed-size blocks** (default: **128 MB**)
- Large block size minimizes seek overhead for sequential reads
- Each block individually replicated (default factor: **3**)

### Example
- File size: 300 MB, Block size: 128 MB
- Block 1: 128 MB → DN1, DN2, DN3
- Block 2: 128 MB → DN4, DN5, DN6
- Block 3: 44 MB → DN7, DN8, DN9

### Replica Placement Policy

| Replica | Placement |
|---------|-----------|
| **1st** | Same node as client (or random if writing externally) |
| **2nd** | Different rack (rack failure protection) |
| **3rd** | Different node, same rack as 2nd replica |

### DataNode Failure Handling
1. NameNode detects failure via missing heartbeats
2. Identifies under-replicated blocks
3. Creates new replicas on available DataNodes

---

## 📖 7. Write Operation in HDFS

### 4 Steps

| Step | Action |
|------|--------|
| **1. Create Request** | Client asks NameNode to create a new file |
| **2. Block Allocation** | NameNode checks permissions, returns DataNode list |
| **3. Pipeline Write** | Client streams data: DN1 → DN2 → DN3 (pipeline) |
| **4. Acknowledge** | ACKs flow back; NameNode finalizes metadata |

**Key point:** Data does NOT go through NameNode — only metadata does!

### Pipeline Mechanism
- Client sends data to first DataNode
- DN1 forwards to DN2, DN2 forwards to DN3
- ACKs flow back: DN3 → DN2 → DN1 → Client

### Handling Write Failures
- Pipeline recovery: failed DataNode removed, pipeline reconstructed
- Already-acknowledged data preserved
- NameNode arranges replacement replica

---

## 📖 8. Read Operation in HDFS

### 4 Steps

| Step | Action |
|------|--------|
| **1. Open Request** | Client calls open() on file; request to NameNode |
| **2. Locate Blocks** | NameNode returns block IDs + DataNode locations (closest-first) |
| **3. Direct Read** | Client connects directly to nearest DataNode for each block |
| **4. Stream & Close** | Blocks streamed and concatenated; client closes stream |

**Key point:** Client reads data DIRECTLY from DataNodes — NOT through NameNode!

### Handling Read Failures
- Automatic fallback: tries next replica if DataNode unreachable
- Checksum verification for data integrity
- Bad block reporting to NameNode

### Read vs Write Comparison

| Feature | Write | Read |
|---------|-------|------|
| NameNode role | Allocates blocks | Returns block locations |
| Data path | Pipeline: DN1→DN2→DN3 | Direct from nearest DN |
| Through NameNode? | No (only metadata) | No (only metadata) |

---

## 📖 9. HDFS Commands

### Syntax
```
hdfs dfs -<command> [options] <args>
```

### Most-Used Commands

| Command | Description |
|---------|-------------|
| `hdfs dfs -ls /path` | List files and directories |
| `hdfs dfs -mkdir /path` | Create directory |
| `hdfs dfs -mkdir -p /a/b/c` | Create nested directories |
| `hdfs dfs -put local.txt /hdfs/` | Upload local file to HDFS |
| `hdfs dfs -copyFromLocal local.txt /hdfs/` | Same as -put |
| `hdfs dfs -get /hdfs/file local.txt` | Download from HDFS |
| `hdfs dfs -cat /path/file` | View file contents |
| `hdfs dfs -tail /path/file` | Show last KB of file |
| `hdfs dfs -rm /path/file` | Delete file |
| `hdfs dfs -rm -r /path` | Recursively delete directory |
| `hdfs dfs -mv src dst` | Move/rename |
| `hdfs dfs -cp src dst` | Copy within HDFS |
| `hdfs dfs -du -s -h /path` | Disk usage (human-readable) |
| `hdfs dfsadmin -report` | Cluster health report |
| `hdfs fsck /path` | Check file system health |
| `hdfs dfs -chmod 755 /path` | Change permissions |
| `hdfs dfs -chown user:group /path` | Change ownership |

---

## 📖 10. Hadoop Ecosystem

### Architecture Layers

| Layer | Tools |
|-------|-------|
| **Storage** | HDFS |
| **Resource Management** | YARN |
| **Processing** | MapReduce (batch), Spark (in-memory) |
| **Querying/ETL** | Hive (SQL), Pig (scripting) |
| **Database** | HBase (NoSQL) |
| **Data Transfer** | Sqoop (RDBMS), Flume (logs) |
| **Coordination** | Zookeeper |
| **Workflow** | Oozie |

### Tool Descriptions

| Tool | Purpose | Key Feature |
|------|---------|-------------|
| **MapReduce** | Batch processing | Map → Shuffle → Reduce stages |
| **Spark** | In-memory processing | Faster than MapReduce, supports ML/streaming |
| **Hive** | SQL-like querying | HiveQL → MapReduce/Spark jobs, schema-on-read |
| **Pig** | ETL scripting | Pig Latin, procedural data flow |
| **HBase** | NoSQL column store | Real-time read/write on HDFS, BigTable model |
| **Sqoop** | RDBMS transfer | Import/export between Hadoop and SQL databases |
| **Flume** | Log ingestion | Source → Channel → Sink pipeline |
| **Zookeeper** | Coordination | Config mgmt, leader election, naming |
| **Oozie** | Workflow scheduling | DAG-based, chains MapReduce/Hive/Pig/Sqoop |

### Exam Tool Matching

| Need | Best Tool |
|------|-----------|
| SQL-style querying | Hive |
| ETL / data transformation | Pig |
| Real-time random read/write | HBase |
| RDBMS ↔ Hadoop | Sqoop |
| Streaming logs | Flume |
| Distributed coordination | Zookeeper |
| Workflow scheduling | Oozie |
| Fast in-memory analytics | Spark |

---

## 🎯 EXAMINATION PERSPECTIVE

### Important Definitions
1. Hadoop, HDFS, NameNode, DataNode, Secondary NameNode
2. Block, Replication Factor, FsImage, EditLog
3. YARN, ResourceManager, NodeManager
4. Rack Awareness, Data Locality

### Potential 5-Mark Questions
1. Explain HDFS architecture with diagram
2. Describe write operation in HDFS step by step
3. Describe read operation in HDFS
4. Explain Hadoop ecosystem tools
5. Characteristics + advantages/limitations of Hadoop
