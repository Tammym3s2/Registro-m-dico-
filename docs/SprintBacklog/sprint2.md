# Sprint 2 — "Advanced Querying & Data Management"

---

## Duration
2 weeks

## Goal

Improve the pet management system by implementing advanced MongoDB queries, logical operators, document updates, and data mutation processes to manage heterogeneous pet information efficiently.

---

## Sprint Goal

> Allow administrators and users to perform advanced searches, logical filtering, and dynamic updates on pet records while maintaining flexible NoSQL structures.

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

- Users can retrieve pet information using `find()` and `findOne()`
- Queries correctly filter documents using comparison operators
- Logical operators return accurate results
- Pet documents can be updated without rewriting the full document
- Array fields support dynamic insertion using `$push`
- All queries execute successfully without syntax errors

---

## Definition of Done

- Queries tested in MongoDB Compass and Mongo Shell
- Scripts uploaded to GitHub repository
- No syntax or execution errors
- Query documentation completed
- Release v2.0 tag created
- Functional query scripts included in `/queries` and `/scripts`

---

## Technical Tasks

### SP2-01 — Basic Read Queries
1. Create `queries/01_simple_find.mongodb`
2. Implement `find()` examples
3. Implement `findOne()` examples
4. Test queries with pet collections

### SP2-02 — Projection Queries
1. Create projection queries for specific fields
2. Hide unnecessary fields using projections
3. Optimize returned data

### SP2-03 — Advanced Filters
1. Create `queries/02_filters.mongodb`
2. Use `$gt` for greater-than conditions
3. Use `$lt` for less-than conditions
4. Use `$in` for list filtering
5. Use `$ne` for exclusion filtering

### SP2-04 — Logical Queries
1. Create `queries/03_logic.mongodb`
2. Implement `$and` conditions
3. Implement `$or` conditions
4. Implement `$not` conditions
5. Test business logic queries

### SP2-05 — Update Pet Information
1. Create `scripts/update_data.js`
2. Use `$set` to modify pet attributes
3. Use `$inc` to update counters or quantities
4. Validate updated documents

### SP2-06 — Array Data Management
1. Create arrays for medical history or comments
2. Use `$push` to insert new elements
3. Verify array updates without replacing documents

### SP2-07 — Query Testing & Optimization
1. Validate all queries in MongoDB Compass
2. Analyze query performance
3. Fix syntax or logic issues
4. Prepare RELEASE v2.0 documentation

---

## Technologies Used

- MongoDB
- MongoDB Compass
- MongoDB Atlas
- Mongo Shell
- JavaScript
- Git & GitHub
- JSON/BSON

---

## Expected Deliverables

- Functional MongoDB query scripts
- Advanced filtering system
- Logical query implementation
- Update and mutation scripts
- Documented query collection
- RELEASE v2.0 ready for presentation

---

## Sprint Summary

| Sprint | Goal | Stories | Points | Duration |
|--------|------|---------|--------|----------|
| Sprint 1 | Project Setup & NoSQL Foundations | 9 | 20 pts | 2 weeks |
| Sprint 2 | Advanced Querying & Data Management | 7 | 21 pts | 2 weeks |
