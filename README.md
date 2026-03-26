# Registro-m-dico-
El sistema actual de gestión de mascotas enfrenta el desafío de manejar datos altamente heterogéneos. Debido a las diferencias biológicas y de cuidado entre especies. Se requiere una solución que permita almacenar información específica para cada tipo de animal sin comprometer la integridad de los datos.
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

![Turtle Query](./imagen/turtle.png)

---

### 🏠 2. Lifestyle and Habitat Filter
**Objective:** Determine which pets live inside the home (indoor), which is critical for diagnoses related to their environment.
* **Code:** `{ "pet.specific_traits.is_indoor": true }`
* **Field used:** `pet.specific_traits.is_indoor` (boolean).

![Indoor Pets](./imagen/domesticos.png)

---

### 🎨 3. Identification by Physical Traits (Color)
**Objective:** Assist in the quick visual identification of a patient, especially useful in cases of loss or record confirmation.
* **Code:** `{ "pet.specific_traits.fur_color": "White" }`
* **Field used:** `pet.specific_traits.fur_color`.

![Color Query](./imagen/colorson.png)

---

### 🏥 4. Medical History Tracking (Reason for Visit)
**Objective:** Filter patients based on the reason for their visit, such as deworming or annual check-ups.
* **Code:** `{ "vet_visit.reason": "Deworming" }`
* **Field used:** `vet_visit.reason`.

![Visit Reason](./imagen/razonvisita.png)

---

### 🆔 5. Precision Search by ID
**Objective:** Locate a specific owner or pet uniquely and accurately using their assigned system code.
* **Code:** `{ "owner.owner_id": "OWN-7721" }`
* **Field used:** `owner.owner_id`.

![Owner ID](./imagen/iddueño.png)

---

### 📅 6. Chronological Control (Year and Month)
**Objective:** Perform visit audits by time periods, identifying new patient registrations in specific months or annual reports.
* **Code (Month):** `{ "vet_visit.date": /^1\// }`
* **Code (Year):** `{ "vet_visit.date": /2026/ }`
* **Technique:** Use of Regular Expressions (Regex).

![January Search](./imagen/buscar%20mes.png)
![2026 Search](./imagen/buscaaño.png)

---

### 📞 7. Contact Information Retrieval (Phone)
**Objective:** Quickly obtain the contact details of the person responsible for the pet for emergencies or appointment reminders.
* **Code:** `{ "owner.phone_number": "973-792-3632" }` 
* **Field used:** `owner.phone_number`.

![Phone Query](./imagen/busca%20tel.png)
