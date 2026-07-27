# PricePilot AI – Database Schema

## Overview

The database stores all the information required for PricePilot AI. During Milestone 1, the application uses three primary tables:

- Users
- Products
- Pricing History

These tables support authentication, product management, and pricing management.

---

# Database Design

```
Users
   │
   │ 1
   │
   │ N
Pricing_History
   │
   │ N
   │
   │ 1
Products
```

---

# Table 1: Users

## Description

Stores user account information for authentication and authorization.

| Column | Data Type | Description |
|---------|-----------|-------------|
| id | Integer | Primary Key |
| name | Varchar(100) | User Name |
| email | Varchar(100) | Email Address |
| password | Varchar(255) | Encrypted Password |
| role | Varchar(30) | Admin / Pricing Manager / Analyst / Viewer |
| is_active | Boolean | Account Status |
| created_at | Timestamp | Account Creation Date |

---

# Table 2: Products

## Description

Stores product details and current pricing information.

| Column | Data Type | Description |
|---------|-----------|-------------|
| id | Integer | Primary Key |
| product_name | Varchar(150) | Product Name |
| category | Varchar(100) | Product Category |
| brand | Varchar(100) | Brand Name |
| cost_price | Decimal | Cost Price |
| selling_price | Decimal | Current Selling Price |
| stock_quantity | Integer | Available Stock |
| created_at | Timestamp | Product Creation Date |
| updated_at | Timestamp | Last Updated Date |

---

# Table 3: Pricing History

## Description

Stores every price update made for a product.

| Column | Data Type | Description |
|---------|-----------|-------------|
| id | Integer | Primary Key |
| product_id | Integer | Foreign Key (Products) |
| old_price | Decimal | Previous Price |
| new_price | Decimal | Updated Price |
| reason | Text | Reason for Price Change |
| updated_by | Integer | Foreign Key (Users) |
| updated_at | Timestamp | Date & Time of Update |

---

# Entity Relationship (ER) Diagram

```
+-----------+
|   Users   |
+-----------+
| id (PK)   |
| name      |
| email     |
| password  |
| role      |
+-----------+
      |
      | updated_by
      |
      ▼
+-------------------+
| Pricing History   |
+-------------------+
| id (PK)           |
| product_id (FK)   |
| old_price         |
| new_price         |
| reason            |
| updated_by (FK)   |
+-------------------+
      ▲
      |
      | product_id
      |
+----------------+
|   Products     |
+----------------+
| id (PK)        |
| product_name   |
| category       |
| brand          |
| cost_price     |
| selling_price  |
| stock_quantity |
+----------------+
```

---

# Relationships

### Users → Pricing History

- One user can update the prices of many products.
- Relationship: **One-to-Many (1:N)**

### Products → Pricing History

- One product can have multiple price updates.
- Relationship: **One-to-Many (1:N)**

---

# Database Workflow

```
User Login
      │
      ▼
Authentication
      │
      ▼
Product Management
      │
      ▼
Update Product Price
      │
      ▼
Save Pricing History
      │
      ▼
Database
```

---

# Future Database Tables

The following tables will be added in future milestones:

- Sales Data
- Demand Forecast
- Price Prediction
- Competitor Prices
- Revenue Reports
- Analytics Reports

---

# Conclusion

The Milestone 1 database schema provides the core foundation for authentication, product management, and pricing management. It is designed to be scalable so that AI modules such as demand forecasting, price prediction, competitor analysis, and revenue optimization can be integrated in future milestones.
