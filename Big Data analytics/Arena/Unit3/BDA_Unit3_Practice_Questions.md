# BDA – Unit 3: Practice Questions & Active Recall Quiz

---

## Part A: 1-Mark MCQs

**Q1.** MapReduce was originally developed by which company?
- (A) Yahoo!  (B) Google  (C) IBM  (D) Apache

**Q2.** What is the default block size used for input splitting in Hadoop?
- (A) 64 MB  (B) 128 MB  (C) 256 MB  (D) 512 MB

**Q3.** The Combiner in MapReduce is:
- (A) Mandatory  (B) Optional  (C) Same as Reducer  (D) Runs after Reducer

**Q4.** Which component determines which Reducer receives Mapper output?
- (A) Combiner  (B) Partitioner  (C) NameNode  (D) ResourceManager

**Q5.** YARN stands for:
- (A) Yet Another Resource Node  (B) Yet Another Resource Negotiator
- (C) Yahoo! Application Resource Node  (D) Yielding Application Resource Network

**Q6.** In Classic MapReduce, which daemon was the bottleneck?
- (A) TaskTracker  (B) NameNode  (C) JobTracker  (D) NodeManager

**Q7.** The damping factor 'd' in PageRank is typically:
- (A) 0.50  (B) 0.75  (C) 0.85  (D) 0.95

**Q8.** In Matrix Multiplication using MapReduce, C[0][0] for A=[1,2;3,4] and B=[5,6;7,8] is:
- (A) 15  (B) 19  (C) 22  (D) 43

**Q9.** Which YARN component runs on every worker node?
- (A) ResourceManager  (B) ApplicationMaster  (C) NodeManager  (D) Scheduler

**Q10.** In SQL Join using MapReduce, tagged records use:
- (A) Row ID as key  (B) Join column as key  (C) Table name as key  (D) Random key

---

## Part B: 2-Mark Questions

**Q11.** Differentiate between Combiner and Reducer in MapReduce.

**Q12.** What is the formula used by HashPartitioner? Give an example.

**Q13.** List the components of YARN and briefly describe each.

**Q14.** What is the PageRank formula? Define each variable.

**Q15.** How does MapReduce perform Matrix Multiplication? Explain briefly.

---

## Part C: 5-Mark Descriptive Questions

**Q16.** Explain the six phases of MapReduce with a suitable example.

**Q17.** Describe the YARN architecture. How is it different from Classic MapReduce framework?

**Q18.** Explain the Word Count problem using MapReduce with step-by-step key-value pairs at each phase.

**Q19.** Describe how Matrix Multiplication can be implemented using MapReduce. Show calculations for a 2×2 example.

**Q20.** Explain how SQL Join (INNER JOIN and LEFT OUTER JOIN) can be performed using MapReduce.

---

## 📝 ANSWER KEY

### Part A Answers
1. **(B)** Google  2. **(B)** 128 MB  3. **(B)** Optional  4. **(B)** Partitioner
5. **(B)** Yet Another Resource Negotiator  6. **(C)** JobTracker  7. **(C)** 0.85
8. **(B)** 19  9. **(C)** NodeManager  10. **(B)** Join column as key

### Part B — Model Answers

**Q11. Combiner vs Reducer:**
- **Combiner** performs local aggregation of Mapper output on the same node. Reduces network traffic. Optional. Runs before Shuffle. Output is intermediate.
- **Reducer** performs global aggregation across all Mappers. Required. Runs after Shuffle. Output is final.

**Q12. HashPartitioner formula:** `partition = hash(key) % number_of_reducers`
Example: 3 Reducers, key = "India" → hash("India") % 3 = 1 → goes to Reducer 1.

**Q13. YARN Components:**
- **ResourceManager:** Global resource management, has Scheduler and ApplicationsManager
- **NodeManager:** Per-worker-node, manages local resources and containers
- **ApplicationMaster:** Per-application, negotiates resources and coordinates tasks
- **Container:** Resource bundle (CPU + memory) where tasks execute

**Q14. PageRank Formula:** `PR(A) = (1-d)/N + d × Σ PR(Ti)/C(Ti)`
- d = damping factor (0.85)
- N = total pages
- Ti = pages linking to A
- C(Ti) = outgoing links from Ti

**Q15. Matrix Multiplication:** Each element stored as (Matrix,Row,Col,Value). Mapper emits partial products A[i][k]×B[k][j] keyed by (i,j). Reducer sums all partial products for each cell.

### Part C — Answer Outlines

**Q16. Six Phases (5 Marks):** Define MapReduce → Each phase with description → 512MB example (4 splits) → Key-value at each stage → Conclusion

**Q17. YARN vs Classic (5 Marks):** Draw YARN architecture → RM, NM, AM, Containers → Classic: JobTracker+TaskTracker → Comparison table → Benefits of YARN → Conclusion

**Q18. Word Count (5 Marks):** Input text → Map output with key-value pairs → Combiner (optional) → Shuffle grouping → Reduce summation → Final output → Conclusion

**Q19. Matrix Multiplication (5 Marks):** Formula C[i][j] → Input format → Map partial products → Reduce sum → 2×2 worked example with all 4 cells → Conclusion

**Q20. SQL Join (5 Marks):** Two tables → Map with tagged records → Shuffle by join key → Reduce matching → INNER vs LEFT OUTER → Example → Conclusion
