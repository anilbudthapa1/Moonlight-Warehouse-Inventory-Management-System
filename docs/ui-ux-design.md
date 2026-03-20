# UI/UX Design
## Moonlight Warehouse Management System

![Status](https://img.shields.io/badge/Status-In%20Progress-blue)
![UI/UX](https://img.shields.io/badge/UI%2FUX-Design-orange)
![Frontend](https://img.shields.io/badge/Frontend-React-61DAFB)
![Database](https://img.shields.io/badge/Database-PostgreSQL-336791)
![Module](https://img.shields.io/badge/Module-Warehouse%20Management-purple)
![Methodology](https://img.shields.io/badge/Approach-User%20Centered-success)

---

# 1. Introduction

This document presents the **UI/UX design** for the **Moonlight Warehouse Management System**, a web-based warehouse and inventory management solution for an Australian e-commerce grocery business. The purpose of this document is to describe how users will interact with the system, how the interface supports the main workflows, and how visual diagrams are used to represent important system use cases.

The UI/UX design focuses on usability, clarity, efficiency, and role-based access. Since the system will be used by administrators, warehouse managers, and warehouse staff, the interface must support different user roles while keeping the navigation simple and consistent. The design also considers common warehouse tasks such as login, product management, supplier management, stock-in, stock-out, inventory adjustments, expiry tracking, and reporting.

This document includes explanations of the main interface workflows and references to use case diagrams stored in the project repository. These diagrams visually represent how users interact with the system for each core function.

---

# 2. UI/UX Design Objectives

The UI/UX design aims to achieve the following:

- provide a clean and easy-to-use interface
- reduce confusion during warehouse operations
- support fast access to key inventory functions
- ensure role-based navigation and permissions
- improve visibility of stock, alerts, and operational data
- support efficient data entry and workflow completion
- make the system easy to learn for first-time users

---

# 3. Design Principles

The UI/UX design follows these principles:

- **Clarity** — pages should be readable and understandable
- **Consistency** — forms, buttons, layouts, and navigation should follow the same style
- **Efficiency** — users should complete common tasks quickly
- **Visibility** — important alerts and stock information should be easy to see
- **Feedback** — the system should clearly show success, failure, and validation messages
- **Role-Based Experience** — users should only see features relevant to their role

---

# 4. Main User Roles in the Interface

The interface is designed for the following user roles:

## 4.1 Administrator
The administrator manages users, permissions, system configuration, and overall data control.

## 4.2 Warehouse Manager
The warehouse manager monitors inventory, adjusts stock, reviews reports, manages suppliers, and tracks expiry-sensitive items.

## 4.3 Warehouse Staff
Warehouse staff perform operational tasks such as stock-in, stock-out, batch entry, and location-based inventory updates.

---

# 5. Main UI Modules

The main user interface modules include:

- Login page
- Role-based dashboard
- Product management page
- Supplier management page
- Warehouse location page
- Inventory management page
- Stock-in page
- Stock-out page
- Batch and expiry tracking page
- Alerts page
- Reports page
- User management page

---

# 6. Diagram Storage Location

All workflow and use case images are stored in the repository under the following location:

```text
charts/resources/diagram/
