# Sprint Backlog — Pet Management System

---

## Sprint Goal

> Develop and implement advanced MongoDB query operations for the pet management system, allowing efficient data retrieval, filtering, logical searching, and dynamic document updates while maintaining database consistency and document integrity throughout the system.

---

# Sprint 2 — "MongoDB Queries & Document Operations"

**Duration:** 4 weeks  
**Objective:** Implement MongoDB read, filtering, logical, and update operations to improve data management and querying within the pet management system.

---

## Sprint Parameters & Capacity Plan

* Sprint Duration: 4 weeks  
* Daily Commitment: 2 hours (Monday-Friday)  
* Total Sprint Capacity: 200 hours  
* Estimated Workload: 100 hours  
* Buffer: 100 hours  

---

## Sprint Backlog

| ID | User Story | Description | Priority | Estimation |
|----|-----------|-------------|----------|------------|
| SP2-01 | Basic Read Queries | Implement `find()` and `findOne()` queries for pet collections | High | 3 pts |
| SP2-02 | Projection Queries | Create projections to return only specific pet fields | Medium | 2 pts |
| SP2-03 | Advanced Filters | Add filtering using `$gt`, `$lt`, `$in`, and `$ne` operators | High | 4 pts |
| SP2-04 | Logical Queries | Implement complex searches using `$and`, `$or`, and `$not` | High | 4 pts |
| SP2-05 | Update Pet Information | Modify pet documents using `$set` and `$inc` | Medium | 3 pts |
| SP2-06 | Array Data Management | Add new medical records or comments using `$push` | Medium | 3 pts |
| SP2-07 | Query Testing & Optimization | Test and validate all MongoDB queries | Low | 2 pts |

**Total:** 21 points

---

## Sprint Acceptance Criteria

| Sprint Backlog ID | Acceptance Criteria | Validation Method |
|---|---|---|
| SP2-01 | `find()` and `findOne()` queries retrieve the correct pet records from collections. | Execute queries and verify returned documents in MongoDB Compass. |
| SP2-02 | Projection queries display only the requested fields without modifying original documents. | Compare query outputs with stored database records. |
| SP2-03 | Advanced filtering operators return accurate and properly filtered results. | Validate queries using multiple pet attributes and conditions. |
| SP2-04 | Logical operators correctly execute complex search conditions across collections. | Test combined conditions and review returned data consistency. |
| SP2-05 | Pet documents are updated correctly using `$set` and `$inc` operations. | Modify sample records and verify updates inside MongoDB Atlas. |
| SP2-06 | Array elements are inserted correctly using `$push` without affecting existing data. | Validate updated arrays in medical history and comments fields. |
| SP2-07 | All MongoDB queries execute efficiently and without errors. | Run testing sessions and validate query performance results. |

---

## Technical Tasks

### SP2-01 — Basic Read Queries
1. Create `find()` queries for pet collections
2. Implement `findOne()` searches
3. Validate returned documents
4. Test queries in MongoDB Compass

### SP2-02 — Projection Queries
1. Select specific fields from documents
2. Exclude unnecessary attributes
3. Validate projection outputs
4. Compare query responses

### SP2-03 — Advanced Filters
1. Apply `$gt` and `$lt` conditions
2. Implement `$in` queries
3. Use `$ne` exclusion filters
4. Validate filtered results

### SP2-04 — Logical Queries
1. Implement `$and` conditions
2. Create `$or` combinations
3. Apply `$not` filters
4. Test complex query logic

### SP2-05 — Update Pet Information
1. Modify fields using `$set`
2. Increment numeric values using `$inc`
3. Validate updated documents
4. Verify database consistency

### SP2-06 — Array Data Management
1. Insert new array elements using `$push`
2. Add medical history records
3. Insert pet comments
4. Validate array structures

### SP2-07 — Query Testing & Optimization
1. Execute query validation tests
2. Detect query execution errors
3. Optimize query performance
4. Verify database integrity

---

# Weekly Execution Roadmap

## Week 1: Basic Queries & Data Retrieval (Est. 8-10 Hours)

- *Focus:* Implementing MongoDB basic read operations and validating data retrieval processes.

- *Key Tasks:*
  - Create `find()` queries for pet collections.
  - Implement `findOne()` operations.
  - Test query execution inside MongoDB Compass.
  - Create projections for selected pet fields.
  - Validate retrieved document structures.

- *Friday Milestone:* Basic MongoDB queries working correctly and validated successfully.

---

## Week 2: Advanced Filters & Logical Operations (Est. 8-10 Hours)

- *Focus:* Applying advanced filtering and logical conditions to improve search functionality.

- *Key Tasks:*
  - Implement `$gt` and `$lt` filtering conditions.
  - Create queries using `$in` and `$ne`.
  - Develop logical queries using `$and`, `$or`, and `$not`.
  - Test combined filtering conditions.
  - Validate returned query results.

- *Friday Milestone:* Advanced filtering and logical queries implemented successfully.

---

## Week 3: Document Updates & Array Operations (Est. 6-8 Hours)

- *Focus:* Managing document modifications and array-based operations within collections.

- *Key Tasks:*
  - Update pet information using `$set`.
  - Increment values using `$inc`.
  - Add medical records with `$push`.
  - Validate document updates.
  - Verify array consistency after modifications.

- *Friday Milestone:* Document update and array operations functioning correctly.

---

## Week 4: Query Validation & Optimization (Est. 6-8 Hours)

- *Focus:* Testing query performance and validating database consistency.

- *Key Tasks:*
  - Execute complete query testing sessions.
  - Identify and correct query errors.
  - Optimize MongoDB query performance.
  - Validate collection consistency.
  - Organize repository documentation and scripts.

- *Friday Milestone:* MongoDB query system validated and optimized successfully.

---

## Expected Deliverables

- Functional MongoDB query scripts
- Advanced filtering operations
- Logical query implementations
- Updated pet documents
- Array management scripts
- Query validation documentation
- Optimized MongoDB operations

---

## Impediments & Dependencies

- *Dependency:* MongoDB Atlas connection must remain active before executing query and update operations.

- *Dependency:* Existing collections and seed data are required for validating filters and query conditions.

- *Dependency:* MongoDB Compass environment must be configured correctly before testing queries.

- *Impediment:* Incorrect MongoDB query syntax could generate execution errors.

- *Impediment:* Poor query optimization may affect database response time during testing.

---

## Definition of Done

* [x] All MongoDB queries execute correctly
* [x] Advanced filters validated successfully
* [x] Logical query operations implemented
* [x] Pet documents updated without errors
* [x] Array operations function properly
* [x] Query testing completed successfully
* [x] Repository documentation updated
* [x] Database consistency verified
