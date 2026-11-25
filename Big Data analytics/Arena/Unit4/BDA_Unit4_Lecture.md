# BDA – Unit 4: Big Data Technologies – NoSQL
## Complete Lecture Notes | OLMCA606

---

## 📋 Topics Covered (Week 5)

1. Evolution of Database Systems
2. NoSQL Introduction
3. Types of NoSQL (Key-Value, Document, Column-Family, Graph)
4. SQL vs NoSQL Comparison
5. HBase — Data Model, Architecture, Operations
6. Hive — Introduction, Architecture, Components

---

## 📖 1. Evolution of Database Systems

Early databases handled small amounts of structured business data. Relational databases (RDBMS) became popular with tables, relationships, SQL, and ACID transactions. As internet applications expanded, organizations began generating much larger quantities of diverse data — text, JSON, images, logs, videos, sensor information. Traditional databases struggled with scale, schema rigidity, and vertical scaling costs. NoSQL databases emerged as the solution for flexibility, scalability, and distributed processing.

---

## 📖 2. NoSQL Introduction

### Official Definition

> **NoSQL** refers to database systems that do not rely exclusively on the traditional relational model. It is commonly interpreted as "Not Only SQL." NoSQL systems use different data models and are designed for distributed environments.

### Characteristics of NoSQL

| # | Characteristic | Description |
|---|---------------|-------------|
| 1 | **Flexible Schema** | Data structures can evolve without rigid schema changes |
| 2 | **Horizontal Scaling** | Add more machines to increase capacity |
| 3 | **Distributed Storage** | Data spread across multiple servers |
| 4 | **High Availability** | Multiple copies; survives node failures |
| 5 | **Large-Scale Processing** | Handles datasets larger than single-server capacity |
| 6 | **Application-Specific Design** | Data modeled around access patterns |

### Advantages
- Flexible schema — accommodates changing requirements
- Horizontal scaling — add machines, not bigger servers
- High availability through replication
- Fault tolerance in distributed architecture
- Optimized for specific read/write patterns
- Suitable for Big Data applications

### Limitations
- Complex relationships may be difficult
- Query languages vary across products
- Transaction support differs between systems
- Data duplication due to denormalization
- Careful application-oriented data modeling required

---

## 📖 3. Types of NoSQL

### 1. Key-Value Database
- Stores data as key-value pairs
- Key = identifier, Value = data (simple or complex object)
- Very fast lookups
- **Use when:** Application knows the key before requesting data
- **Example:** Redis, Session storage
- **Data:** `C101 → Ravi, Chennai`

### 2. Document Database
- Stores data as documents (JSON/JSON-like)
- Supports nested objects and arrays
- Different documents can have different fields
- **Use when:** Flexible entity-based information with evolving structure
- **Example:** MongoDB, Product catalog

### 3. Column-Family Database
- Data organized in groups of related columns (column families)
- Designed for large-scale distributed storage
- Data spread across multiple servers
- **Examples:** HBase, Cassandra
- **Use when:** IoT data, large distributed datasets

### 4. Graph Database
- Uses nodes (entities) and edges (relationships)
- Properties attached to nodes and edges
- **Use when:** Relationships are central to the application
- **Example:** Neo4j, Social networks

### Summary Table

| Type | Structure | Best For | Example |
|------|-----------|----------|---------|
| Key-Value | Key → Value | Session storage, caching | Redis |
| Document | JSON documents | Product catalog, CMS | MongoDB |
| Column-Family | Column groups | IoT, large distributed data | HBase, Cassandra |
| Graph | Nodes + Edges | Social networks, recommendations | Neo4j |

---

## 📖 4. SQL vs NoSQL

| Feature | SQL | NoSQL |
|---------|-----|-------|
| **Data Model** | Relational (tables, rows, columns) | Multiple models (KV, Document, Column, Graph) |
| **Schema** | Fixed, predefined | Often flexible, schema-less |
| **Scaling** | Vertical (bigger server) | Horizontal (more servers) |
| **Joins** | Strong support | Often minimized (denormalized) |
| **Transactions** | Strong ACID | Varies by product |
| **Query Language** | Standard SQL | Product-specific APIs/languages |
| **Typical Use** | Transactional (banking, payroll) | Large-scale distributed data |

### When to Use SQL
- Data is structured and relatively stable
- Relationships between entities are important
- Complex queries and joins required
- Strong transaction support necessary (banking, payroll, accounting)

### When to Use NoSQL
- Data structure changes frequently
- Very large datasets need distribution
- Horizontal scalability important
- High availability required
- Semi-structured data (social media, IoT, web apps)

---

## 📖 5. HBase

### Official Definition

> **Apache HBase** is a distributed, scalable, column-family database designed to work with very large datasets. It is closely integrated with Hadoop, uses HDFS for storage, and provides random read and write access to individual records.

### Why HBase?
HDFS is excellent for batch processing of large files but not for accessing individual records. HBase provides row-key-based random access to distributed data.

### HBase Data Model

| Term | Description | Example |
|------|-------------|---------|
| **Table** | Collection of related records | student |
| **Row Key** | Unique identifier for a row | 101 |
| **Column Family** | Groups related columns (defined at table creation) | personal, academic |
| **Column Qualifier** | Specific column within a family | name, city, course, cgpa |
| **Cell** | Stores an individual value | Ravi |
| **Timestamp** | Associates values with versions | 8.5 (old), 8.7 (new) |

**Cell address:** Row Key + Column Family + Column Qualifier + Timestamp

### HBase Architecture

| Component | Role |
|-----------|------|
| **HMaster** | Administrative/coordination — assigns regions to RegionServers, load balancing, recovery. Does NOT handle normal data requests |
| **RegionServer** | Worker node — processes client read/write requests, manages MemStore (memory) and HFiles (persistent on HDFS) |
| **Region** | Subset of table rows (by row key range), distributed across RegionServers. Splits as table grows |
| **MemStore** | In-memory write buffer on RegionServer |
| **HFile** | Persistent storage format on HDFS |

### Region Example
- Region 1: Row keys 0001–1000 → RegionServer A
- Region 2: Row keys 1001–2000 → RegionServer B
- Region 3: Row keys 2001–3000 → RegionServer C

### HBase Read Operation
1. Client specifies row key
2. HBase identifies the appropriate region
3. Request reaches relevant RegionServer
4. RegionServer locates data (MemStore → HFile)
5. Value returned to client

### Advantages
- Suitable for very large distributed datasets
- Random read and write access
- Integrates with Hadoop and HDFS
- Distributed storage using regions
- Suitable for sparse data

### Disadvantages
- Complex joins not its strength
- Row-key design requires careful planning
- Administration can be complex
- Not a direct replacement for every RDBMS workload

---

## 📖 6. Hive

### Official Definition

> **Apache Hive** is a data warehouse and analytical system in the Hadoop ecosystem. It provides an SQL-like language called Hive Query Language (HQL/HiveQL) for analyzing large datasets without writing low-level distributed programs.

### Key Characteristics
- SQL-like interface for large-scale data analysis
- Supports tables, partitions, views, multiple data types
- Works with various storage and file formats
- Integrates with HDFS
- Execution via MapReduce, Tez, or Spark
- Primarily for analytical workloads, NOT OLTP

### Example
```sql
SELECT product, SUM(amount)
FROM sales
GROUP BY product;
```
Hive converts this HQL into MapReduce/Spark jobs automatically.

### Hive vs RDBMS

| Feature | RDBMS | Hive |
|---------|-------|------|
| Orientation | Transaction | Analytics |
| Operations | Record-level | Large-scale batch |
| Latency | Low | High (batch) |
| Storage | Relational | Hadoop ecosystem (HDFS) |
| Language | SQL | HQL/HiveQL |

### Hive Architecture Components

| Component | Role |
|-----------|------|
| **User Interface** | Accepts HQL via CLI, JDBC, ODBC |
| **Driver** | Manages query execution lifecycle and session |
| **Compiler** | Parses query, semantic analysis, gets metadata from Metastore, generates logical plan |
| **Optimizer** | Improves query plan — reduces unnecessary processing, partition pruning, join optimization |
| **Metastore** | Stores metadata — table names, columns, data types, partition info, storage locations |
| **Execution Engine** | Executes physical plan using MapReduce, Tez, or Spark |

### Query Flow
```
User → UI (HQL) → Driver → Compiler → Optimizer → Execution Engine → Result
                         ↑
                     Metastore (metadata)
```

---

## 📖 7. HBase vs Hive

| Feature | HBase | Hive |
|---------|-------|------|
| **Purpose** | Random read/write access | Analytical querying |
| **Data Model** | Column-family | Tables with HQL |
| **Latency** | Low-latency | High (batch) |
| **Storage** | HDFS via Regions | HDFS files |
| **Best For** | Real-time individual record access | SQL-like analytics on big data |
| **Query** | HBase API | HiveQL/HQL |

---

## 📖 8. Hive File Formats (Week 6)

### Why File Format Matters
The choice of format affects storage space, query performance, compression, read/write speed, and compatibility.

### 6 File Formats

| Format | Type | Key Feature | Best For |
|--------|------|-------------|----------|
| **TextFile** | Row-oriented | Simple, human-readable, delimited | Simple raw data, easy import/export |
| **SequenceFile** | Row-oriented binary | Key-value pairs, compression support | Hadoop processing pipelines |
| **Avro** | Row-oriented | Schema stored with data, schema evolution | Data pipelines, evolving structures |
| **RCFile** | Column-group hybrid | Row groups + column within groups | Legacy Hive analytics |
| **Parquet** | Column-oriented | Column-level compression, cross-platform | Analytics, multi-framework |
| **ORC** | Column-oriented | Stripes, Hive-optimized, excellent compression | Hive data warehouse, high-performance |

### Parquet vs ORC
| Feature | ORC | Parquet |
|---------|-----|---------|
| Storage | Columnar | Columnar |
| Hive Integration | Strong (native) | Yes |
| Compression | Excellent | Excellent |
| Ecosystem | Hive-focused | Broad (Spark, Impala, etc.) |

---

## 📖 9. Hive DDL Commands (Week 6)

DDL commands define and manage database structures.

### CREATE
```sql
CREATE DATABASE IF NOT EXISTS company;
USE company;

CREATE TABLE employee (
  id INT,
  name STRING,
  department STRING,
  salary DOUBLE
);
```

### Hive Data Types
INT, BIGINT, FLOAT, DOUBLE, STRING, BOOLEAN, DATE, TIMESTAMP

### Managed vs External Table

| Feature | Managed | External |
|---------|---------|----------|
| Data ownership | Hive | External system/user |
| Location | Hive-managed | User-specified |
| DROP TABLE | Data removed | Data remains |
| Use when | Hive owns data | Shared/existing data |

```sql
CREATE EXTERNAL TABLE employee_ext (
  id INT, name STRING, salary DOUBLE
)
STORED AS TEXTFILE
LOCATION '/data/employees';
```

### Other DDL Commands
```sql
SHOW DATABASES;
SHOW TABLES;
DESCRIBE employee;
DESCRIBE FORMATTED employee;

ALTER TABLE employee RENAME TO employee_details;
ALTER TABLE employee ADD COLUMNS (email STRING, city STRING);

DROP TABLE IF EXISTS employee;
TRUNCATE TABLE employee;
```

---

## 📖 10. Hive DML Commands (Week 6)

### LOAD DATA
```sql
-- From local filesystem
LOAD DATA LOCAL INPATH '/home/user/employee.csv' INTO TABLE employee;
-- From HDFS
LOAD DATA INPATH '/data/employee.csv' INTO TABLE employee;
```

### INSERT
```sql
INSERT INTO TABLE employee VALUES (101, 'Ravi', 'IT', 75000);
INSERT INTO TABLE employee SELECT id, name, department, salary FROM employee_temp;
INSERT OVERWRITE TABLE employee_summary
  SELECT department, AVG(salary) FROM employee GROUP BY department;
```

### SELECT with Aggregations
```sql
SELECT name, salary FROM employee WHERE salary > 50000;

SELECT department, AVG(salary) AS avg_salary
FROM employee
GROUP BY department
HAVING AVG(salary) > 60000
ORDER BY avg_salary DESC;
```

### Aggregate Functions
COUNT(), SUM(), AVG(), MIN(), MAX()

---

## 📖 11. HBase DDL Commands (Week 6)

HBase uses Shell commands, not SQL.

```bash
# Start shell
hbase shell

# Create table with column families
create 'student', 'personal', 'academic'

# List all tables
list

# Describe table
describe 'student'

# Alter: add column family
alter 'student', {NAME => 'contact'}

# Disable (required before drop/alter)
disable 'student'
is_disabled 'student'

# Enable
enable 'student'
is_enabled 'student'

# Drop (must disable first!)
disable 'student'
drop 'student'
```

**Important:** HBase requires table to be disabled before dropping!

---

## 📖 12. HBase DML Commands (Week 6)

```bash
# PUT - insert or update
put 'student', 'S101', 'personal:name', 'Ravi'
put 'student', 'S101', 'personal:age', '20'
put 'student', 'S101', 'academic:course', 'BCA'

# GET - retrieve
get 'student', 'S101'
get 'student', 'S101', {COLUMN => 'personal:name'}
get 'student', 'S101', {COLUMN => ['personal:name', 'academic:course']}

# SCAN - multiple rows
scan 'student'
scan 'student', {COLUMNS => ['personal:name', 'academic:course']}
scan 'student', {LIMIT => 5}
scan 'student', {STARTROW => 'S100', STOPROW => 'S200'}

# DELETE
delete 'student', 'S101', 'personal:age'
deleteall 'student', 'S101'

# COUNT & TRUNCATE
count 'student'
truncate 'student'   # removes data, keeps structure
```

### DROP vs TRUNCATE
- **DROP:** Removes entire table (structure + data)
- **TRUNCATE:** Removes data only, keeps table structure

---

## 📖 13. Hive DDL/DML vs HBase DDL/DML

| Operation | Hive (HQL) | HBase (Shell) |
|-----------|-----------|---------------|
| Create table | `CREATE TABLE t (col TYPE)` | `create 't','family'` |
| Insert data | `INSERT INTO TABLE t VALUES (...)` | `put 't','row','f:q','val'` |
| Read data | `SELECT * FROM t WHERE...` | `get 't','row'` or `scan 't'` |
| Delete | `DELETE FROM t WHERE...` | `delete 't','row','f:q'` |
| Drop | `DROP TABLE t` | `disable 't'` then `drop 't'` |

---

## 🎯 EXAMINATION PERSPECTIVE

### Important Definitions
1. NoSQL, Key-Value, Document, Column-Family, Graph databases
2. HBase, Row Key, Column Family, Cell, Region, RegionServer
3. Hive, HiveQL, Metastore, HMaster

### SQL vs NoSQL — 7-point comparison table (frequently asked)

### Potential 5-Mark Questions
1. Explain types of NoSQL databases with examples
2. Compare SQL and NoSQL databases
3. Describe HBase data model and architecture
4. Explain Hive architecture with components
5. Differentiate between HBase and Hive
6. Explain Hive file formats with comparison
7. Describe Hive DDL commands with Managed vs External table
8. Explain HBase DDL and DML commands with syntax
