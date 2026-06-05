# Sprint Backlog — Pet Management System

---

## Sprint Goal

> Develop and validate MongoDB query operations for the pet management system, allowing users to retrieve, filter, update, and manage pet information efficiently through advanced NoSQL queries and document modification techniques.

---

# Sprint 2 — "MongoDB Queries & Document Operations"

**Duration:** 4 weeks  
**Objective:** Implement MongoDB query operations, apply advanced filters, and manage document updates within the pet management database.

---

## Sprint Parameters & Capacity Plan

* Sprint Duration: 4 weeks  
* Daily Commitment: 2 hours (Monday-Friday)  
* Total Sprint Capacity: 250 hours  
* Estimated Workload: 110 hours  
* Buffer: 90 hours  

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
| SP2-01 | `find()` and `findOne()` queries retrieve correct pet records from collections. | Execute queries and verify returned documents in MongoDB Compass. |
| SP2-02 | Projection queries display only the requested fields without affecting document integrity. | Compare query outputs with original documents. |
| SP2-03 | Advanced filters using `$gt`, `$lt`, `$in`, and `$ne` return accurate filtered results. | Test filters with different pet attributes and validate outputs. |
| SP2-04 | Logical queries using `$and`, `$or`, and `$not` perform complex searches correctly. | Execute combined conditions and verify query accuracy. |
| SP2-05 | Pet documents update correctly using `$set` and `$inc` operators. | Modify sample documents and confirm changes in database collections. |
| SP2-06 | New elements are successfully inserted into arrays using `$push`. | Validate array updates in medical records or comments collections. |
| SP2-07 | All queries execute without errors and return expected results efficiently. | Run query testing sessions and validate performance. |

---

## Technical Tasks

### SP2-01 — Basic Read Queries
1. Create `find()` queries for pet collections
2. Implement `findOne()` searches
3. Validate returned documents

### SP2-02 — Projection Queries
1. Select specific fields from pet documents
2. Exclude unnecessary attributes
3. Validate projection outputs

### SP2-03 — Advanced Filters
1. Apply `$gt` and `$lt` conditions
2. Implement `$in` operator queries
3. Use `$ne` for exclusion filters
4. Validate filtered results

### SP2-04 — Logical Queries
1. Implement `$and` conditions
2. Create `$or` search combinations
3. Use `$not` operator in filters
4. Test complex query structures

### SP2-05 — Update Pet Information
1. Update fields using `$set`
2. Increment numeric values with `$inc`
3. Validate document modifications

### SP2-06 — Array Data Management
1. Insert new array elements using `$push`
2. Add medical history records
3. Validate array integrity

### SP2-07 — Query Testing & Optimization
1. Execute query validation tests
2. Identify query errors
3. Optimize query performance
4. Verify database consistency

---

# Weekly Execution Roadmap

## Week 1: Basic Queries & Data Retrieval (Est. 8-10 Hours)

- *Focus:* Implementing basic MongoDB read operations and validating retrieved pet data.

- *Key Tasks:*
  - Create `find()` queries for pet collections.
  - Implement `findOne()` searches.
  - Test query outputs in MongoDB Compass.
  - Create projections for specific pet fields.
  - Validate returned documents and field visibility.

- *Friday Milestone:* Basic read queries functioning correctly with validated outputs.

---

## Week 2: Advanced Filtering & Logical Queries (Est. 8-10 Hours)

- *Focus:* Applying advanced MongoDB filters and logical conditions for complex searches.

- *Key Tasks:*
  - Implement `$gt` and `$lt` filters.
  - Create queries using `$in` and `$ne`.
  - Develop logical conditions with `$and`, `$or`, and `$not`.
  - Test combined query structures with different pet attributes.
  - Validate accuracy of filtered results.

- *Friday Milestone:* Advanced filtering and logical query operations working successfully.

---

## Week 3: Document Updates & Array Management (Est. 6-8 Hours)

- *Focus:* Managing document modifications and array operations within MongoDB collections.

- *Key Tasks:*
  - Update pet documents using `$set`.
  - Increment numeric values using `$inc`.
  - Add new medical records with `$push`.
  - Validate updated documents and array structures.
  - Test database consistency after updates.

- *Friday Milestone:* Document updates and array operations validated successfully.

---

## Week 4: Testing, Optimization & Validation (Est. 6-8 Hours)

- *Focus:* Final testing, query optimization, and sprint validation.

- *Key Tasks:*
  - Execute complete query testing sessions.
  - Identify and fix query execution errors.
  - Optimize MongoDB query performance.
  - Validate database integrity and consistency.
  - Organize repository documentation and scripts.

- *Friday Milestone:* MongoDB queries optimized and sprint deliverables completed.

---

## Expected Deliverables

- Functional MongoDB query scripts
- Advanced filtering operations
- Logical query implementations
- Updated pet documents
- Array management operations
- Query testing documentation
- Optimized database queries

---

## Impediments & Dependencies

- *Dependency:* MongoDB Atlas connection must remain active before executing query and update operations.

- *Dependency:* Existing pet collections and seed data are required for testing filters and logical queries.

- *Dependency:* MongoDB Compass environment must be configured before validating query outputs.

- *Impediment:* Incorrect query syntax may generate execution or filtering errors.

- *Impediment:* Poorly optimized queries could affect database response time during testing.

---

## Definition of Done

* [x] All MongoDB queries execute correctly
* [x] Advanced filters validated successfully
* [x] Logical queries return accurate results
* [x] Pet documents updated without errors
* [x] Array operations function properly
* [x] Query testing completed successfully
* [x] Repository documentation updated
* [x] Database consistency verified
