# BDA – Unit 2: Big Data Technologies – Hadoop
## Summary Notes | OLMCA606

---

## 1. Important Definitions

**Hadoop:** An open-source framework for distributed storage and processing of large datasets across clusters of commodity hardware. It provides scalability, fault tolerance, and handles any data type at massive scale.

**HDFS (Hadoop Distributed File System):** The primary storage system of Hadoop. It divides large files into blocks and distributes them across multiple DataNodes, providing high-throughput data access and fault tolerance through replication.

**NameNode:** The central master node in HDFS that maintains metadata — file namespace, directory tree, block locations, permissions, and replication info. It does NOT store actual data.

**DataNode:** Worker machines in HDFS that store actual data blocks. They handle client read/write requests and send heartbeats and block reports to the NameNode.

**Secondary NameNode:** Performs periodic checkpointing of NameNode metadata by merging FsImage and EditLog. It is NOT a backup/failover NameNode.

**Block:** The unit of data storage in HDFS. Default block size is 128 MB. Large files are split into blocks distributed across DataNodes.

**Replication Factor:** The number of copies of each block maintained across different DataNodes. Default = 3.

**FsImage:** A persistent snapshot of the entire HDFS file system namespace and block mappings.

**EditLog:** A transaction log recording every change made to HDFS metadata.

**Rack Awareness:** HDFS's strategy of placing replicas across different racks to survive rack-level failures.

---

## 2. Evolution of Hadoop

| Year | Milestone |
|------|-----------|
| 2003 | Google File System paper published |
| 2005 | Google MapReduce paper published |
| 2006 | **Doug Cutting** created Hadoop at **Yahoo!** |
| 2008 | Apache Hadoop released |
| — | Hadoop 1.x: HDFS + MapReduce only (JobTracker = bottleneck) |
| — | Hadoop 2.x: Introduced **YARN** (separated resource management) |
| — | Hadoop 3.x: Erasure coding, multiple standby NameNodes |

**Exam tip:** Founder = Doug Cutting, Company = Yahoo!, Inspired by = Google

---

## 3. Hadoop Characteristics (6 Key Features)

| Feature | Description |
|---------|-------------|
| **Scalable** | Add more nodes to grow storage and compute linearly |
| **Fault-Tolerant** | Data replicated; cluster survives node failures |
| **Cost-Effective** | Runs on inexpensive commodity hardware |
| **Flexible** | Handles any data format without fixed schema |
| **High Throughput** | Optimized for fast reading/writing of large datasets |
| **Data Locality** | Moves computation TO data, not data to computation |

---

## 4. HDFS Architecture

```
         ┌──────────────┐
         │    Client    │
         └──────┬───────┘
                │ metadata requests
         ┌──────▼───────┐
         │   NameNode   │ ← Master (metadata only)
         │  (FsImage +  │
         │   EditLog)   │
         └──────┬───────┘
                │
    ┌───────────┼───────────┐
    ▼           ▼           ▼
┌────────┐ ┌────────┐ ┌────────┐
│DataNode│ │DataNode│ │DataNode│ ← Workers (actual data)
│  DN-1  │ │  DN-2  │ │  DN-3  │
│Blocks  │ │Blocks  │ │Blocks  │
└────────┘ └────────┘ └────────┘

   Secondary NameNode (separate machine, checkpointing)
```

### Component Summary

| Component | Role | Key Facts |
|-----------|------|-----------|
| **NameNode** | Master — manages metadata | Stores FsImage + EditLog in RAM, handles all file operations |
| **DataNode** | Worker — stores data blocks | Sends heartbeat every 3 sec, sends block reports periodically |
| **Secondary NameNode** | Checkpointing | Merges FsImage + EditLog, NOT a backup, runs on separate machine |

---

## 5. HDFS Blocks & Replication

- **Default block size:** 128 MB
- **Default replication factor:** 3
- **Example:** 300 MB file → Block 1 (128 MB) + Block 2 (128 MB) + Block 3 (44 MB)

### Replica Placement Policy

| Replica | Placement |
|---------|-----------|
| 1st | Same node as client (or random if external) |
| 2nd | Different rack (rack failure protection) |
| 3rd | Different node, same rack as 2nd replica |

### Node Failure Handling
- NameNode detects failure via missing heartbeats
- Identifies under-replicated blocks
- Creates new replicas on available DataNodes

---

## 6. Write Operation in HDFS (4 Steps)

| Step | Action |
|------|--------|
| **1. Create Request** | Client asks NameNode to create a new file |
| **2. Block Allocation** | NameNode checks permissions, returns DataNode list |
| **3. Pipeline Write** | Client streams data: DN1 → DN2 → DN3 (pipeline) |
| **4. Acknowledge** | ACKs flow back; NameNode finalizes metadata |

**Key point:** Data does NOT go through NameNode — only metadata does!

---

## 7. Read Operation in HDFS (4 Steps)

| Step | Action |
|------|--------|
| **1. Open Request** | Client calls open() on file; request goes to NameNode |
| **2. Locate Blocks** | NameNode returns block IDs + DataNode locations (closest-first) |
| **3. Direct Read** | Client connects directly to nearest DataNode for each block |
| **4. Stream & Close** | Blocks streamed and concatenated; client closes stream |

**Key point:** Client reads data DIRECTLY from DataNodes — NOT through NameNode!

### Read vs Write Comparison

| Feature | Write | Read |
|---------|-------|------|
| NameNode role | Allocates blocks | Returns block locations |
| Data path | Pipeline: DN1→DN2→DN3 | Direct from nearest DN |
| Through NameNode? | No (only metadata) | No (only metadata) |

---

## 8. HDFS Commands (Most Important)

| Command | Description |
|---------|-------------|
| `hdfs dfs -ls /path` | List files/directories |
| `hdfs dfs -mkdir /path` | Create directory |
| `hdfs dfs -mkdir -p /a/b/c` | Create nested directories |
| `hdfs dfs -put local.txt /hdfs/` | Upload local file to HDFS |
| `hdfs dfs -get /hdfs/file local.txt` | Download from HDFS to local |
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

**Syntax:** `hdfs dfs -<command> [options] <args>`

---

## 9. Hadoop Ecosystem Tools

| Tool | Purpose | Key Feature |
|------|---------|-------------|
| **HDFS** | Distributed Storage | Primary storage layer |
| **YARN** | Resource Management | Separates resource mgmt from processing |
| **MapReduce** | Batch Processing | Divides into Map → Shuffle → Reduce |
| **Spark** | In-Memory Processing | Faster than MapReduce, supports ML/streaming |
| **Hive** | SQL-like Querying | HiveQL → MapReduce/Spark jobs |
| **Pig** | ETL Scripting | Pig Latin language, procedural |
| **HBase** | NoSQL Database | Column-oriented, real-time read/write on HDFS |
| **Sqoop** | RDBMS ↔ Hadoop Transfer | Import/export between Hadoop and SQL databases |
| **Flume** | Log/Event Ingestion | Source → Channel → Sink pipeline |
| **Zookeeper** | Distributed Coordination | Configuration mgmt, leader election |
| **Oozie** | Workflow Scheduling | DAG-based, chains MapReduce/Hive/Pig/Sqoop |

### Exam Tool Matching

| Need | Best Tool |
|------|-----------|
| SQL-style querying | **Hive** |
| ETL / data transformation | **Pig** |
| Real-time random read/write | **HBase** |
| RDBMS ↔ Hadoop transfer | **Sqoop** |
| Streaming log ingestion | **Flume** |
| Distributed coordination | **Zookeeper** |
| Workflow scheduling | **Oozie** |
| Fast in-memory analytics | **Spark** |

---

## 10. Advantages & Limitations of Hadoop

### Advantages
- Highly scalable with commodity hardware
- Fault-tolerant through data replication
- Cost-effective vs traditional storage
- Open-source with large community
- Flexible — any data format
- Data locality reduces network traffic

### Limitations
- Inefficient with many small files
- Not for low-latency, real-time queries
- Complex to set up and administer
- Not ideal for iterative algorithms (MapReduce limitation)
- Historically weaker security

---

## 11. Last-Minute Revision

```
HADOOP = Open-source, distributed, commodity hardware
Founder: Doug Cutting (Yahoo!, 2006)

HDFS ARCHITECTURE:
  NameNode (Master) → metadata, FsImage, EditLog
  DataNode (Worker) → actual data blocks, heartbeat every 3s
  Secondary NameNode → checkpointing (NOT backup!)

BLOCKS: Default 128 MB | Replication: Default 3
Replica Policy: Same node → Different rack → Same rack diff node

WRITE: Client → NameNode (allocate) → Pipeline DN1→DN2→DN3 → ACK
READ:  Client → NameNode (locate) → Direct DN (nearest first)

ECOSYSTEM:
  Storage: HDFS | Resources: YARN | Batch: MapReduce
  Fast: Spark | SQL: Hive | ETL: Pig | NoSQL: HBase
  Transfer: Sqoop | Logs: Flume | Coord: Zookeeper | Workflow: Oozie
```

---

## 12. Common Mistakes & Confusions

| Mistake | Correct Understanding |
|---------|----------------------|
| "Secondary NameNode = Backup" | NO! It does checkpointing only, not failover |
| "Data goes through NameNode" | NO! Only metadata goes through NameNode |
| "Hadoop = HDFS" | Hadoop = HDFS + YARN + MapReduce + Common |
| "HDFS for small files" | HDFS is inefficient for many small files |
| "Block size = replication" | Block = data chunk, Replication = copies |
| "YARN = MapReduce" | YARN manages resources; MapReduce processes data |
