“Mundo Animal” Veterinary Management System
Week: (March 23-27)

**Rol The Data Modeler(Alejandra Porras)
Designing the Basic Document Structure
Objective: To define how pet data would appear in JSON format.
Action: I created the first draft documents for the pets collection. Instead of using separate tables for owners and pets, I designed a schema where the owner's information is stored directly within the pet's record (nested objects), establishing the initial database hierarchy.

2. Challenges and Questions from That Week

A. Difficulty Connecting to the Cluster
Problem: There was confusion when trying to connect to the database using external tools.
Question: Why couldn't I access my collections if I had already created the cluster?
Resolution: We identified that IP address access was missing from the Atlas security panel. Once the 0.0.0.0/0 rule was added, the connection was successful.
B. Data Visualization
Problem: When uploading the first JSON files, it wasn't clear how to display them correctly.
Question: What is the difference between the "Table" view and the "JSON" view in the Atlas Explorer?
Solution: I learned to navigate the "Collections" tab in Atlas to verify that the nested structure of my documents was being saved correctly as designed.

** Roll als Query Developer (Tammy Nashely)
Evidence Report: Query Developer Role
Project: "Animal World" Veterinary Management System
Responsible: (JSON Architect and Query Developer)
Summary of Activities
As an MQL (MongoDB Query Language) Developer, I was responsible for designing, implementing, and optimizing the system's data retrieval capabilities. My primary focus was ensuring efficient communication between the Node.js server and the MongoDB Atlas cluster, enabling the administrative team to access critical patient information instantly.
Technical Implementations
I developed a query architecture focused on user flexibility, highlighting the following technical milestones:
* Species Segmentation: I implemented logical filters to classify the patient population (canines, felines, etc.), allowing for an organized visualization of the clinical workload.
* Advanced Chronological Analysis: I designed queries using regular expressions (Regex) to filter medical records by specific months and years, facilitating the generation of periodic visit reports.
* Contact Indexing: This will structure direct searches by the owner's phone number, optimizing response times in emergency or follow-up situations.
All queries were tested to dynamically handle new database attributes, including specific physical traits and pet birth dates, ensuring a scalable and accurate system.

**Rol the Data Seeles/QA(ximena)
2. "Fat" Document Stress Test (Performance Optimization)

I generated a "Fat Document" for a specific pet (a Golden Retriever named "Max") containing a nested medical history of over 50 entries, including vaccinations, surgeries, and daily check-ups.
Action: I ran a standard db.pets.find() vs. a projected find({ name: 1, history: { $slice: 1 } }).
Result: Standard retrieval showed a measurable latency spike (increased milliseconds) due to the document's BSON size.
Report: It is mandatory to use proyections or the $slice operator to "thin out" the response. We should not send the entire 50-line history to the main dashboard; only the most recent entry should be loaded by default.

