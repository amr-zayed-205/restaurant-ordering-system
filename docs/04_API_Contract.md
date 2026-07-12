# 🔌 Restaurant Ordering System

# API Contract

---

# Overview

This document defines the communication contract between the Frontend and Backend.

All API responses must follow the structures defined in this document.

Changing response structures requires agreement from both Frontend and Backend teams.

---

# Base URL

Development

/api

---

# Response Format

Every API response should follow this format.

## Success Response

```json
{
  "success": true,
  "message": "Request completed successfully.",
  "data": {}
}
```

---

## Error Response

```json
{
  "success": false,
  "message": "Something went wrong.",
  "errors": []
}
```

---

# Meals

## GET /api/meals

Description

Returns all meals.

Response

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Burger",
      "description": "Classic Beef Burger",
      "price": 120,
      "imageUrl": "/images/burger.png",
      "categoryId": 1
    }
  ]
}
```

---

## GET /api/meals/{id}

Returns a single meal.

Response

```json
{
  "success": true,
  "data": {
    "id": 1,
    "name": "Burger",
    "description": "Classic Beef Burger",
    "price": 120,
    "imageUrl": "/images/burger.png",
    "categoryId": 1
  }
}
```

---

# Categories

## GET /api/categories

Response

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Burger"
    }
  ]
}
```

---

# Shopping Cart

Shopping cart is managed on the Frontend.

No API required in Version 1.

---

# Orders

## POST /api/orders

Request

```json
{
  "customerName": "Ahmed",
  "phoneNumber": "01000000000",
  "address": "Cairo",
  "notes": "",
  "items": [
    {
      "mealId": 1,
      "quantity": 2
    }
  ]
}
```

Response

```json
{
  "success": true,
  "message": "Order created successfully."
}
```

---

# Data Models

## Meal

| Field | Type |
|--------|------|
| id | integer |
| name | string |
| description | string |
| price | decimal |
| imageUrl | string |
| categoryId | integer |

---

## Category

| Field | Type |
|--------|------|
| id | integer |
| name | string |

---

## Customer

| Field | Type |
|--------|------|
| customerName | string |
| phoneNumber | string |
| address | string |
| notes | string |

---

## Order Item

| Field | Type |
|--------|------|
| mealId | integer |
| quantity | integer |

---

# API Rules

- All responses must be JSON.
- All endpoints return HTTP status codes correctly.
- Naming convention uses camelCase.
- IDs are integers.
- Prices are decimal numbers.

---

Document Version

v1.0