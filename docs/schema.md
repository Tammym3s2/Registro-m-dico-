```
erDiagram
    PET ||--o| OWNER : "belongs_to"
    SALE ||--o| OWNER : "references"
    SALE ||--|{ SALE_ITEMS : "contains"
    SALE_ITEMS }|--|| MEDICATION : "lists"

    OWNER {
        string owner_id PK
        string full_name
        string email
        string phone_number
    }

    PET {
        string pet_id PK
        string name
        string species
        date birthdate
        string owner_id FK
        object specific_traits
    }

    SALE {
        string sale_id PK
        date sale_date
        object customer_summary
        float total_amount
        string payment_method
    }

    SALE_ITEMS {
        string service
        string id_medication FK
        string name_medication
        int quantity
        float unit_price
    }

    MEDICATION {
        string id_medication PK
        string name_medication
        string specie
        float price
        int stock
        string laboratory
        date date_Exp
    }
    ```
