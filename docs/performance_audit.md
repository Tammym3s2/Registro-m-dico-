# Database Performance Audit & Indexing Report (Week 16)
*Project:* Mundo Animal (Veterinary Management System)  
*Developer:* Tammy (Query Developer)  
*Date:* June 2, 2026  

---

## 1. Introduction and Technical Justification
During the development of the *Mundo Animal* backend architecture, data tier access speed is crucial. The primary goal of this audit report is to empirically demonstrate how indexing transforms database engine operations from resource-heavy linear lookups (*COLLSCAN) to efficient, tree-structured lookups (IXSCAN*). This step minimizes server workload and protects our Node.js/Express APIs against high-concurrency latencies as our records grow.

---

## 2. Case Study 1: Searching Patient Records by Name
This query simulates a standard operational request at the veterinary front desk, where a receptionist types a patient's name to fetch their medical record.

* *Audited Target Query:*
  ```javascript
  db.pets.find({ pet_name: "iris" }).explain("executionStats")

  ```

  ### Baseline Status (COLLSCAN)
Lacking an optimization key, MongoDB ran a full collection scan. It examined all 59 documents in the collection just to return the 1 matching document containing the pet name "iris". This establishes an inefficient $O(N)$ linear time complexity.

### Index Design Strategy (createIndex)
1. Navigated to the *"Indexes"* tab inside MongoDB Compass for the pets collection.
2. Clicked the interactive *"Create Index"* button.
3. Mapped the property key definition to the pet_name field.
4. Selected sorting property 1 (asc) (Ascending).
5. Saved and deployed the structure, successfully initializing the pet_name_1 index.

### Optimized Status (IXSCAN)
After clearing the database cache layer, re-evaluating the plan showed that the strategy shifted to *IXSCAN + FETCH*. MongoDB searched our new B-Tree index structure in RAM and examined strictly 1 document, achieving optimal 100% data access efficiency.

![imagen](/img/petname.png)

---

## 3. Case Study 2: Fetching Patient Records by Owner ID

This query simulates a dashboard lookup or an automated client workspace request where the application fetches all pet entities linked to an external owner profile reference.

*Audited Target Query:*

  ```

db.pets.find({ owner_id: "OWN-1778049152811" }).explain("executionStats")

  ```
### Baseline Status (COLLSCAN)
Before optimization, MongoDB Compass flagged a warning stating "No index available for this query". The query engine had to fall back to a full disk scan, processing all 59 records to filter the matches for that explicit customer reference.

### Index Design Strategy (createIndex)
1. Opened the index generation interface in Compass.
2. Defined the relational property attribute key as owner_id.
3. Picked constraint parameter 1 (asc) to index keys in contiguous memory blocks.
4. Formally saved the schema patch, resulting in the native active index owner_id_1.

### Optimized Status (IXSCAN)
Running the updated explain plan on the owner reference completely bypassed the raw database documents scan. The planner used the new owner_id_1 tree map, reducing documents examined from 59 to exactly 1, bringing the overall processing runtime down to $0\text{ ms}$.

![imagen](/img/ownerIXS.png)

---

## 4. Consolidated Performance Metrics Matrix

| Target Query Context | Metric Analyzed | Baseline (Before Index) | Optimized (After Index) | Production Impact & Outcome |
| :--- | :--- | :--- | :--- | :--- |
| *Case 1:* { pet_name: "iris" } | Execution Stage<br><br>Docs Examined<br><br>Structure Used | COLLSCAN<br><br>59 documents<br><br>None (Raw Data Table) | IXSCAN + FETCH<br><br>1 document<br><br>Index: pet_name_1 | Replaced blind brute-force table scanning with structural tree pointer search. |
| *Case 2:* { owner_id: "OWN-177..." } | Execution Stage<br><br>Docs Examined<br><br>Structure Used | COLLSCAN<br><br>59 documents<br><br>None (Raw Data Table) | IXSCAN + FETCH<br><br>1 document<br><br>Index: owner_id_1 | Instant grouping of nested relations, eliminating 98.3% of overhead disk reads. |

---

## 5. Query Developer Conclusion

By deploying the `pet_name_1` and `owner_id_1` index optimizations, the Mundo Animal data access layer is now scalable and prepared for production. Core system queries run at peak speed with a temporal complexity of $O(\log N)$, completely satisfying the software delivery standards for Week 16.

