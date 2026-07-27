# PricePilot AI – System Architecture

## Overview

PricePilot AI follows a modular three-tier architecture consisting of a frontend, backend, database, and AI/ML layer. This architecture provides scalability, maintainability, and easy integration of future AI modules.

---

# System Architecture

```
                          +----------------------+
                          |      Frontend        |
                          |      Next.js         |
                          |   Tailwind CSS       |
                          +----------+-----------+
                                     |
                                     | REST API
                                     |
                                     ▼
                          +----------------------+
                          |      Backend         |
                          |      FastAPI         |
                          +----------+-----------+
                                     |
         ---------------------------------------------------------
         |            |             |            |                |
         ▼            ▼             ▼            ▼                ▼
+---------------+ +---------------+ +---------------+ +----------------+
| Authentication| | Product Mgmt  | | Pricing Mgmt | | Analytics APIs |
+---------------+ +---------------+ +---------------+ +----------------+
                                     |
                                     ▼
                          +----------------------+
                          |   SQLAlchemy ORM     |
                          +----------+-----------+
                                     |
                                     ▼
                          +----------------------+
                          |   MySQL/PostgreSQL   |
                          +----------+-----------+
                                     |
                                     ▼
                          +----------------------+
                          | Retail Pricing Data  |
                          | E-commerce Sales Data|
                          +----------+-----------+
                                     |
                                     ▼
                          +----------------------+
                          | Future AI Modules    |
                          | Price Prediction     |
                          | Demand Forecasting   |
                          | Revenue Optimization |
                          +----------------------+
```

---

# Frontend Layer

The frontend is developed using **Next.js** and **Tailwind CSS**.

### Responsibilities

- User Login
- Dashboard
- Product Management
- Pricing Management
- Analytics Dashboard
- Display Charts and Reports

---

# Backend Layer

The backend is developed using **FastAPI**.

### Responsibilities

- Authentication
- JWT Token Generation
- Role-Based Access Control
- Product APIs
- Pricing APIs
- Business Logic
- AI API Integration (Future)

---

# Database Layer

The database stores all application data.

### Main Tables

- Users
- Products
- Pricing History

### Responsibilities

- Store Users
- Store Products
- Store Pricing Information
- Maintain Pricing History

---

# AI/ML Layer (Future)

The AI layer will process business data and generate intelligent pricing recommendations.

### Planned Modules

- Price Prediction
- Demand Forecasting
- Revenue Optimization
- Competitor Analysis

---

# Project Architecture

```
pricepilot-ai/

│
├── frontend/
│     │
│     ├── Dashboard
│     ├── Products
│     ├── Pricing
│     └── Analytics
│
├── backend/
│     │
│     ├── Authentication
│     ├── Product APIs
│     ├── Pricing APIs
│     ├── ML Models
│     └── Database
│
├── docs/
│
└── README.md
```

---

# Technology Stack

| Layer | Technology |
|--------|------------|
| Frontend | Next.js |
| UI | Tailwind CSS |
| Backend | FastAPI |
| ORM | SQLAlchemy |
| Database | MySQL / PostgreSQL |
| Authentication | JWT |
| ML Framework | Scikit-learn, Prophet |
| Version Control | Git & GitHub |

---

# Request Flow

```
User
 │
 ▼
Next.js Frontend
 │
 ▼
FastAPI API
 │
 ▼
Authentication
 │
 ▼
Business Logic
 │
 ▼
Database
 │
 ▼
Response
 │
 ▼
Frontend
```

---

# Conclusion

The architecture of PricePilot AI is modular and scalable. It separates the frontend, backend, database, and AI components, making the system easy to maintain and extend. This design supports the implementation of advanced AI features in future milestones while providing a stable foundation during Milestone 1.
