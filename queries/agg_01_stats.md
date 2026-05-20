# Deliverable Report: S14 - Introduction to Aggregation

**Role:** Query Developer (MQL Constructor)  
**Project:** Mundo Animal  
**Week:** S14 (May 18–22)  

---

## 1. Key Concepts

* **Aggregation Pipeline:** A framework that processes documents in sequential stages (like a factory conveyor belt). Each stage transforms the data and passes the result to the next one.
* **Difference from `find()`:** The `find()` function only searches for and returns documents exactly as they are stored. Meanwhile, `aggregate()` transforms the data, allowing you to group it by categories and perform analytical calculations (such as sums or counts).
* **Operators Used:**
    * `$match`: Filters input documents based on a specific condition.
    * `$group`: Classifies documents by a common field (`_id`) and calculates accumulated totals.
    * `$count`: Directly counts the absolute total of documents that successfully reach that stage.

---

## 2. Pipelines Executed in "Mundo Animal"

### Query A: Metrics by Payment Method (Grouping and Sum)

Filters sales greater than zero and groups them by payment method to obtain total revenue and transaction volume.

```javascript
[
  {
    $match: {
      total_amount: { $gt: 0 }
    }
  },
  {
    $group: {
      _id: "$payment_method",
      cantidad_pagos: { $sum: 1 },
      ingresos_totales: { $sum: "$total_amount" }
    }
  }
]
