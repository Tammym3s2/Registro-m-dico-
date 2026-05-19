a# PetHealth Connect: Gestión Veterinaria e Integral
## 📖 Tabla de Contenidos
 * Descripción
 * Guía de Inicio Rápido
 * Arquitectura de Datos
 * Estructura de Colecciones
 * Tecnologías Utilizadas
 * Autores y Contacto
## Descripción
**PetHealth Connect** es una plataforma web integral diseñada para la gestión digital de servicios veterinarios, permitiendo a los dueños de mascotas agendar citas médicas y adquirir medicamentos especializados en un solo ecosistema optimizado. Este proyecto resuelve la desorganización de historiales médicos y la dificultad de acceso a suministros de salud animal, eliminando las barreras de comunicación entre la clínica y el usuario. Para el dueño de una mascota, representa la tranquilidad de tener un control total, rápido y centralizado sobre el bienestar de su compañero.
## ⚡ Guía de Inicio Rápido
Para tener el modelo de datos corriendo en tu máquina local en el menor tiempo posible:
 1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/tu-usuario/pethealth-connect.git](https://github.com/tu-usuario/pethealth-connect.git)
   cd pethealth-connect
   
   ```
 2. **Importar Datos de Prueba:**
   Asegúrate de tener MongoDB instalado y ejecuta los siguientes comandos para cargar los 100 documentos (50 de dueños/mascotas y 50 de ventas):
   ```bash
   # Importar Colección de Dueños
   mongoimport --db vetDB --collection owners --file data/owners_pets_seed.json --jsonArray
   
   # Importar Colección de Ventas
   mongoimport --db vetDB --collection sales --file data/sales_seed.json --jsonArray
   
   ```
 3. **Verificación:**
   Abre **MongoDB Compass**, conéctate a tu instancia local y explora la base de datos vetDB.
## 🏗️ Arquitectura de Datos
Como **Data Modeler**, el diseño se centró en la eficiencia de lectura y la integridad histórica utilizando los siguientes patrones NoSQL:
 * **Patrón de Embebido (Embedded Pattern):** Las mascotas están anidadas dentro de sus dueños para reducir la latencia de las consultas de perfil.
 * **Patrón de Desnormalización:** Copia de precios unitarios en las ventas para proteger los registros contables contra cambios de precios en el catálogo.
 * **Esquema Polimórfico:** Uso de objetos flexibles para manejar rasgos específicos de diferentes especies animales.
## 📁 Estructura de Colecciones
El proyecto se divide en dos grandes ejes documentales:
 * **owners (Dueños & Mascotas):** Datos de contacto y perfil médico anidado de cada mascota.
 * **sales (Transacciones & Citas):** Registro de facturación, servicios prestados y medicamentos vendidos.
## 🛠️ Tecnologías Utilizadas
 * **Motor de Base de Datos:** MongoDB Atlas / Community Server
 * **Formato de Datos:** JSON / BSON
 * **Gestión de Datos:** MongoDB Compass
 * **Documentación Técnica:** Markdown
© 2026 PetHealth Connect - Desarrollado bajo estándares de Modelado de Datos NoSQL.
## 👥 Team Roles and Responsibilities

| # | Technical Role | Main Responsibility (Weekly Sprints) |
| :--- | :--- | :--- |
| **1** | **The Data Modeler** <br>Porras Ramirez Alejandra | **JSON Architect.** Defines document structures. Decides between "embedding" vs "referencing" data. Designs Mermaid.js diagrams. |
| **2** | **The Query Developer** <br>Barragan Figueroa Tammy Nashieli| **MQL Constructor.** Translates business questions into MongoDB code (`db.collection.find()`). Works with AI to optimize filters. |
| **3** | **The Integration Specialist** <br>Hernandez Jimenez Brayan | **Environment Configurator.** Sets up Atlas Clusters or Compass connections. Manages basic indexes and GitHub repository administration. |
| **4** | **The Data Seeder / QA** <br>Perez Rosas Ximena Victoria | **Chaos Generator.** Creates mock data (JSON files) using AI or Mockaroo. Validates queries against real-world scenarios and reports bugs. |
| **5** | **The Scrum Master** <br>Ricaño Cansino Annel | **Process Facilitator.** Eliminates blockers, ensures the team follows the MongoDB sprint goals, and manages the "Definition of Done" for GitHub artifacts. |


# 🔍 Database Analysis and Queries (MQL)

The queries performed on the **Mundo Animal** database are essential tools for clinical management. They allow for the extraction of strategic information about both patients and owners to streamline veterinary care.

Below are the key queries implemented in this deliverable:

---

### 🐢 1. Inventory Count by Species
**Objective:** Identify how many patients of a specific species (e.g., Turtles or Hamsters) are registered to manage medical resources.
* **Code:** `{ "pet.species": "Turtle" }`
* **Field used:** `pet.species` to filter by taxonomic categories.

![Turtle Query](./img/turtle.png)

---

### 🏠 2. Lifestyle and Habitat Filter
**Objective:** Determine which pets live inside the home (indoor), which is critical for diagnoses related to their environment.
* **Code:** `{ "pet.specific_traits.is_indoor": true }`
* **Field used:** `pet.specific_traits.is_indoor` (boolean).

![Indoor Pets](./img/domesticos.png)

---

### 🎨 3. Identification by Physical Traits (Color)
**Objective:** Assist in the quick visual identification of a patient, especially useful in cases of loss or record confirmation.
* **Code:** `{ "pet.specific_traits.fur_color": "White" }`
* **Field used:** `pet.specific_traits.fur_color`.

![Color Query](./img/colorson.png)

---

### 🏥 4. Medical History Tracking (Reason for Visit)
**Objective:** Filter patients based on the reason for their visit, such as deworming or annual check-ups.
* **Code:** `{ "vet_visit.reason": "Deworming" }`
* **Field used:** `vet_visit.reason`.

![Visit Reason](./img/razonvisita.png)

---

### 🆔 5. Precision Search by ID
**Objective:** Locate a specific owner or pet uniquely and accurately using their assigned system code.
* **Code:** `{ "owner.owner_id": "OWN-7721" }`
* **Field used:** `owner.owner_id`.

![Owner ID](./img/iddueño.png)

---

### 📅 6. Chronological Control (Year and Month)
**Objective:** Perform visit audits by time periods, identifying new patient registrations in specific months or annual reports.
* **Code (Month):** `{ "vet_visit.date": /^1\// }`
* **Code (Year):** `{ "vet_visit.date": /2026/ }`
* **Technique:** Use of Regular Expressions (Regex).

![January Search](./img/buscar%20mes.png)
![2026 Search](./img/buscaraño.png)

---

### 📞 7. Contact Information Retrieval (Phone)
**Objective:** Quickly obtain the contact details of the person responsible for the pet for emergencies or appointment reminders.
* **Code:** `{ "owner.phone_number": "973-792-3632" }` 
* **Field used:** `owner.phone_number`.

![Phone Query](./img/busca%20tel.png)

---

### 📊 8. Data Distribution (Species Overview)
**Objective:** Visualize the variety of patients registered in the clinic using **MongoDB Compass Schema Analysis**. This tool helps the clinic understand at a glance which species are the most common in our database.

**Insights:** * As shown in the generated chart, **horse** currently represent **10%** of our total registered patients.
* This distribution allows the veterinary staff to better plan for specialized medical supplies (e.g., specific food or medicine for exotic pets).

![Schema Analysis Overview](./img/species.png)

---
### 📊 Sprint - Team Status Board

# Product Backlog - Mundo Animal Veterinary Management System

## Product Goal
Develop a NoSQL veterinary management system in MongoDB Atlas that allows registration of pets, owners, medications, and sales, while supporting efficient queries, updates, and analytics for veterinary administration.

---

## Epic 1: Database Setup and Configuration
### User Stories
- As a developer, I want to configure the development environment so the team can start the project.
- As a team member, I want to connect MongoDB Atlas with Compass and VS Code so I can manage collections easily.

### Tasks
- [x] Install VS Code, MongoDB Compass, Git
- [x] Create MongoDB Atlas cluster
- [x] Configure connection string
- [x] Set security access (IP whitelist)
- [x] Create initial repository and README.md

---

## Epic 2: Data Modeling
### User Stories
- As a Data Modeler, I want to design JSON document structures so pet and owner data can be stored correctly.
- As a system, I need embedded documents to simplify pet-owner access.

### Tasks
- [x] Design `pets` collection schema
- [x] Design `medications` collection schema
- [x] Design `sales` collection schema
- [x] Define embedding vs referencing strategy
- [x] Create Mermaid ER diagram
- [x] Validate nested object hierarchy

---

## Epic 3: Data Seeding
### User Stories
- As a QA/Data Seeder, I want realistic test datasets so the system can be validated under multiple scenarios.

### Tasks
- [x] Generate `seeds.json` with +50 records
- [x] Create edge cases (ages 0, 25, invalid values)
- [x] Create linked datasets between collections
- [x] Test fat documents
- [x] Import data with `mongoimport`

---

## Epic 4: Query Development
### User Stories
- As a Query Developer, I want to retrieve pet and sales information using MQL so admins can access reports.

### Tasks
- [x] Basic queries with `find()` and `findOne()`
- [x] Filters using `$gt`, `$lt`, `$in`, `$ne`
- [x] Logical operators `$and`, `$or`, `$not`
- [x] Regex date filtering
- [x] Search by owner phone number
- [x] Query optimization with projections
- [x] Test `$slice` operator

---

## Epic 5: Data Mutation
### User Stories
- As an Integration Specialist, I want to update records dynamically so the system remains accurate.

### Tasks
- [ ] Implement `$set`
- [ ] Implement `$inc`
- [ ] Implement `$push`
- [ ] Implement delete operations
- [ ] Validate updates in terminal
- [ ] Connect Node.js backend

---

## Epic 6: Aggregation and Analytics
### User Stories
- As an admin, I want summarized reports so I can analyze veterinary operations.

### Tasks
- [ ] Create aggregation pipeline with `$match`
- [ ] Group records using `$group`
- [ ] Count documents with `$count`
- [ ] Create advanced reports with `$project`
- [ ] Sort results with `$sort`
- [ ] Join collections with `$lookup`

---

## Epic 7: Performance Optimization
### User Stories
- As a QA engineer, I want to validate performance so the database works efficiently with large datasets.

### Tasks
- [ ] Create indexes
- [ ] Test query speed
- [ ] Use `.explain("executionStats")`
- [ ] Compare before/after indexes
- [ ] Document performance audit

---

## Sprint Retrospective Tasks
- [x] Identify access issues to Atlas
- [x] Resolve terminal syntax errors
- [x] Standardize English naming in collections
- [x] Improve query filters
- [x] Weekly report generation
- [x] GitHub artifact documentation

---

## Team Roles
| Role | Member | Responsibility |
|------|--------|----------------|
| Scrum Master | Annel Ricaño | Sprint planning, retrospective, blockers |
| Data Modeler | Alejandra Porras | JSON schema design |
| Query Developer | Tammy Nashely | MQL queries |
| Data Seeder / QA | Ximena Rosas | Dataset generation and testing |
| Integration Specialist | Brayan Hernandez | MongoDB + Node.js connection |

---

## Current Sprint
### Sprint 3 - Data Intelligence
- [ ] Aggregation pipelines
- [ ] Index optimization
- [ ] Final demo preparation
- [ ] Release v3.0
| Task ID | Role | Technical Specification | Definition of Done (DoD) | Tech Stack / Tag | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **VET-INT-01** | **Integration Specialist**<br>*(Brayan Hernandez)* | • Transition MQL filters into live environment.<br>• Validate boundary conditions for `$gt`, `$lt`, `$in`, and `$ne`. | • `db.products.find()` runs with 0 syntax errors.<br>• Query performance verified in MongoDB Compass. | `MQL` / `Atlas` / `Filters` |  🟢 To Do |
| **VET-QRY-01** | **Query Developer**<br>*(Tammy Nashely)* | • Optimize retrieval times using Indexing.<br>• Refactor Regex filters to enforce case-insensitive matching (`$options: "i"`). | • Execution time stays under 50ms via MongoDB Profiler.<br>• Emergency phone-number lookup algorithm fully verified. | `Regex` / `Indexing` / `Profiler` |  🟢 To Do|
| **VET-ARC-01** | **Data Modeler & Architect**<br>*(Alejandra Porras)* | • Document the unified English schema foundations.<br>• Implement JSON Schema Validation rules for data types. | • Validation scripts successfully block Spanish keys.<br>• 100% agreement on relational links between collections. | `JSON Schema` / `Validation` | 🟢 To Do |
| **VET-SED-01** | **Data Seeder**<br>*(Research Role)* | • Configure Mockaroo formulas for conditional logic.<br>• Execute large-scale data ingestion via terminal. | • Generate a clean dataset with 1.5 million valid entities.<br>• Successful import via `mongoimport` CLI tool. | `Mockaroo` / `mongoimport` |  🟢 To Do |
## 👥 Autores y Contacto
¡Gracias por visitar este proyecto! Si tienes dudas sobre el modelado NoSQL o quieres conectar profesionalmente para networking, puedes encontrarnos aquí:
| Autor | Rol | Enlaces Profesionales |
|---|---|---|
| **Alejandra Porras** | Data Modeler | LinkedIn • GitHub |
| **Tammy Barragán** | The Query Developer | LinkedIn • GitHub |
| **Brayan Hernández** | The Integration Specialist | LinkedIn • GitHub |
| **Ximena Pérez** | The Data Seeder  | LinkedIn • GitHub |
© 2026 PetHealth Connect - Desarrollado bajo estándares de Modelado de Datos NoSQL.
