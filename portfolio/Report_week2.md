“Mundo Animal” Veterinary Management System
Week: (April 13-17)

**Rol The Data Modeler(Alejandra Porras)

This week, the main focus was on the architecture and technical design of the database in MongoDB. The necessary foundations were established to ensure the veterinary system is scalable and professional:
Entity Modeling: The three fundamental collections were defined and structured: pets for patient registration, medications for inventory control, and sales for transaction management.
Inventory Management: The medication collection was configured with unique identifiers (IDs), unit prices, and standardized medical categories.
Professional Transaction System: A sales structure was designed that allows linking professional services (such as consultations and grooming) with pharmacy products in a single accounting entry.

🧠 2. Challenges and Solutions
During the design process, significant challenges arose. Initially, the sales scheme presented a language inconsistency, mixing Spanish and English terms. This was resolved through a complete restructuring to unify the entire system under global standards.
Another challenge was the business logic in the sales collection; initially, the records only included pharmacy products, omitting the professional services that are the foundation of a veterinary practice. To address this, the sales JSON was redesigned to include an array of items capable of supporting multiple services and products simultaneously. Finally, meticulous work was done to ensure that each transaction was perfectly linked to the owners registered in the system, guaranteeing data consistency and eliminating orphaned records.

** Roll als Query Developer (Tammy Nashely)

As an MQL (MongoDB Query Language) Developer, I was responsible for designing, implementing, and optimizing the system's data retrieval layer. My primary focus was ensuring efficient communication between the Node.js server and the MongoDB Atlas cluster, enabling the administrative team to access critical patient information instantly.
Technical Implementations
I developed a query architecture focused on user flexibility, highlighting the following technical milestones:
* Species Segmentation: I implemented logical filters to classify the patient population (canines, felines, etc.), allowing for an organized visualization of the clinical workload.
* Advanced Chronological Analysis: I designed queries using regular expressions (Regex) to filter medical records by specific month and year, facilitating the generation of periodic visit reports.
* * Contact Indexing: I structured direct searches by owner's phone number, optimizing response times in urgent or follow-up situations.
All queries were tested to dynamically handle new database attributes, including specific physical traits and pet birth dates, ensuring a scalable and accurate system.

**Integration Specialist Role (Brayan Hernandez)

Activity Description.
This week, we worked with comparison operators in MongoDB, specifically:
$gt, $lt, $in, $ne, focusing on advanced queries and data filtering within the database.
The objective was to apply these operators in queries to obtain specific information from collections, particularly in numeric filtering and list scenarios.
Activities Performed.
I analyzed the query structure in MongoDB (MQL).
I reviewed advanced filtering examples in queries/02_filters.
I understood the use of comparison operators:

$gt (greater than)
$lt (less than)
$in (in list)
$ne (not equal)

I prepared the query logic requested in the exercise.
Limitations Encountered
I am currently not allowed to directly execute queries in the database, therefore:
I could not validate the query results in real time.
I had to work solely with the theoretical structure.
I'm waiting for database access to be enabled or updated to continue with practical testing.
Requested Exercise
Problem:
"I need to find products with a price greater than 50 AND stock less than 10."
Solution (MQL Query)

db.products.find({
price: { $gt: 50 },
stock: { $lt: 10 }
})

Explanation of the operators
$gt (greater than)
Filters documents where the price field is greater than 50.
$lt (less than)
Filters documents where the stock field is less than 10.
Both conditions are implicitly combined with an AND, since they are within the same object.
Expected Results
We expect to obtain all products that:
Have a price greater than 50
And a stock of less than 10 units

Conclusion
We successfully understood and correctly structured advanced queries in MongoDB using comparison operators. However, the lack of database access prevented practical validation, so we are awaiting access to continue with real-world testing.

**Role of The Data Seeler/QA (Ximena Rosas)

* Synthetic Data Generation:
Research how to create millions of records that appear real but cover all possible variations (long names, nonexistent addresses, emails with unusual formats).
* Edge Case Analysis:
Identify the system's limits. If a field accepts numbers from 1 to 100, your research focuses on what happens if you enter 0, 101, -1, 0, A, B, C, D, A, B, C, E, D, A, B, C, D, E, C, E, A, B, C, D, E ... * Related Datasets: How to generate linked JSON files (so that the product_id in the "Sales" collection actually exists in the "Products" collection).
B. MongoDB Shell & Compass
As a Data Seeder, you need to move data quickly:
* mongoimport / mongoexport: Terminal commands to load JSON/CSV files in bulk.

**scrum master (Annel Ricaño)

During the week, I managed the existing blocks to facilitate standardization. My goal was to do a brief retrospective of the block that occurred.

"issue": "No DB access for Integration Specialist",
"action": "Requested credentials to Atlas Admin",

After that, I created the report for the first week of work: Week_report.md
