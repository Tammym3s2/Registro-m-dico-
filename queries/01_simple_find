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

