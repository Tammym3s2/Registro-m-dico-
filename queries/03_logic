# 🚀 Advanced Data Filtering Evidence - MongoDB

This document provides the **MQL (MongoDB Query Language)** queries and technical explanations for complex business logic. These scripts focus on inventory management, sales auditing, and clinical control for the **"Mundo Animal"** veterinary project.

---

### 🐱 1. High-Priority Patient Identification ($and)
* **Objective:** Identify specific feline patients that require indoor monitoring or specialized clinical attention.
* **Query:**
    ```javascript
    {
      $and: [
        { "pet.species": "cat" },
        { "specific_traits.is_indoor": true }
      ]
    }
    ```
* **Technical Detail:** The `$and` operator ensures both conditions are met. We use **Dot Notation** to access nested fields within the `pet` and `specific_traits` objects.
* **Business Value:** Allows the clinic to target specialized health campaigns for indoor cats.

---

### 💊 2. Strategic Inventory Control ($and)
* **Objective:** Detect affordable medications with high stock levels to optimize warehouse space and prevent over-purchasing.
* **Query:**
    ```javascript
    {
      $and: [
        { price: { $lt: 60 } },
        { stock: { $gt: 50 } }
      ]
    }
    ```
* **Technical Detail:** Combines two comparison operators (`$lt` for "Less Than" and `$gt` for "Greater Than") within a logical array.
* **Business Value:** Optimizes procurement by identifying low-cost items that do not require immediate restocking.

---

### 💰 3. Financial Audit & Liquidity ($or)
* **Objective:** Filter transactions representing high-value revenue or immediate cash liquidity for daily reconciliation.
* **Query:**
    ```javascript
    {
      $or: [
        { "total_amount": { $gte: 500 } },
        { "payment_method": "Cash" }
      ]
    }
    ```
* **Technical Detail:** The `$or` operator retrieves documents that satisfy **at least one** of the conditions provided in the array.
* **Business Value:** Essential for daily cash-till verification and identifying significant sales entries.

---

### 🛡️ 4. Preventive Health Screening ($and + Boolean)
* **Objective:** Locate specific animals (cats) with incomplete vaccination records.
* **Query:**
    ```javascript
    {
      $and: [
        { "pet.species": "cat" },
        { "specific_traits.complete_vaccinations": false }
      ]
    }
    ```
* **Technical Detail:** Matches a string literal and a boolean value. It strictly filters documents where the `complete_vaccinations` flag is set to `false`.
* **Business Value:** Triggers automated appointment reminders for pending vaccinations.

---

### 💳 5. Non-Cash Transaction Audit ($not)
* **Objective:** Isolate all sales processed via digital or alternative payment methods (Credit, Debit, Transfer).
* **Query:**
    ```javascript
    {
      payment_method: { $not: { $eq: "Cash" } }
    }
    ```
* **Technical Detail:** The `$not` operator inverts the query expression, selecting all documents where the `payment_method` is **not** equal to "Cash".
* **Business Value:** Facilitates the reconciliation of bank statements and digital terminal reports.

---

### 🐕 6. Multi-Pet Clinical Retrieval ($and + $or Nesting)
* **Objective:** Retrieve specific pet records belonging to a single owner for a group consultation.
* **Query:**
    ```javascript
    {
      $and: [
        { "owner.full_name": "Alejandra Porras" },
        { 
          $or: [
            { "pet.name": "Luna" },
            { "pet.name": "Michi" }
          ] 
        }
      ]
    }
    ```
* **Technical Detail:** Demonstrates **Nested Logical Operations**. It locks the search to a specific owner and then branches out to find either pet name within that owner's scope.
* **Business Value:** Improves staff efficiency when pulling clinical histories for multi-pet households.
