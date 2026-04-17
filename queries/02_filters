# Advanced Data Filtering Evidence - MongoDB

This document provides the MQL (MongoDB Query Language) queries and technical explanations for inventory management, sales auditing, and chronological control.

---

### 💰 1. High-Value Sales Analysis
* **Objective:** Identify transactions that exceed a specific amount for revenue auditing.
* **Query:** `{ total_amount: { $gt: 300 } }`
* **Operator:** `$gt` (Greater Than) - Filters documents where the amount is strictly greater than 300.
(./img/evidencia1.png)
---

### 💊 2. Critical Stock Control (Medicines)
* **Objective:** Detect products with low stock to generate replenishment alerts.
* **Query:** `{ stock: { $lt: 100 } }`
* **Operator:** `$lt` (Less Than) - Filters records with a quantity of less than 100 units.
(./img/evidencia2.png)
---

### 🏷️ 3. Premium Products with Low Inventory
* **Objective:** Find high-cost products that are running out of stock.
* **Query:** ```javascript
  { 
    price: { $gt: 50 }, 
    stock: { $lt: 10 } 
  }
