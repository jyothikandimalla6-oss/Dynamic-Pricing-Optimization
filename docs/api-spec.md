# PricePilot AI – API Specification

## Overview

This document defines the REST APIs used in Milestone 1 of the PricePilot AI project.

The APIs are divided into the following modules:

- Authentication APIs
- Product Management APIs
- Pricing Management APIs

---

# Base URL

```
http://localhost:8000/api/v1
```

---

# Module 1 – Authentication APIs

## 1. Register User

**Endpoint**

```
POST /auth/register
```

### Description

Creates a new user account.

### Request Body

```json
{
  "name": "Jyothi Lakshmi",
  "email": "jyothi@gmail.com",
  "password": "Password123",
  "role": "ADMIN"
}
```

### Response

```json
{
  "message": "User registered successfully"
}
```

---

## 2. Login User

**Endpoint**

```
POST /auth/login
```

### Description

Authenticates the user and returns a JWT token.

### Request Body

```json
{
  "email": "jyothi@gmail.com",
  "password": "Password123"
}
```

### Response

```json
{
  "access_token": "JWT_TOKEN",
  "token_type": "bearer"
}
```

---

## 3. Current User

**Endpoint**

```
GET /auth/me
```

### Description

Returns the currently logged-in user's information.

---

# Module 2 – Product Management APIs

## 1. Get All Products

```
GET /products
```

Returns the complete list of products.

---

## 2. Get Product by ID

```
GET /products/{id}
```

Returns details of a specific product.

---

## 3. Add Product

```
POST /products
```

### Request

```json
{
  "product_name": "Dell Laptop",
  "category": "Electronics",
  "brand": "Dell",
  "cost_price": 48000,
  "selling_price": 55000,
  "stock_quantity": 20
}
```

### Response

```json
{
  "message": "Product added successfully"
}
```

---

## 4. Update Product

```
PUT /products/{id}
```

Updates product information.

---

## 5. Delete Product

```
DELETE /products/{id}
```

Deletes a product from the database.

---

# Module 3 – Pricing Management APIs

## 1. Update Product Price

```
PUT /products/{id}/price
```

### Request

```json
{
  "new_price": 56000,
  "reason": "Festival Offer"
}
```

### Response

```json
{
  "message": "Price updated successfully"
}
```

---

## 2. Pricing History

```
GET /products/{id}/pricing-history
```

Returns all previous price changes for the selected product.

---

# Authentication

All protected APIs require a JWT access token.

Example Header:

```
Authorization: Bearer <JWT_TOKEN>
```

---

# HTTP Status Codes

| Code | Meaning |
|------|---------|
| 200 | Success |
| 201 | Resource Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

---

# API Workflow

```
User
 │
 ▼
Login
 │
 ▼
JWT Token
 │
 ▼
Access Protected APIs
 │
 ├── Products
 ├── Pricing
 └── Dashboard
```

---

# Milestone 1 APIs

### Authentication

- POST /auth/register
- POST /auth/login
- GET /auth/me

### Products

- GET /products
- GET /products/{id}
- POST /products
- PUT /products/{id}
- DELETE /products/{id}

### Pricing

- PUT /products/{id}/price
- GET /products/{id}/pricing-history

---

# Future APIs

The following APIs will be implemented in future milestones:

- Price Prediction API
- Demand Forecast API
- Competitor Analysis API
- Revenue Optimization API
- Analytics API

---

# Conclusion

The APIs defined in Milestone 1 provide the core functionality required for authentication, product management, and pricing management. Future milestones will extend these APIs with AI-powered pricing optimization and business intelligence features.
