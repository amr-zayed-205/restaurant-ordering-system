# 🗄️ Restaurant Ordering System

# Database Design

---

# Overview

This document describes the database structure of the Restaurant Ordering System.

The goal is to organize data efficiently while keeping the design simple and scalable.

Database Engine

SQL Server

---

# Database Entities

The first version of the system consists of five main entities.

- Categories
- Meals
- Customers
- Orders
- OrderItems

---

# Entity Relationship

Category

↓

contains

↓

Meals

↓

ordered through

↓

OrderItems

↓

belongs to

↓

Orders

↓

created by

↓

Customer

---

# Tables

---

## Categories

Description

Stores all meal categories.

Fields

| Name | Type |
|------|------|
| Id | int |
| Name | nvarchar(100) |

---

## Meals

Description

Stores restaurant meals.

Fields

| Name | Type |
|------|------|
| Id | int |
| Name | nvarchar(150) |
| Description | nvarchar(max) |
| Price | decimal |
| ImageUrl | nvarchar(255) |
| CategoryId | int |

Relationship

One Category

↓

Many Meals

---

## Customers

Description

Stores customer information.

Fields

| Name | Type |
|------|------|
| Id | int |
| FullName | nvarchar(150) |
| PhoneNumber | nvarchar(20) |
| Address | nvarchar(255) |

---

## Orders

Description

Stores customer orders.

Fields

| Name | Type |
|------|------|
| Id | int |
| CustomerId | int |
| OrderDate | datetime |
| TotalPrice | decimal |
| Notes | nvarchar(max) |

Relationship

One Customer

↓

Many Orders

---

## OrderItems

Description

Stores meals inside an order.

Fields

| Name | Type |
|------|------|
| Id | int |
| OrderId | int |
| MealId | int |
| Quantity | int |
| UnitPrice | decimal |

Relationship

One Order

↓

Many Order Items

One Meal

↓

Many Order Items

---

# Relationships Summary

Category

1 → Many Meals

Customer

1 → Many Orders

Order

1 → Many OrderItems

Meal

1 → Many OrderItems

---

# Future Database Expansion

The following tables may be added in future versions.

- Restaurant
- Employees
- Coupons
- Reviews
- Payments
- Delivery
- Favorites

---

# Notes

The database is intentionally simple for Version 1.

Additional tables and relationships will be added as the project grows.

---

Document Version

v1.0