# BDA – Unit 5: Practice Questions & Active Recall Quiz

---

## Part A: 1-Mark MCQs

**Q1.** MongoDB stores data internally in which format?
- (A) JSON  (B) BSON  (C) XML  (D) CSV

**Q2.** The default unique identifier in MongoDB is:
- (A) Primary Key  (B) UUID  (C) ObjectId  (D) Auto-increment ID

**Q3.** Which operator is used to increment a field value in MongoDB?
- (A) $set  (B) $add  (C) $inc  (D) $update

**Q4.** In MongoDB replication, which node receives all write operations?
- (A) Secondary  (B) Arbiter  (C) Primary  (D) Config Server

**Q5.** Which component routes queries in MongoDB sharding?
- (A) Config Server  (B) Shard  (C) Mongos  (D) Replica Set

**Q6.** Which query finds students with CGPA greater than 9?
- (A) find({cgpa: 9})  (B) find({cgpa: {$gt: 9}})  (C) find({cgpa: >9})  (D) find({cgpa: $greater: 9})

**Q7.** Which MongoDB operator adds an element to an array?
- (A) $add  (B) $append  (C) $push  (D) $insert

**Q8.** In aggregation, which stage filters documents?
- (A) $group  (B) $match  (C) $sort  (D) $project

**Q9.** Which command creates a compound index on department and age?
- (A) createIndex({department:1, age:1})
- (B) createIndex({department:1, age:-1})
- (C) Both A and B
- (D) createIndex(department, age)

**Q10.** Which tool is used for MongoDB database backup?
- (A) mongoexport  (B) mongodump  (C) mongosave  (D) mongobackup

---

## Part B: 2-Mark Questions

**Q11.** Differentiate between Embedding and Referencing in MongoDB.

**Q12.** What is BSON? Why does MongoDB use it instead of JSON?

**Q13.** Explain the difference between Managed and External tables. *(Hive - quick recall)*
What is the difference between `drop` and `truncate` in MongoDB?

**Q14.** What is a Replica Set in MongoDB? What are its components?

**Q15.** Explain the purpose of the `$group` stage in aggregation with an example.

---

## Part C: 5-Mark Descriptive Questions

**Q16.** Explain MongoDB document structure with BSON, ObjectId, flexible schema, and embedded documents.

**Q17.** Describe MongoDB replication architecture with primary, secondary nodes, and read preferences.

**Q18.** Explain MongoDB sharding architecture with its components. When would you use sharding?

**Q19.** Write MongoDB queries for: finding students by department, CGPA range, array search, nested document, projection, and sorting.

**Q20.** Explain the MongoDB aggregation framework with pipeline stages. Give an example of filter + group + sort.

---

## 📝 ANSWER KEY

### Part A
1. (B) BSON  2. (C) ObjectId  3. (C) $inc  4. (C) Primary
5. (C) Mongos  6. (B) find({cgpa: {$gt: 9}})  7. (C) $push  8. (B) $match
9. (C) Both A and B  10. (B) mongodump

### Part B — Model Answers

**Q11. Embedding vs Referencing:**
- Embedding stores related data inside the same document. Good when accessed together, manageable size.
- Referencing stores related data in separate documents with ID reference. Good when data is large, shared, or independently updated.

**Q12. BSON:**
BSON = Binary JSON. MongoDB uses it because: supports more data types (Date, ObjectId, Binary), efficient storage and traversal, binary encoding is faster to process than text JSON.

**Q13. drop vs truncate:**
- `drop`: Removes entire collection including structure.
- `truncate` (deleteMany({})): Removes all documents but keeps collection structure.

**Q14. Replica Set:**
A group of MongoDB instances maintaining the same dataset. Components: Primary (receives writes, replicates), Secondary (maintains copy, participates in elections). Provides high availability and automatic failover.

**Q15. $group stage:**
Groups documents by a specified expression and applies accumulator operators. Example: `{$group: {_id: "$department", averageCGPA: {$avg: "$cgpa"}}}` — groups by department and calculates average CGPA.

### Part C — Answer Outlines

**Q16. Document Structure (5 Marks):** Define MongoDB → BSON explanation → ObjectId → Flexible schema with example → Arrays and embedded documents → Embedding vs referencing → Conclusion

**Q17. Replication (5 Marks):** Define replication → Replica set → Primary node role → Secondary nodes role → Automatic failover → Read preferences (5 types) → Use cases → Conclusion

**Q18. Sharding (5 Marks):** Define sharding → When to shard → Architecture (Mongos, Config Servers, Shards) → Shard key concept → Diagram → Conclusion

**Q19. Queries (5 Marks):** 6 query types with syntax and examples: find with department, CGPA range ($gt/$lt), array search, nested document (dot notation), projection, sorting → Conclusion

**Q20. Aggregation (5 Marks):** Define aggregation pipeline → List stages ($match, $group, $sort, $project, $limit, $count) → Aggregate operators → Filter+Group+Sort example → Conclusion
