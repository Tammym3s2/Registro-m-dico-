# PetHealth Connect: Gestión Veterinaria e Integral
## Descripción
**PetHealth Connect** es una plataforma web integral diseñada para la gestión digital de servicios veterinarios, permitiendo a los dueños de mascotas agendar citas médicas y adquirir medicamentos especializados en un solo ecosistema optimizado. Este proyecto resuelve la desorganización de historiales médicos y la dificultad de acceso a suministros de salud animal, eliminando las barreras de comunicación entre la clínica y el usuario. Para el dueño de una mascota, representa la tranquilidad de tener un control total, rápido y centralizado sobre el bienestar de su compañero, asegurando que el cuidado médico y farmacéutico esté a un solo clic de distancia.
## 🏗️ Rol del Colaborador: Data Modeler
Como responsable del modelado de datos, el enfoque principal de este repositorio es la arquitectura de la base de datos NoSQL en MongoDB, asegurando la integridad, escalabilidad y eficiencia en las consultas.
### Características del Modelo de Datos:
 * **Patrón de Embebido:** Optimización de lecturas mediante la anidación de mascotas dentro de sus respectivos dueños.
 * **Integridad Financiera:** Desnormalización de precios en la colección de ventas para mantener registros históricos exactos.
 * **Polimorfismo:** Estructura flexible para soportar diversas especies de mascotas con rasgos específicos.
## 📁 Estructura de Datos (Semillas)
El proyecto incluye dos colecciones principales con 100 documentos de prueba para validación:
 1. **Owners & Pets:** Registro de dueños y sus mascotas anidadas.
 2. **Sales:** Registro de transacciones, citas y medicamentos adquiridos.
## 🛠️ Tecnologías Utilizadas
 * **Base de Datos:** MongoDB Atlas (Cloud)
 * **Formato de Datos:** JSON
 * **Modelado:** NoSQL / Documental
## 🚀 Instalación y Uso
Para probar los datos en tu entorno local o en MongoDB Atlas:
 1. Clona este repositorio.
 2. Localiza los archivos owners_pets_seed.json y sales_seed.json.
 3. Importa los archivos usando MongoDB Compass o la terminal:
   ```bash
   mongoimport --uri "tu_cadena_de_conexion" --collection owners --file owners_pets_seed.json --jsonArray
   
   ```
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


| Role | Responsibility | Status | Key Deliverables |
| :--- | :--- | :--- | :--- |
| **Integration Specialist** | Comparison Operators | 🔴 Blocked | MQL Query Logic (`$gt`, `$lt`) |
| **Query Developer** | Data Retrieval | 🟢 Done | Regex & Species Filters |
| **Lead Architect** | DB Structure | 🟢 Done | English Schema Design |
| **Data Seeder** | Data Generation | 🟡 Active | Mockaroo Configuration |
