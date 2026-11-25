# BDA – Unit 5: Analysing Unstructured Data – MongoDB
## Complete Lecture Notes | OLMCA606

---

## 📋 Topics Covered (Week 7 + Week 8)

1. MongoDB Introduction
2. MongoDB vs Relational Database
3. BSON, ObjectId, Document Structure
4. CRUD Operations
5. Indexes
6. Replication
7. Sharding
8. MongoDB Queries & Operators
9. Update & Delete Operations
10. Import/Export/Backup
11. Aggregation Framework

---

## 📖 1. MongoDB Introduction

### Official Definition

> **MongoDB** is a document-oriented NoSQL database management system. It stores data in flexible, JSON-like documents rather than traditional rows and columns. Internally, MongoDB uses BSON (Binary JSON) to represent documents.

### Hinglish Explanation

Traditional database mein data rows aur columns mein hota hai tables mein — sab structured. MongoDB mein data JSON documents mein hota hai — flexible, nested, aur dynamic. Same collection mein alag-alag documents ke alag-alag fields ho sakte hain.

---

## 📖 2. MongoDB vs Relational Database

| Relational DB | MongoDB |
|---------------|---------|
| Database | Database |
| Table | Collection |
| Row | Document |
| Column | Field |
| Primary Key | _id |
| SQL | MongoDB Query Language (MQL) |
| JOIN | Embedding / $lookup |
| Fixed Schema | Flexible Document Structure |

---

## 📖 3. BSON, ObjectId, and Document Structure

### BSON (Binary JSON)
MongoDB uses BSON internally because it:
- Supports more data types than standard JSON
- Allows efficient storage and traversal
- Supports Date, ObjectId, Binary data

### Data Types
String, Integer, Double, Decimal, Boolean, Array, Embedded Document, ObjectId, Date, Null, Binary Data, Regular Expression

### _id Field
- Every document has a unique `_id` field
- Auto-generated as ObjectId if not provided
- Provides document-level uniqueness within a collection

### ObjectId
- Compact, unique identifier
- Contains creation time information
- No central counter needed

### Flexible Schema
Different documents in the same collection can have different fields:
```json
{"name": "Ravi", "age": 21}
{"name": "Priya", "age": 22, "skills": ["Java", "Python"]}
```

### Arrays and Embedded Documents
```json
{"name": "Ravi", "skills": ["Java", "Python", "MongoDB"]}
{"name": "Priya", "address": {"street": "Main Road", "city": "Vellore", "pincode": 632001}}
```

### Embedding vs Referencing
- **Embedding:** Related data stored inside the same document. Use when data is accessed together and manageable in size.
- **Referencing:** Related data in separate documents with ID reference. Use when data is large, shared, or independently updated.

---

## 📖 4. CRUD Operations

### Create
```javascript
db.students.insertOne({name: "Ravi", age: 21})
db.students.insertMany([{...}, {...}, {...}])
```

### Read
```javascript
db.students.find()                         // All documents
db.students.find({age: 21})               // Filter
db.students.findOne({studentId: 105})     // Single document
```

### Update
```javascript
db.students.updateOne({name: "Ravi"}, {$set: {age: 22}})
db.students.updateMany({department: "CSE"}, {$inc: {cgpa: 0.1}})
```

### Delete
```javascript
db.students.deleteOne({studentId: 101})
db.students.deleteMany({cgpa: {$lt: 8}})
```

---

## 📖 5. Indexes

An index helps MongoDB locate documents efficiently — without scanning all documents.

### Types of Indexes

| Type | Description | Example |
|------|-------------|---------|
| **Single-field** | Index on one field | `createIndex({name: 1})` |
| **Compound** | Index on multiple fields | `createIndex({department: 1, age: -1})` |
| **Multikey** | For arrays | Auto-created when indexing array field |
| **Text** | Full-text search | `createIndex({content: "text"})` |
| **Geospatial** | Location data | `createIndex({location: "2dsphere"})` |
| **Hashed** | For sharding | `createIndex({id: "hashed"})` |
| **Partial** | Subset of documents | `createIndex({email:1}, {partialFilterExpression:{...}})` |

### Unique Index
```javascript
db.students.createIndex({email: 1}, {unique: true})
```

---

## 📖 6. Replication

### Official Definition

> **Replication** means maintaining copies of data on multiple MongoDB servers. A **replica set** is a group of MongoDB instances that maintain the same dataset.

### Replica Set Components

| Node | Role |
|------|------|
| **Primary** | Receives all writes, records oplog, replicates to secondaries |
| **Secondary** | Maintains copy of primary's data, can participate in elections |

### Read Preferences
- **Primary:** Read from primary only
- **Primary Preferred:** Primary first, then secondary
- **Secondary:** Read from secondary only
- **Secondary Preferred:** Secondary first
- **Nearest:** Read from lowest latency node

### Objectives
- High availability
- Fault tolerance
- Automatic failover
- Data redundancy

---

## 📖 7. Sharding

### Official Definition

> **Sharding** means distributing data across multiple servers. It is MongoDB's approach to horizontal scaling.

### Architecture

| Component | Role |
|-----------|------|
| **Mongos** | Query router — routes client requests to correct shard |
| **Config Servers** | Store metadata — which data is on which shard |
| **Shards** | Store actual data (each shard = replica set) |

### When to Shard
- Data volume exceeds single server capacity
- Write/read workload too high for one server
- Need horizontal scaling

### Shard Key
Determines how data is distributed across shards. Good shard key design is critical for even distribution.

---

## 📖 8. MongoDB Queries & Operators

### Comparison Operators
| Operator | Meaning | Example |
|----------|---------|---------|
| `$gt` | Greater than | `{cgpa: {$gt: 9}}` |
| `$gte` | Greater than or equal | `{cgpa: {$gte: 9}}` |
| `$lt` | Less than | `{cgpa: {$lt: 8}}` |
| `$lte` | Less than or equal | `{age: {$lte: 21}}` |
| `$in` | In list | `{dept: {$in: ["CSE","IT"]}}` |
| `$nin` | Not in list | `{dept: {$nin: ["CSE"]}}` |

### Logical Operators
| Operator | Meaning | Example |
|----------|---------|---------|
| `$or` | Either condition | `{$or: [{dept:"CSE"}, {dept:"IT"}]}` |
| `$and` | Both conditions | `{dept:"CSE", cgpa:{$gt:9}}` |

### Projection (select fields)
```javascript
db.students.find({}, {name: 1, cgpa: 1, _id: 0})
```

### Sorting, Limit, Skip
```javascript
db.students.find().sort({cgpa: -1}).limit(5).skip(3)
```

### Array Search
```javascript
db.students.find({skills: "Python"})
```

### Nested Document Search
```javascript
db.students.find({"marks.dbms": {$gt: 90}})
```

---

## 📖 9. Update & Delete Operators

### Update Operators
| Operator | Purpose | Example |
|----------|---------|---------|
| `$set` | Set/change value | `{$set: {cgpa: 8.9}}` |
| `$inc` | Increment | `{$inc: {cgpa: 0.1}}` |
| `$unset` | Remove field | `{$unset: {scholarship: ""}}` |
| `$push` | Add to array | `{$push: {skills: "Cloud"}}` |
| `$pull` | Remove from array | `{$pull: {skills: "Cloud"}}` |

### Import/Export
```bash
# Export to JSON
mongoexport --db=collegeDB --collection=students --out=students.json

# Export to CSV
mongoexport --db=collegeDB --collection=students --type=csv --fields=studentId,name,department --out=students.csv

# Import
mongoimport --db=collegeDB2 --collection=students --file=students.json --jsonArray
```

### Backup/Restore
```bash
mongodump --db=collegeDB --out=backup/
mongorestore --db=collegeDB_restore backup/collegeDB
```

---

## 📖 10. Aggregation Framework

### Pipeline Stages

| Stage | Purpose |
|-------|---------|
| `$match` | Filter documents |
| `$group` | Group by field, aggregate |
| `$sort` | Sort results |
| `$project` | Select/rename/compute fields |
| `$limit` | Limit number of results |
| `$count` | Count total documents |
| `$unwind` | Deconstruct array |

### Aggregate Operators
`$avg`, `$max`, `$min`, `$sum`, `$add`, `$multiply`

### Examples

**Count Students:**
```javascript
db.students.aggregate([{$count: "totalStudents"}])
```

**Average CGPA by Department:**
```javascript
db.students.aggregate([
  {$group: {_id: "$department", averageCGPA: {$avg: "$cgpa"}}}
])
```

**Filter + Group + Sort:**
```javascript
db.students.aggregate([
  {$match: {cgpa: {$gte: 8}}},
  {$group: {_id: "$department", avgCGPA: {$avg: "$cgpa"}}},
  {$sort: {avgCGPA: -1}}
])
```

**Calculate Total Marks ($project + $add):**
```javascript
db.students.aggregate([
  {$project: {
    name: 1,
    totalMarks: {$add: ["$marks.dbms", "$marks.bigdata", "$marks.ai"]}
  }}
])
```

---

## 🎯 EXAMINATION PERSPECTIVE

### Important Definitions
1. MongoDB, BSON, ObjectId, Document, Collection
2. Replica Set, Primary, Secondary, Read Preference
3. Sharding, Mongos, Config Server, Shard Key
4. Aggregation Pipeline

### Key Commands
- CRUD: insertOne, find, updateOne, deleteOne
- Index: createIndex
- Aggregation: aggregate with $match, $group, $sort, $project

### Potential 5-Mark Questions
1. Explain MongoDB document structure with BSON and flexible schema
2. Describe MongoDB replication with replica set architecture
3. Explain MongoDB sharding architecture
4. Write MongoDB queries for various operations (find, update, aggregate)
5. Explain aggregation framework with pipeline stages
