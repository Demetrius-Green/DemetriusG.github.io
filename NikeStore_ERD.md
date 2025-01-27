erDiagram
    PRODUCT {
        string product_id PK "Unique identifier for each product"
        string product_name "Name of the shoe model"
        float price "Price of the shoe"
    }
    CUSTOMER {
        string customer_id PK "Unique identifier for each customer"
        string first_name "Customer's first name"
        string last_name "Customer's last name"
        string email "Customer's email address"
        string phone "Customer's phone number"
    }
    SALE {
        string sale_id PK "Unique transaction ID"
        string customer_id FK "Customer making the purchase"
        string product_id FK "Product purchased"
        int quantity "Quantity of product sold"
        date sale_date "Date"
        float total_amount "Total price for the transaction"
    }
    INVENTORY {
        string product_id FK "The product in the inventory"
        int stock_level "Number of products in stock"
    }

    PRODUCT ||--o| SALE : "sold in"
    CUSTOMER ||--o| SALE : "makes"
    PRODUCT ||--o| INVENTORY : "tracked in"

