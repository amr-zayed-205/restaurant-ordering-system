# 🏗️ Restaurant Ordering System

# System Architecture

---

# 1. Architecture Overview

The Restaurant Ordering System follows a simple Client-Server Architecture.

The frontend communicates with the backend through REST APIs.

The backend processes requests, communicates with the database, and returns data in JSON format.

The customer accesses the system through a web browser.

---

# 2. High-Level Architecture

                    Customer
                        │
                        │
                  Web Browser
                        │
                        ▼
             React Frontend (Client)
                        │
                 HTTP / REST API
                        │
                        ▼
          ASP.NET Core Web API (Server)
                        │
                Entity Framework Core
                        │
                        ▼
                 SQL Server Database

---

# 3. System Components

## Frontend

Technology

- React
- Vite
- Tailwind CSS

Responsibilities

- Display Menu
- Display Categories
- Shopping Cart
- Checkout
- Form Validation
- Consume Backend APIs

---

## Backend

Technology

- ASP.NET Core Web API

Responsibilities

- Handle Requests
- Business Logic
- Validation
- Order Processing
- Generate WhatsApp Message
- Return JSON Responses

---

## Database

Technology

SQL Server

Responsibilities

Store

- Meals
- Categories
- Customers
- Orders
- Order Items

---

# 4. Data Flow

Customer

↓

Opens Website

↓

React requests data from API

↓

Backend processes request

↓

Database returns data

↓

Backend returns JSON

↓

React displays data

↓

Customer places order

↓

Backend generates WhatsApp message

↓

Customer is redirected to WhatsApp

---

# 5. API Communication

Frontend communicates with Backend using REST APIs.

Example Endpoints

GET /api/meals

Returns all meals.

---

GET /api/categories

Returns all meal categories.

---

POST /api/orders

Creates a new customer order.

---

# 6. JSON Contract

Example Meal Object

```json
{
  "id": 1,
  "name": "Burger",
  "description": "Classic Beef Burger",
  "price": 120,
  "image": "burger.jpg",
  "categoryId": 1
}
```

All team members must follow the same JSON structure.

---

# 7. Project Folder Structure

```
restaurant-ordering-system/

│

├── frontend/

│   ├── src/

│   ├── components/

│   ├── pages/

│   ├── services/

│   ├── assets/

│

├── backend/

│   ├── Controllers/

│   ├── Models/

│   ├── DTOs/

│   ├── Services/

│   ├── Data/

│

├── docs/

│

└── README.md
```

---

# 8. Database Tables

The first version of the database will contain:

- Categories
- Meals
- Customers
- Orders
- OrderItems

---

# 9. AI Integration (Future)

The AI module will be independent from the main application.

Possible AI Features

- Meal Recommendation

- Smart Search

- Budget Recommendation

- Popular Meals

The AI service will consume the same data exposed by the backend APIs.

---

# 10. Flutter Integration (Future)

A Flutter application can use the same Backend APIs.

Architecture

Flutter App

↓

REST API

↓

ASP.NET Core

↓

SQL Server

This allows both the website and the mobile application to share the same backend and database.

---

# 11. Development Workflow

UI/UX

↓

Frontend Development

↓

Backend Development

↓

Frontend & Backend Integration

↓

Testing

↓

Deployment

---

# 12. Version History

Version 1

Static JSON + UI

---

Version 2

API Integration + Database

---

Version 3

Ordering System + WhatsApp

---

Version 4

AI Features

---

Document Version

v1.0