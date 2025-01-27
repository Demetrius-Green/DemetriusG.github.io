```mermaid
erDiagram

    PRODUCT {
        string id PK "Product ID"
        string name "Product Name"
        float price "Price"
        string size "Size"
    }

    CUSTOMER {
        string id PK "Customer ID"
        string name "Customer Name"
        string email "Email"
        string phone "Phone"
    }

    SALE {
        string id PK "Sale ID"
        string customer_id FK "Customer ID"
        string product_id FK "Product ID"
        int quantity "Quantity Sold"
        date sale_date "Date of Sale"
        float total_price "Total Price"
    }

    INVENTORY {
        string product_id FK "Product ID"
        int stock_quantity "Stock Quantity"
    }

    PRODUCT ||--o| SALE : "sells"
    CUSTOMER ||--o| SALE : "makes"
    PRODUCT ||--o| INVENTORY : "has"
```
1. Customer to Sale: A customer can make many sales, so it's a one-to-many relationship.
2. Product to Sale: A product can be sold in many sales, so it's a one-to-many relationship.
3. Product to Inventory: Each product has one inventory record, so it's a one-to-one relationship.
4. Sale to Product and Customer: Each sale involves one product and one customer.
