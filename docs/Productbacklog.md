### Product Backlog
# Mundo Animal: Veterinary Management System Product Backlog

## Product Goal
> "To build a scalable and efficient veterinary management system using MongoDB, allowing staff to register pets, owners, medications, and sales while ensuring fast data access, accurate medical records, and optimized reporting."

---

## User Stories

### User Story #1: Register a New Pet
**Description:**  
*As a* veterinary assistant,  
*I want to* register a new pet with its owner information,  
*So that* all patient data is stored in one document and can be accessed quickly.

**Acceptance Criteria:**  
* **Scenario 1: Successful registration**
  * **Given** the user is in the pets module,  
  * **When** they enter the pet’s information and owner details,  
  * **Then** the system must save the data in the `pets` collection as a nested JSON document.  

* **Scenario 2: Required fields validation**
  * **Given** the registration form is open,  
  * **When** the user leaves required fields empty,  
  * **Then** the system must prevent saving and show an error message.  

* **Scenario 3: Data persistence**
  * **Given** the pet was registered successfully,  
  * **When** the collection is opened in MongoDB Atlas,  
  * **Then** the document must appear correctly in JSON format.  

---

### User Story #2: Search Pets by Species
**Description:**  
*As a* veterinary administrator,  
*I want to* filter pets by species,  
*So that* I can organize patients according to their type.

**Acceptance Criteria:**  
* **Scenario 1: Filter by species**
  * **Given** the pets collection contains multiple species,  
  * **When** the user runs a query by species,  
  * **Then** only matching records must be displayed.  

* **Scenario 2: Multiple species query**
  * **Given** the collection contains birds and reptiles,  
  * **When** the user uses the `$or` operator,  
  * **Then** both matching species must be returned.  

---

### User Story #3: Search by Owner Phone Number
**Description:**  
*As a* veterinary employee,  
*I want to* search pets by owner phone number,  
*So that* I can quickly contact the owner in emergencies.

**Acceptance Criteria:**  
* **Scenario 1: Direct search**
  * **Given** the owner’s phone number exists,  
  * **When** the query is executed,  
  * **Then** the associated pet record must be displayed.  

* **Scenario 2: Invalid number**
  * **Given** the number does not exist,  
  * **When** the query is executed,  
  * **Then** no results must be returned.  

---

### User Story #4: Manage Medication Inventory
**Description:**  
*As a* veterinary administrator,  
*I want to* register medications with stock and prices,  
*So that* inventory can be controlled efficiently.

**Acceptance Criteria:**  
* **Scenario 1: Add medication**
  * **Given** the user is in the medications module,  
  * **When** they enter medication details,  
  * **Then** the system must store it in the `medications` collection.  

* **Scenario 2: Stock filtering**
  * **Given** medications have stock values,  
  * **When** the user runs a query with `$lt`,  
  * **Then** only medications with low stock must appear.  

---

### User Story #5: Register a Sale
**Description:**  
*As a* cashier,  
*I want to* register a sale containing services and products,  
*So that* all veterinary transactions are recorded.

**Acceptance Criteria:**  
* **Scenario 1: Add new sale**
  * **Given** the sales form is open,  
  * **When** the user enters services and products,  
  * **Then** the system must save them inside an `items` array.  

* **Scenario 2: Link to owner**
  * **Given** a sale is saved,  
  * **When** the record is reviewed,  
  * **Then** it must be linked to the correct owner ID.  

---

### User Story #6: Update Medical History
**Description:**  
*As a* veterinarian,  
*I want to* add new medical history entries to a pet record,  
*So that* the clinical history remains updated.

**Acceptance Criteria:**  
* **Scenario 1: Add history entry**
  * **Given** the pet document exists,  
  * **When** the user uses `$push`,  
  * **Then** the new entry must be appended without overwriting previous records.  

* **Scenario 2: Verify latest record**
  * **Given** the pet has multiple history entries,  
  * **When** the user applies `$slice`,  
  * **Then** only the most recent entry must be shown.  

---

### User Story #7: Generate Reports
**Description:**  
*As a* veterinary manager,  
*I want to* generate reports using aggregation pipelines,  
*So that* I can analyze sales and patient statistics.

**Acceptance Criteria:**  
* **Scenario 1: Count patients**
  * **Given** the pets collection has records,  
  * **When** the user runs `$count`,  
  * **Then** the total number of patients must be displayed.  

* **Scenario 2: Group sales**
  * **Given** the sales collection contains multiple transactions,  
  * **When** the user runs `$group`,  
  * **Then** sales totals by category must be generated.  

---

### User Story #8: Optimize Query Performance
**Description:**  
*As a* system administrator,  
*I want to* create indexes on frequently queried fields,  
*So that* search results are faster.

**Acceptance Criteria:**  
* **Scenario 1: Create index**
  * **Given** the pets collection exists,  
  * **When** an index is created on `owner.phone`,  
  * **Then** query execution time must decrease.  

* **Scenario 2: Compare performance**
  * **Given** the query is tested before and after indexing,  
  * **When** `.explain("executionStats")` is executed,  
  * **Then** the improvement must be documented in `performance_audit.md`.  
