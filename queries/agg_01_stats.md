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

]```



**Compass Result:**

* Card (`"card"`) recorded 3 payments totaling $2,400.

* Cash (`"oxxo"`) recorded 5 payments totaling $7,800.



### Query B: Popularity and Revenue by Service (Grouping and Sum)

Classifies and accumulates financial revenue and sales volume based on the type of service provided at the veterinary clinic.



```javascript

[

  {

    $match: {

      servicie: { $exists: true, $ne: "" }

    }

  },

  {

    $group: {

      _id: "$servicie",

      veces_vendido: { $sum: 1 },

      total_recaudado: { $sum: "$total_amount" }

    }

  }

]```



**Compass Result:**

* `"Baño y Corte"` (Bath & Grooming) recorded 1 sale of $170.5.

* `"Hospitalizacion"` (Hospitalization) recorded 1 sale of $140.



### Query C: Total Cash Sales (Absolute Count)

Isolates transactions via a filter and directly counts in a single stage how many total sales were made under the "Cash" payment label.



```javascript

[

  {

    $match: {

      payment_method: "Cash"

    }

  },

  {

    $count: "total_ventas_efectivo"

  }

]```



**Compass Result:**

* The system returned a consolidated count of 18 cash sales.



---



## Conclusion

The implemented pipelines optimize server load by filtering data with the `$match` operator before processing it with `$group` or `$count`. This successfully meets the requirements of the Analytics phase for the project 

