“Mundo Animal” Veterinary Management System 
Week: (April 20–29)

**Role of the Data Modeler (Alejandra Porras).
This week, the work focused on debugging the pets collection within the MongoDB Atlas cluster. The main objective was to maintain the records of owners and pets, ensuring that contact and health information were properly linked.
2. Log of Questions and Technical Challenges
During the process, key obstacles arose that required an in-depth analysis of the database architecture:

Monday 20 - Tuesday 21: Interface Confusion (Query vs. Command)

Question: Why was the platform displaying syntax errors (red borders) when attempting to execute update commands?
Finding: It was identified that the work was being done on the Filters bar (Query Bar), which is limited exclusively to reading. To make structural or data changes through code, the use of Mongosh or external administration tools is essential.

Wednesday 22 - Thursday 23: Identifying Field Paths (Dot Notation)
Question: Search filters were not returning results even when the correct ID was entered.
Finding: After reviewing the JSON documents, it was confirmed that the information is not "flat." The data is organized into nested objects. For example, the owner's ID does not reside in the root object, but within a sub-object called `owner`. This forced a rethink of how the information is accessed.

Friday 24: Terminal Syntax Errors
Question: The system was rejecting commands despite having correct logic.
Finding: Extreme sensitivity to invisible characters (leading spaces) and errors in separating blocks with commas were detected. A single-line writing protocol was established to avoid interruptions in terminal execution.

3. Solution Implemented
To resolve the terminal visibility issues in the browser and meet the technical requirements, the following was implemented:
Validating the field hierarchy: Ensuring that each path matches the schema (object.field).
Using MongoDB Compass: The desktop application was recommended to guarantee stable access to the command console when the web interface had display limitations.

4. Week-End Status
The database is now correctly structured. A thorough understanding of how to navigate complex documents has been achieved, and communication barriers with the MongoDB search engine have been resolved.

** Query Developer Role (Tammy Nashely)

1. Activity Summary
This week, the main focus was on implementing advanced logical operators to refine information retrieval and improve the accuracy of animal health reports. Queries were optimized to allow for multiple filters and specific exclusions.

2. Implementation of Logical Operators
The following queries were developed using MongoDB Query Language (MQL) syntax:
A. Using the $or Operator
This operator was used to identify records that meet at least one of the specified conditions. It is ideal for searching for multiple species or symptoms simultaneously.
• Use Case: Filtering patients who are birds or reptiles.
• Query:
db.patients.find({
$or: [
{ species: "Canary" },
{ species: "Turtle" }
]
})

B. Use of the $and Operator
It was implemented for queries that require all conditions to be strictly met. Although MongoDB applies an implicit $and in many cases, its explicit use is necessary when the same key is repeated with different operators.
• Use Case: Filter pets of a specific species that were treated within a given date range.
• Query:
db.consultas.find({
$and: [
{ species: "Hamster" },
{ visit_date: { $regex: /2026-04/ } }
]
})
db.consultas.find({
$and: [
{ species: "Hamster" },
{ visit_date: { $regex: /2026-04/ } }
]
})

C. Use of the $not Operator
This operator was applied to invert the effect of other operators, allowing the exclusion of specific results that do not meet a technical or health criterion.
• Use case: Identify patients who have not been marked as "stable".
• Query:
db.patients.find({
health_status: { $not: { $eq: "Stable" } }
})
3. Results and Validations
• Filter Accuracy: Deeper segmentation of the medical_record collection was achieved.
• Optimization: The queries were tested in MongoDB Compass to ensure optimal response times before integrating them into the Node.js backend.
• Consistency: The results were verified to match the data analysis requirements requested by the team.

**Integration Specialist Role (Brayan Hernandez)

Activity Report – Connecting to MongoDB
Activity performed:
Today I connected to the MongoDB database using the terminal, using Figma as a design tool to visualize the project structure.
Process description:
First, I used Figma, a design application, to visually organize and structure the project. Based on this design, I worked on everything within a single folder, which kept the files organized and facilitated the integration between the design and technical aspects.
Next, I used the terminal to establish the connection with MongoDB. I configured the necessary parameters and executed the corresponding commands to establish communication between the application and the database, allowing the terminal to correctly send data to MongoDB.

Difficulties encountered:
During the process, some problems arose when establishing the connection, likely related to the configuration or execution of commands in the terminal. However, these issues were quickly resolved after reviewing the errors and adjusting the configuration.

Final result: The connection to MongoDB was successfully established, allowing data to be sent from the terminal to the database. Using Figma facilitated the project's pre-organization, and managing everything in a single folder helped maintain better control over development.

Conclusion: The activity was successful, as the objective of connecting the terminal to MongoDB was achieved. Furthermore, it reinforced learning about connection configuration and the importance of planning ahead with design tools like Figma, as well as maintaining good file organization.

**Role of the Data Seeler/QA (Ximena Rosas)

Generating "Seeds" (Datasets)
You created three interconnected collections using Chaos logic:
Pets Collection: You didn't just add dog names. You researched and generated data with variability:
Applied Chaos: You included pets with extreme ages (0 or 25 years) and rare species to test the search filters.
Medicine Collection: This is where precision comes in.
Applied Chaos: Medications with past expiration dates, zero stock levels, and prices with complex decimals to test the $lt (less than) and $lte operators.
Sales Collection: The transaction history.
Applied Chaos: Sales without an associated pet ID or with negative amounts, to see if the QA system detects a lack of integrity.

**Roll des Scrum Masters (Annel Ricaño)

This week we reviewed the filters. The queries were optimized to allow multiple filters and specific exclusions.
2. Implementation of Logical Operators
The following are the queries developed using MongoDB Query Language (MQL) syntax:
A. Using the $or Operator
This operator is used to identify records that meet at least one of the specified conditions. It is ideal for searching for multiple species or symptoms simultaneously.
