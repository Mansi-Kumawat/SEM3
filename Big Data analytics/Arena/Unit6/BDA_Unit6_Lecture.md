# BDA Unit 6 — Analysing Streaming Data & Cassandra
## Complete Lecture Notes (Hinglish) | Week 9 + Week 10

---

## 1. Streaming Data Kya Hai?

**Definition:** Streaming data consists of continuously generated records. Data arrives over time instead of being collected as a completed dataset.

**Simple bhasha mein:** Dekho, batch processing mein data ek saath collect hota hai aur phir process hota hai. Lekin streaming mein data **lagatar aata rehta hai** — ek ek karke, real-time mein. Jaise tumhara heart monitor — har second data bhejta rehta hai. Rukta nahi hai.

**Sources of Streaming Data — yaad rakhna exam ke liye:**
- 🌡️ **IoT devices:** Temperature, pressure, humidity sensors — continuously data bhejte hain
- 🌐 **Web applications:** Clicks, page views, searches — har user action ek event hai
- 🏦 **Banking:** Payments, fraud alerts — real-time transactions
- 📞 **Telecommunications:** Call events, network events
- 🏥 **Healthcare:** Patient monitoring devices — continuously vital signs bhejte hain
- ☁️ **Cloud systems:** Application logs, server metrics

### Characteristics — 5 V's (Streaming Data bhi Big Data hai!)

| V | Matlab | Example |
|---|--------|---------|
| **Velocity** | Data kitni speed se aa raha hai | Per second 10,000 events |
| **Volume** | Kitna data aa raha hai | TBs per day |
| **Variety** | Alag-alag formats | JSON, XML, binary |
| **Veracity** | Data kitna reliable hai | Sensors kabhi galat bhi bhej sakte hain |
| **Value** | Insights kitni useful hain | Fraud detect karna = value |

---

## 2. Batch vs Stream Processing

**Difference samjho — exam mein table banake aata hai:**

| Feature | Batch Processing | Stream Processing |
|---------|-----------------|-------------------|
| **Data** | Accumulated data — pehle collect, phir process | Arriving events — aate hi process |
| **Timing** | Scheduled (daily, weekly, monthly) | Continuous — real-time |
| **Use case** | Historical reports | Immediate alerts |
| **Example** | Monthly sales report | Payment fraud alert — turant pakadna hai! |

**Ek real example se samjho:**
- **Batch:** Mahine ke end mein sabhi transactions ka report banana — "Is mahine kitna sales hua?"
- **Stream:** Abhi-abhi koi transaction ho raha hai, aur turant check karna — "Ye fraud toh nahi hai?"

### Streaming Data Processing Pipeline (6 Stages)

Yeh pipeline bahut important hai — step by step samjho:

| Stage | Kya Hota Hai | Example |
|-------|-------------|---------|
| **1. Source** | Events generate hote hain | Sensor ne temperature bheja |
| **2. Ingestion** | Events receive aur transport hote hain | Apache Kafka events ko receive karta hai |
| **3. Processing** | Filter, transform, aggregate | "Sirf >100°C wale events dikhao" |
| **4. Storage** | Records save hote hain querying ke liye | Cassandra mein store kiya |
| **5. Analytics** | Patterns aur anomalies identify | "Pichle 1 ghante mein temperature consistently badh raha hai" |
| **6. Action** | Alert trigger ya dashboard update | "Alert: Machine overheating!" |

**Example tools yaad rakhna:**
- **Apache Kafka** → Event transport (ingestion layer)
- **Apache Flink** → Stream processing (real-time processing)
- **Cassandra** → Distributed storage (data store karna)

### Windows in Stream Processing

Streaming mein data kabhi rukta nahi, toh hum **windows** define karte hain — ki kaunse events ko ek saath group karna hai:

| Window Type | Matlab | Example |
|-------------|--------|---------|
| **Tumbling Window** | Fixed, non-overlapping intervals | Har 5 minute ka alag group — 12:00-12:05, 12:05-12:10 |
| **Sliding Window** | Overlapping intervals | Har 1 minute pe pichle 5 minute ka data — overlap hota hai |
| **Session Window** | Inactivity periods se group | User active hai tab tak ek group, 30 min idle = naya session |

---

## 3. Apache Cassandra

**Definition:** Apache Cassandra is an open-source, distributed NoSQL database designed for high availability and large-scale workloads. It stores data across multiple nodes and uses CQL (Cassandra Query Language).

**Simple matlab:** Cassandra ek aisa database hai jo:
- **Distributed hai** — data ek machine pe nahi, bahut machines pe spread hota hai
- **NoSQL hai** — SQL tables nahi, flexible schema hai
- **High availability** — ek machine band ho toh bhi kaam chalta hai
- **Large-scale** — terabytes of data handle kar sakta hai

**Yeh kahan use hota hai:**
- Instagram (messages store karta hai)
- Netflix (user data)
- Apple (billions of events daily)
- Uber (ride data)

### Key Features — Exam Points

| Feature | Matlab |
|---------|--------|
| **Peer-to-peer architecture** | Koi master-slave nahi — sab nodes equal hain |
| **High write throughput** | Bahut tezi se likh sakta hai — reads se faster |
| **Horizontal scalability** | Aur machines add karo, capacity badhao |
| **Configurable consistency** | Tum decide karo — speed chahiye ya accuracy |
| **Geographic distribution** | Different data centers mein data rakh sakte ho |
| **Time-series & event data** | Streaming data ke liye perfect |

### Cassandra vs RDBMS — Difference Table

| Feature | Cassandra (NoSQL) | RDBMS (MySQL, PostgreSQL) |
|---------|-----------|-------|
| **Architecture** | Peer-to-peer (sab equal) | Client-Server (master-slave) |
| **Schema** | Flexible — columns add ho sakte hain | Fixed — pehle se define |
| **Scaling** | Horizontal (machines add karo) | Vertical (bigger machine lo) |
| **Joins** | ❌ Not supported | ✅ Strong support |
| **Consistency** | Tunable (tum choose karo) | Strong (ACID guaranteed) |
| **Best for** | Large-scale, distributed data | Complex queries, transactions |

---

## 4. Cassandra Node Components

Har node (machine) ke andar 6 important components hote hain — **yeh bahut important hai exam ke liye:**

| Component | Kya Karta Hai | Simple Explanation |
|-----------|--------------|-------------------|
| **Commit Log** | Har mutation record karta hai recovery ke liye | "Jo bhi likha, uska backup log" — agar power cut ho toh is se recover hoga |
| **Memtable** | In-memory structure holding recent writes | RAM mein temporarily data rakhta hai — fast access |
| **SSTable** | Immutable on-disk storage file | Disk pe permanently likha hua data — ek baar likha toh change nahi hota |
| **Bloom Filter** | Identifies SSTables unlikely to contain a key | Ek "shortcut" — pehle check karta hai ki key yahan hai ya nahi — unnecessary search bachata hai |
| **Partition Index** | Helps locate partition data | SSTable ka index — jaise book ka table of contents |
| **Compaction** | Merges SSTables, removes obsolete data | Purane SSTables merge karke space free karta hai |

### Write Path — Data kaise likha jata hai (IMPORTANT!)

```
Write Request → Commit Log → Memtable → (flush when full) → SSTable
```

**Step by step samjho:**
1. Write request aata hai
2. Pehle **Commit Log** mein likha jata hai (safety ke liye — crash recovery)
3. Phir **Memtable** mein likha jata hai (RAM mein, fast hai)
4. Jab Memtable full ho jaye → **flush** hota hai → naya **SSTable** disk pe banta hai

### Data Distribution & Partitioning

Cassandra mein data kaise distribute hota hai:
- Har row ek **partition** belong karti hai
- **Partition key** determines the token — partition key se decide hota hai data kis node pe jayega
- Tokens map karte hain partitions ko responsible nodes se
- **Good partition key** = even workload distribution (sab nodes equal kaam karein)
- **Poor partition key** = hot partitions (ek node pe bahut load, baaki free)

---

## 5. Replication Factor

**Definition:** Replication Factor (RF) specifies the number of replicas for each partition within the replication scope.

**Simple matlab:** RF = kitni copies rakhni hain data ki. Agar RF=3 hai, toh data ki 3 copies hongi 3 different nodes pe. Ek node down ho toh bhi data safe!

### Example — RF=1 vs RF=3

| Partition | RF = 1 (1 copy — risky!) | RF = 3 (3 copies — safe!) |
|-----------|--------|--------|
| P1 | Sirf N1 pe | N1, N2, N3 — teeno pe |
| P2 | Sirf N2 pe | N2, N3, N4 — teeno pe |
| P3 | Sirf N3 pe | N3, N4, N5 — teeno pe |

### Storage Overhead — Kitna extra storage lagega?

```
Approximate replica storage = Logical data size × RF
```

| Data Size | RF=1 | RF=2 | RF=3 |
|-----------|------|------|------|
| 100 GB | 100 GB | 200 GB | 300 GB |

**Matlab:** RF badhao toh safety badhti hai, lekin storage cost bhi badhti hai!

### Replication Strategies

| Strategy | Kab Use Karein |
|----------|----------|
| **SimpleStrategy** | Single data center, testing ke liye |
| **NetworkTopologyStrategy** | Production environment, multi-datacenter — BEST PRACTICE |

### Creating Keyspace — CQL Commands

```sql
-- SimpleStrategy (testing)
CREATE KEYSPACE college_demo
WITH replication = {
  'class': 'SimpleStrategy',
  'replication_factor': 3
};

-- NetworkTopologyStrategy (production)
CREATE KEYSPACE iot_demo
WITH replication = {
  'class': 'NetworkTopologyStrategy',
  'datacenter1': 3,
  'datacenter2': 2
};
```

---

## 6. Consistency Levels

**Definition:** Consistency level decide karta hai ki write/read operation successful hone ke liye **kitne replicas ko respond karna zaroori hai**.

**Simple samjho:** Tumne data likha RF=3 ke saath (3 copies). Ab kya zaroori hai ki teeno copies likhi jaayein successful? Ya sirf ek? Ya majority? Yeh consistency level decide karta hai.

| Level | Requirement | Latency | Availability | Kab Use Karein |
|-------|-------------|---------|-------------|----------------|
| **ONE** | Sirf 1 replica respond kare | Sabse fast (lowest) | Sabse zyada (highest) | Jab speed chahiye, thoda risk ok hai |
| **QUORUM** | Majority respond kare | Medium | Medium | **Best balance** — production mein commonly used |
| **ALL** | Saare replicas respond karein | Sabse slow (highest) | Sabse kam (lowest) | Jab 100% accuracy chahiye |

**QUORUM ka formula:** `QUORUM = (RF / 2) + 1`
- RF=3 → QUORUM = 2 (2 out of 3 kaafi hain)
- RF=5 → QUORUM = 3

### Node Failure Example — Exam Important!

Scenario: RF = 3, replicas N1, N2, N3 pe hain. N2 fail ho gaya!

| Consistency Level | Result | Kyun? |
|------------------|--------|-------|
| **ONE** | ✅ Success | N1 ya N3 mein se koi bhi respond kar de |
| **QUORUM** | ✅ Success | 2 nodes available hain (N1, N3) — 2 ≥ 2 (required) |
| **ALL** | ❌ Fail | 3 chahiye the, sirf 2 hain — possible nahi |

**Exam tip:** QUORUM best hai kyunki RF=3 mein 1 node fail ho toh bhi kaam chalta hai!

---

## 7. CQL — Cassandra Query Language

**CQL kya hai?** Cassandra se baat karne ki language. SQL jaisa dikhta hai, lekin kuch differences hain (no joins, no subqueries).

### DDL Commands (Data Definition Language)

```sql
-- 1. Keyspace Create Karna
CREATE KEYSPACE myks WITH replication = {
  'class': 'SimpleStrategy', 'replication_factor': 3
};

-- 2. Table Create Karna
CREATE TABLE students (
  student_id int PRIMARY KEY,
  name text,
  cgpa double,
  department text
);

-- 3. Alter Table — Column Add Karna
ALTER TABLE students ADD email text;

-- 4. Drop Table — Pura table delete
DROP TABLE students;
```

### DML Commands (Data Manipulation Language)

```sql
-- INSERT — Data daalna
INSERT INTO students (student_id, name, cgpa)
VALUES (101, 'Ravi', 8.5);

-- SELECT — Data dekhna
SELECT name, cgpa FROM students WHERE student_id = 101;

-- UPDATE — Data change karna
UPDATE students SET cgpa = 9.0 WHERE student_id = 101;

-- DELETE — Data hatana
DELETE FROM students WHERE student_id = 101;
```

**Yaad rakhna:** Cassandra mein UPDATE aur INSERT same hain internally — dono ko **"upsert"** kehte hain. Agar record hai toh update, nahi hai toh insert!

---

## 8. Collections in Cassandra

Cassandra mein 3 types ki collections hoti hain — columns mein multiple values store karne ke liye:

| Type | Kya Hai | Example Use Case |
|------|---------|-----------------|
| **Set** | Unordered, unique values — koi duplicate nahi | Tags, skills (Python, Java, SQL) |
| **List** | Ordered, duplicates allowed, indexed | Ranked items (top 5 movies) |
| **Map** | Key-value pairs | User preferences (theme: dark, lang: hindi) |

### Examples — CQL Commands

```sql
-- SET — Unordered, unique
CREATE TABLE users (
  id int PRIMARY KEY,
  skills set<text>
);
INSERT INTO users (id, skills) VALUES (1, {'Python', 'Java'});
-- 'Python' do baar add karoge toh bhi ek hi rahega (unique!)

-- LIST — Ordered, duplicates allowed
CREATE TABLE tasks (
  id int PRIMARY KEY,
  steps list<text>
);
INSERT INTO tasks (id, steps) VALUES (1, ['Step 1', 'Step 2', 'Step 1']);
-- 'Step 1' do baar aa sakta hai (duplicates allowed!)

-- MAP — Key-value pairs
CREATE TABLE profiles (
  id int PRIMARY KEY,
  prefs map<text, text>
);
INSERT INTO profiles (id, prefs) VALUES (1, {'theme': 'dark'});
UPDATE profiles SET prefs = prefs + {'lang': 'hindi'} WHERE id = 1;
-- Ab prefs = {'theme': 'dark', 'lang': 'hindi'}
```

### Collections ke Advantages

| Advantage | Matlab |
|-----------|--------|
| **No joins needed** | Related data ek saath store hota hai — alag table se lane ki zaroorat nahi |
| **Fast read/write** | Denormalized hai — seedha access milta hai |
| **Denormalized design** | Data repeat ho sakta hai, but queries fast hain |
| **Related data together** | User ka data + user ki skills + user ki preferences — sab ek jagah |

---

## 9. Quick Summary — Exam Revision

### Definitions (2 marks ke liye)
1. **Streaming Data** — Continuously generated records arriving over time
2. **Cassandra** — Open-source distributed NoSQL DB, peer-to-peer, CQL
3. **Commit Log** — Records mutations for crash recovery
4. **Memtable** — In-memory buffer for recent writes
5. **SSTable** — Immutable on-disk data file
6. **Bloom Filter** — Quick check if key might exist in SSTable
7. **Replication Factor** — Number of copies of each partition
8. **Consistency Level** — How many replicas must respond (ONE/QUORUM/ALL)
9. **CQL** — Cassandra Query Language — SQL-like interface
10. **Collections** — Set (unique), List (ordered), Map (key-value)

### Most Important Topics (5 marks ke liye)
1. Streaming Data Pipeline (6 stages)
2. Cassandra Architecture (Node Components + Write Path)
3. Replication Factor + Consistency Levels
4. CQL Commands (DDL + DML)
5. Collections (Set, List, Map with examples)

---

*Unit 6 Complete! Streaming Data + Cassandra — dono important hain exam ke liye!* 🎯
