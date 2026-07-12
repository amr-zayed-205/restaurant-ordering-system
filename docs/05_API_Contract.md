# 🔌 Restaurant Ordering System

# API Contract

---

# Purpose

This document defines the data structure shared between the Frontend and Backend.

Both teams must follow this contract when sending and receiving data.

---

# Meals

## GET /api/meals

Returns all meals.

### Response

```json
[
  {
    "id": 1,
    "name": "Burger",
    "description": "Classic Beef Burger",
    "price": 120,
    "imageUrl": "burger.jpg",
    "categoryId": 1
  }
]
```

---

## GET /api/meals/{id}

Returns one meal.

```json
{
  "id": 1,
  "name": "Burger",
  "description": "Classic Beef Burger",
  "price": 120,
  "imageUrl": "burger.jpg",
  "categoryId": 1
}
```

---

# Categories

## GET /api/categories

```json
[
  {
    "id": 1,
    "name": "Burger"
  }
]
```

---

# Orders

## POST /api/orders

### Request

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

---

# Shared Models

## Meal

| Field | Type |
|--------|------|
| id | int |
| name | string |
| description | string |
| price | decimal |
| imageUrl | string |
| categoryId | int |

---

## Category

| Field | Type |
|--------|------|
| id | int |
| name | string |

---

## Customer Order

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
| mealId | int |
| quantity | int |

---

# Notes

- Frontend and Backend must use the same field names.
- Any change must be discussed before implementation.
- This document is the reference for all JSON structures.

---

Document Version

v1.0