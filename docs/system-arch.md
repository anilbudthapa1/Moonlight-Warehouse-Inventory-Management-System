# System Architecture
## Moonlight Warehouse Management System

![Architecture](https://img.shields.io/badge/Architecture-3--Tier-blue)
![Frontend](https://img.shields.io/badge/Frontend-React-61DAFB)
![Backend](https://img.shields.io/badge/Backend-Node.js%20%26%20Express-339933)
![Database](https://img.shields.io/badge/Database-PostgreSQL-336791)
![Security](https://img.shields.io/badge/Security-JWT%20%26%20RBAC-orange)
![Approach](https://img.shields.io/badge/Design-Modular-success)

---

## 1. Introduction

This document describes the system architecture of the **Moonlight Warehouse Management System**, a web-based warehouse inventory solution designed for an Australian e-commerce grocery business. The purpose of this architecture document is to explain how the system is structured, how its major components interact, and how the chosen technologies support the project requirements.

The system architecture provides a high-level technical view of the application, including the frontend, backend, database, authentication mechanism, modules, and communication flow. It acts as a guide for development, testing, deployment, and future maintenance.

---

## 2. Architecture Overview

The Moonlight Warehouse Management System follows a **3-tier architecture**. This architecture separates the system into three main layers:

1. **Presentation Layer** – the user-facing interface built with React  
2. **Application Layer** – the backend logic and API built with Node.js and Express  
3. **Data Layer** – the PostgreSQL database used to store and manage system data  

This structure helps keep the system modular, easier to maintain, and suitable for future extension.

---

## 3. Technology Stack

The project uses the following technologies:

| Layer | Technology | Purpose |
|---|---|---|
| Frontend | React.js | User interface and page rendering |
| Backend | Node.js + Express.js | REST API and business logic |
| Database | PostgreSQL | Relational data storage |
| Authentication | JWT | Secure login session handling |
| Authorization | Role-Based Access Control (RBAC) | Restrict access by role |
| Database Tools | pgAdmin 4, DBeaver | Database management and ERD generation |
| Version Control | GitHub | Source code and documentation management |

---

## 4. High-Level Architecture Diagram

```text
User
  │
  ▼
React Frontend (Presentation Layer)
  │
  ▼
Node.js + Express Backend (Application Layer)
  │
  ▼
PostgreSQL Database (Data Layer)
```

### Explanation
- The **user** interacts with the system through the React frontend
- The **frontend** sends requests to the backend API
- The **backend** validates requests, applies business logic, and communicates with the database
- The **database** stores products, suppliers, inventory, users, stock movements, batches, and alerts
- The backend sends responses back to the frontend, which then updates the UI

---

## 5. Presentation Layer

The **presentation layer** is the frontend part of the system and is built using **React.js**. It is responsible for displaying the user interface and supporting interaction between users and system features.

### Main frontend responsibilities
- Displaying login page and dashboards
- Showing product, supplier, inventory, and report pages
- Handling form input and user actions
- Showing alerts, validation messages, and results
- Managing protected pages for different roles

### Key frontend pages
- Login Page
- Dashboard
- Product Management Page
- Supplier Management Page
- Warehouse Location Page
- Inventory Page
- Stock-In Page
- Stock-Out Page
- Inventory Adjustment Page
- Batch and Expiry Tracking Page
- Reports Page

The frontend will communicate with the backend using REST API requests and will display data in a user-friendly format.

---

## 6. Application Layer

The **application layer** is the backend part of the system and is built using **Node.js** and **Express.js**. It contains the core business logic of the warehouse management system.

### Main backend responsibilities
- Handling user authentication
- Verifying user roles and permissions
- Processing product, supplier, and inventory requests
- Recording stock movements
- Updating inventory quantities
- Managing batch and expiry data
- Generating alerts and reports
- Returning JSON responses to the frontend

### Main backend modules
- Authentication module
- User and role management module
- Product management module
- Supplier management module
- Warehouse location module
- Inventory management module
- Stock movement module
- Batch and expiry module
- Alerts module
- Reports module

---

## 7. Data Layer

The **data layer** uses **PostgreSQL** as the main relational database management system. It stores all structured data required by the warehouse system.

### Main data entities
- Users
- Roles
- Products
- Categories
- Suppliers
- Warehouse Locations
- Inventory
- Stock Movements
- Batches
- Alerts

### Main database responsibilities
- Store and retrieve system data
- Maintain relationships between entities
- Support accurate stock and batch tracking
- Enforce data integrity through keys and constraints
- Provide a reliable source of data for reports and dashboards

The database structure is designed using relational tables and foreign key relationships.

---

## 8. Authentication and Authorization

The system uses **JWT (JSON Web Token)** for authentication and **Role-Based Access Control (RBAC)** for authorization.

### Authentication flow
1. User opens login page
2. User enters credentials
3. Backend validates credentials
4. Backend generates JWT token
5. Frontend stores token securely
6. Protected requests include the token
7. Backend verifies token before allowing access

### Authorization flow
- **Administrator** can manage users, roles, and master data
- **Warehouse Manager** can manage products, suppliers, inventory, adjustments, and reports
- **Warehouse Staff** can perform stock-in, stock-out, and inventory-related actions based on assigned permissions

This ensures users only access features allowed by their role.

---

## 9. Module Breakdown

The system is divided into major functional modules:

### 9.1 Authentication Module
Handles login, logout, token verification, and access control.

### 9.2 User Management Module
Handles creation, editing, and deletion of user accounts and role assignment.

### 9.3 Product Management Module
Handles product records, categories, SKU, barcode, pricing, and status.

### 9.4 Supplier Management Module
Handles supplier records, contact information, and supplier-product relationships.

### 9.5 Warehouse Location Module
Handles storage location records such as rack, bin, and shelf.

### 9.6 Inventory Management Module
Handles inventory records, quantity tracking, and stock visibility.

### 9.7 Stock Movement Module
Handles stock-in, stock-out, transfer, and adjustment operations.

### 9.8 Batch and Expiry Module
Handles batch numbers, manufacture dates, expiry dates, and expiry tracking.

### 9.9 Alerts Module
Handles low-stock, near-expiry, and expired item alerts.

### 9.10 Reports Module
Handles stock summary, movement reports, expiry reports, and dashboard analytics.

---

## 10. Data Flow

The system follows a straightforward request-response data flow.

### Example: Stock-In Process
1. User opens stock-in page on frontend
2. User enters stock-in details
3. Frontend sends request to backend API
4. Backend validates the request
5. Backend updates inventory in PostgreSQL
6. Backend records stock movement
7. Backend returns success response
8. Frontend updates stock display

### Example: Login Process
1. User enters login credentials
2. Frontend sends credentials to backend
3. Backend checks user account and password
4. Backend generates token if valid
5. Frontend stores token
6. User is redirected to the correct dashboard

---

## 11. API Communication

The frontend and backend communicate using **REST APIs**.

### API communication style
- Frontend sends HTTP requests
- Backend processes requests and validates data
- Backend returns JSON responses
- Frontend displays results to the user

### Example API groups
- `/api/auth`
- `/api/users`
- `/api/products`
- `/api/suppliers`
- `/api/inventory`
- `/api/stock-movements`
- `/api/batches`
- `/api/alerts`
- `/api/reports`

This API-based structure keeps the system modular and easier to test.

---

## 12. Security Considerations

Security is an important part of the architecture.

### Key security controls
- JWT-based authentication
- Role-based access control
- Password hashing
- Input validation
- Protected API endpoints
- Controlled access to sensitive operations
- Secure handling of user credentials
- Logging of stock movement and adjustment activity

These controls reduce the risk of unauthorized access and data misuse.

---

## 13. Deployment Overview

The project is intended to be deployed as a web-based system.

### Deployment components
- **Frontend** deployed as a React web application
- **Backend** deployed as a Node.js server
- **Database** hosted using PostgreSQL
- **Environment variables** used for database and token configuration

### Basic deployment flow
1. Build frontend
2. Deploy backend server
3. Configure PostgreSQL connection
4. Set environment variables
5. Connect frontend to backend APIs
6. Test deployed system

---

## 14. Scalability and Maintainability

The architecture is designed to support future growth and easier maintenance.

### Scalability features
- Modular backend structure
- Separate frontend, backend, and database layers
- Reusable API design
- Expandable database schema
- Ability to add more modules later

### Maintainability features
- Clear separation of concerns
- Structured documentation
- Role-based module design
- Easier bug fixing and testing
- Support for future upgrades and integrations

This design makes the system easier to improve over time.

---

## 15. Constraints

The architecture is affected by the following constraints:

- Limited academic project duration
- Limited team size and development resources
- Focus on core warehouse functionality only
- Exclusion of advanced enterprise modules such as ERP integration
- Dependence on PostgreSQL, React, and Node.js as selected technologies

These constraints help keep the system realistic and achievable within the project scope.

---

## 16. Conclusion

The Moonlight Warehouse Management System uses a 3-tier architecture that separates the user interface, business logic, and data storage into clear layers. This architecture supports secure authentication, inventory management, supplier management, stock movement tracking, expiry monitoring, and reporting. The use of React, Node.js, Express, and PostgreSQL provides a strong technical foundation for building a modular, maintainable, and scalable warehouse management solution for an Australian e-commerce grocery business.
 easier to improve over time.

---

## 15. Constraints

The architecture is affected by the following constraints:

- Limited academic project duration
- Limited team size and development resources
- Focus on core warehouse functionality only
- Exclusion of advanced enterprise modules such as ERP integration
- Dependence on PostgreSQL, React, and N
