# Sprint Backlog — Pet Management System

---

## Sprint Goal

> Implement MongoDB querying and document mutation features for the pet management system, allowing users to retrieve specific pet records, apply advanced filters based on species characteristics, execute logical search conditions, and update pet information dynamically without affecting document integrity.

---

# Sprint 1 — "Project Setup & NoSQL Foundations"

**Duration:** 2 weeks  
**Objective:** Configure the development environment, understand NoSQL fundamentals, and establish the initial project architecture.

---

## Sorint Paramentrer & Capacity Plan
* Sprint Duration: 2 week
* Daily Commitment: 2 hours (Monday-Friday)
* Total Sprint Capacity: 40 hours
* Estimated Workload: 20 hours
* Buffer: 20 hours

---

## Sprint Backlog

| ID | Story | Description | Priority | Estimate |
|----|-------|-------------|----------|----------|
| SP1-01 | Development Environment Setup | Install and configure VS Code, MongoDB Compass, and Git | High | 2 pts |
| SP1-02 | Initial Repository Setup | Create repository with README.md and signed Student Pledge | High | 1 pt |
| SP1-03 | JSON/BSON Fundamentals | Create valid JSON structures representing real-world entities | High | 2 pts |
| SP1-04 | Project Idea Definition | Define the ABP project idea and system requirements | Medium | 2 pts |
| SP1-05 | Schema Modeling | Design ER diagram using Mermaid.js | High | 3 pts |
| SP1-06 | MongoDB Atlas Integration | Create MongoDB Atlas cluster and connect database | High | 3 pts |
| SP1-07 | Collection Initialization Script | Create initialization script for collections | Medium | 2 pts |
| SP1-08 | Seed Data Generation | Generate test dataset with +50 documents | Medium | 3 pts |
| SP1-09 | Architecture Defense Preparation | Prepare project documentation and repository for release v1.0 | Low | 2 pts |

**Total:** 20 points

---

## Sprint Acceptance Criteria

- VS Code, Git, and MongoDB Compass are correctly installed
- Repository contains README.md with signed Student Pledge
- JSON files are valid and correctly formatted
- Mermaid.js ER diagram accurately represents the database schema
- MongoDB Atlas cluster is connected successfully
- Collections are initialized without errors
- Seed dataset contains at least 50 valid documents
- Repository is ready for RELEASE v1.0

---

## Definition of Done

* [x] All scripts execute without errors
* [x] Database connection works correctly
* [x] JSON/BSON structures validated
* [x]  Repository uploaded to GitHub
* [x] Documentation completed
* [x] MongoDB collections created successfully
* [x] Seed data inserted correctly into database

---

## Technical Tasks

### SP1-01 — Development Environment Setup
1. Install VS Code
2. Install MongoDB Compass
3. Install Git
4. Configure GitHub repository access

### SP1-02 — Initial Repository Setup
1. Create `README.md`
2. Add signed Student Pledge
3. Perform Initial Commit

### SP1-03 — JSON/BSON Fundamentals
1. Create `portfolio/me.json`
2. Define nested objects and arrays
3. Validate JSON syntax

### SP1-04 — Project Idea Definition
1. Define project objectives
2. Identify system requirements
3. Analyze heterogeneous pet data needs

### SP1-05 — Schema Modeling
1. Design ER diagram using Mermaid.js
2. Compare Embedding vs Referencing
3. Define collections relationships

### SP1-06 — MongoDB Atlas Integration
1. Create free MongoDB Atlas cluster
2. Configure database user
3. Obtain Connection String
4. Connect Compass to Atlas

### SP1-07 — Collection Initialization
1. Create `scripts/01_create_collections.js`
2. Initialize collections
3. Verify database structure

### SP1-08 — Seed Data Generation
1. Create `data/seeds.json`
2. Generate +50 test documents
3. Insert seed data into collections

### SP1-09 — Architecture Defense
1. Review repository structure
2. Validate loaded data
3. Create RELEASE v1.0 tag

---
# Weekly Execution Roadmap

## Week 1: Environment Setup & NoSQL Foundations (Est. 8-10 Hours)

- *Focus:* Setting up the development environment and defining the foundational architecture for the pet management system.

- *Key Tasks:*
  - Install and configure VS Code, Git, and MongoDB Compass.
  - Create the GitHub repository with README.md and signed Student Pledge.
  - Create portfolio/me.json with valid JSON/BSON structures.
  - Define the main objectives and requirements of the pet management system.
  - Analyze heterogeneous pet data requirements for different animal species.

- *Friday Milestone:* Development environment fully configured and repository initialized successfully.

---

## Week 2: Database Modeling & MongoDB Integration (Est. 8-10 Hours)

- *Focus:* Designing the NoSQL schema and integrating MongoDB Atlas for database management.

- *Key Tasks:*
  - Design the ER diagram using Mermaid.js.
  - Compare Embedding vs Referencing strategies for pet-related data.
  - Create MongoDB Atlas free cluster and configure database access.
  - Obtain and secure the MongoDB Connection String.
  - Connect MongoDB Compass with Atlas successfully.
  - Create scripts/01_create_collections.js for collection initialization.

- *Friday Milestone:* MongoDB Atlas connected successfully and collections created correctly.

---

## Week 3: Data Initialization & Seed Management (Est. 6-8 Hours)

- *Focus:* Generating test data and validating database structures.

- *Key Tasks:*
  - Create data/seeds.json with more than 50 test documents.
  - Insert seed data into MongoDB collections.
  - Validate JSON/BSON document structures.
  - Verify database integrity and collection relationships.
  - Test initialization scripts without execution errors.

- *Friday Milestone:* Database populated with valid seed data and scripts functioning correctly.

---

## Week 4: Documentation, Validation & Release v1.0 (Est. 6-8 Hours)

- *Focus:* Final validation, repository organization, and sprint closure.

- *Key Tasks:*
  - Review repository structure and project organization.
  - Validate all scripts and MongoDB queries.
  - Complete technical documentation and schema descriptions.
  - Verify GitHub uploads and version control history.
  - Prepare RELEASE v1.0 tag for deployment and presentation.

- *Friday Milestone:* Project documentation completed and RELEASE v1.0 ready for submission.
  
---

## Expected Deliverables

- Functional GitHub repository
- Configured MongoDB Atlas cluster
- Database schema diagram
- Initialization scripts
- Seed dataset
- RELEASE v1.0 ready for deployment

---

## Impediments & Dependencies

- *Dependency:* MongoDB Atlas connection and GitHub repository access must be configured before initializing collections and executing database scripts.

- *Dependency:* JSON/BSON validation is required before inserting documents into MongoDB collections.

- *Dependency:* MongoDB Compass and VS Code environment setup must be completed before executing query and initialization scripts.

- *Impediment:* Possible connection issues between MongoDB Compass and MongoDB Atlas due to incorrect Connection String configuration.

- *Impediment:* Inconsistent or invalid JSON syntax could generate insertion errors during seed data loading.
