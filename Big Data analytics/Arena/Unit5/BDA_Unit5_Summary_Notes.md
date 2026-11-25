# BDA – Unit 5: MongoDB
## Summary Notes | OLMCA606

---

## 1. Important Definitions

**MongoDB:** Document-oriented NoSQL database storing data in JSON-like documents. Uses BSON internally.

**BSON (Binary JSON):** Binary-encoded JSON format used by MongoDB for efficient storage and more data types.

**ObjectId:** Auto-generated unique identifier containing creation time info. Default `_id` value.

**Collection:** Group of MongoDB documents (equivalent to a table in RDBMS).

**Replica Set:** Group of MongoDB instances maintaining the same dataset (Primary + Secondaries).

**Sharding:** Distributing data across multiple servers for horizontal scaling.

**Aggregation Pipeline:** Series of stages processing documents to produce computed results.

---

## 2. MongoDB vs Relational DB

| RDBMS | MongoDB |
|-------|---------|
| Table | Collection |
| Row | Document |
| Column | Field |
| Primary Key | _id |
| SQL | MQL |
| JOIN | Embedding / $lookup |
| Fixed schema | Flexible schema |

---

## 3. CRUD Operations

| Operation | Command |
|-----------|---------|
| Create | `db.collection.insertOne({})` |
| Read | `db.collection.find({condition})` |
| Update | `db.collection.updateOne({filter}, {$set: {field: value}})` |
| Delete | `db.collection.deleteOne({filter})` |

---

## 4. Query Operators

| Operator | Meaning |
|----------|---------|
| $gt, $gte | Greater than / Greater than or equal |
| $lt, $lte | Less than / Less than or equal |
| $in, $nin | In list / Not in list |
| $or | Either condition |
| $set | Set field value |
| $inc | Increment field |
| $push | Add to array |
| $pull | Remove from array |
| $unset | Remove field |

---

## 5. Indexes (7 Types)

Single-field, Compound, Multikey (arrays), Text, Geospatial, Hashed, Partial

---

## 6. Replication

- **Primary:** Receives writes, replicates to secondaries
- **Secondary:** Maintains copy, participates in elections
- **Auto failover** when primary fails
- **Read Preferences:** Primary, PrimaryPreferred, Secondary, SecondaryPreferred, Nearest

---

## 7. Sharding

| Component | Role |
|-----------|------|
| Mongos | Query router |
| Config Servers | Metadata storage |
| Shards | Data storage (each = replica set) |

---

## 8. Aggregation Pipeline

```
$match → $group → $sort → $project → $limit → $count
```

Key operators: $avg, $max, $min, $sum, $add

---

## 9. Import/Export/Backup

| Task | Command |
|------|---------|
| Export JSON | `mongoexport --db=X --collection=Y --out=file.json` |
| Export CSV | `mongoexport --db=X --collection=Y --type=csv --fields=a,b` |
| Import | `mongoimport --db=X --collection=Y --file=file.json` |
| Backup | `mongodump --db=X --out=backup/` |
| Restore | `mongorestore --db=X backup/X` |

---

## 10. Last-Minute Revision

```
MongoDB = Document NoSQL, BSON, flexible schema, _id=ObjectId
CRUD: insertOne, find, updateOne($set), deleteOne
Indexes: 7 types (single, compound, multikey, text, geo, hashed, partial)
Replication: Primary+Secondary, auto failover, 5 read preferences
Sharding: Mongos→Config→Shards, horizontal scaling
Queries: $gt/$lt/$in/$or, projection, sort, limit, skip
Aggregation: $match→$group($avg/$max/$min/$sum)→$sort→$project
```
