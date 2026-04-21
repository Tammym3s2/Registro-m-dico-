{
"Status Table"
{
      "role": "Integration Specialist",
      "status": "Blocked",
      "Responsibility": ["Comparison Operators"],
      "Key Deliverable": ["MQL Query Logic"]
    },
    {
      "role": "Query Developer",
      "status": "Completed",
      "Responsibility": ["Data Retrieval"],
      "Key Deliverable": [Regex & Filters]
    },
    {
      "role": "Lead Architect",
      "status": "Completed",
      "Responsibility": ["DB Structure"],
      "Key Deliverable": [English Schema]
    },
    {
      "role": "Data Seeder",
      "status": "In Progress",
      "Responsibility": ["Data Generation"],
      "Key Deliverable": [Mockaroo Config]
    }
    ### 1. Integration Specialist (Comparison Operators)
*   **Focus:** Advanced filtering and query logic using comparison operators.
*   **Technical Achievements:**
    *   Mastered the usage of `$gt` (greater than), `$lt` (less than), `$in` (in list), and `$ne` (not equal).
    *   Designed a specialized query to filter products by price and inventory levels.
*   **MQL Output:**
    ```javascript
    // Filter: price > 50 AND stock < 10
    db.products.find({
      price: { $gt: 50 },
      stock: { $lt: 10 }
    })
    ```
*   **Status:** 🔴 Blocked. Logic is verified, but database access is required for final execution.

### 2. Query Developer (MQL Architecture)
*   **Focus:** Optimization of data retrieval for the "Mundo Animal" Veterinary System.
*   **Technical Achievements:**
    *   **Species Segmentation:** Implemented logical filters to classify patients (canines, felines, etc.).
    *   **Chronological Analysis:** Developed Advanced Regex queries to filter medical records by month and year.
    *   **Contact Indexing:** Structured direct search logic by owner's phone number for emergency response.
*   **Outcome:** Improved response times for clinical administrative staff.

### 3. Lead Architect (Schema & Standardization)
*   **Focus:** Foundation and technical design of the NoSQL database.
*   **Technical Achievements:**
    *   **Entity Modeling:** Defined core collections: `pets` (patients), `medications` (inventory), and `sales` (transactions).
    *   **Global Standardization:** Successfully migrated the entire schema from Spanish to English to ensure scalability.
    *   **Transaction Logic:** Redesigned the sales JSON to support multiple items (services + products) in a single document.
*   **Refinement:** Resolved inconsistencies where professional services were being omitted from financial records.

### 4. Data Seeder (Synthetic Data Research)
*   **Focus:** Large-scale data generation and system stress testing.
*   **Research & Tools:**
    *   **Mockaroo:** Investigated "Custom Logic" to create conditional fields (e.g., country-specific postal codes).
    *   **Relational Datasets:** Developed a strategy to link `product_id` across different collections using JSON.
    *   **Automation:** Mastered `mongoimport` and `mongoexport` for bulk data loading via terminal.
*   **Edge Case Analysis:** Identified critical limits for field validation (nombres largos, formatos de correo extraños).
    }
