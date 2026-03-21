# Software Requirements Specification (SRS)
## Moonlight Warehouse Management System

**Project Name:** Moonlight Warehouse Management System  
**Project Type:** Web-Based Warehouse Inventory Management System  
**Target Business:** Australian E-commerce Grocery Business  
**Technology Stack:** React, Node.js, Express, PostgreSQL  

---

# 1. Introduction

## 1.1 Purpose
The purpose of this Software Requirements Specification (SRS) is to define the functional and non-functional requirements for the Moonlight Warehouse Management System. This document describes the business needs, system features, user roles, constraints, and expected behaviour of the system. It serves as a reference for the project team during analysis, design, development, testing, deployment, and final delivery.

## 1.2 Scope
The Moonlight Warehouse Management System is a web-based software solution designed to improve warehouse and inventory operations for an Australian e-commerce grocery business. The system will provide centralized management of products, categories, suppliers, warehouse locations, inventory records, stock movements, batch numbers, and expiry dates. It will also support user authentication, role-based access, alerts, dashboards, and reports.

The system is intended to reduce manual work, improve inventory accuracy, support better tracking of perishable goods, and help staff and managers make informed operational decisions.

## 1.3 Intended Audience
This document is intended for:

# Stakeholder Team

> ![Project Manager](https://img.shields.io/badge/Project%20Manager-Anil%20Budthapa-blueviolet?style=for-the-badge)  
> ![Backend Developer](https://img.shields.io/badge/Backend%20Developer-Anil%20Budthapa-1E90FF?style=for-the-badge)  
> `K250101@student.kent.edu.au`

> ![Tech Lead](https://img.shields.io/badge/Tech%20Lead-Diwas%20Phuyal-red?style=for-the-badge)  
> ![Frontend Developer](https://img.shields.io/badge/Frontend%20Developer-Diwas%20Phuyal-ff69b4?style=for-the-badge)  
> `K250106@student.kent.edu.au`

> ![Frontend Developer](https://img.shields.io/badge/Frontend%20Developer-Anil%20K%20C-orange?style=for-the-badge)  
> `K250771@student.kent.edu.au`

> ![Backend Developer](https://img.shields.io/badge/Backend%20Developer-Achima%20Basnet-2ecc71?style=for-the-badge)  
> `K210655@student.kent.edu.au`

> ![QA Engineer](https://img.shields.io/badge/QA%20Engineer-Thi%20Phuong%20Thanh%20Bui-yellow?style=for-the-badge)  
> `K250200@student.kent.edu.au`

## 1.4 Definitions, Acronyms, and Abbreviations

- **SRS** – Software Requirements Specification
- **UI** – User Interface
- **UX** – User Experience
- **ERD** – Entity Relationship Diagram
- **JWT** – JSON Web Token
- **API** – Application Programming Interface
- **CRUD** – Create, Read, Update, Delete
- **RBAC** – Role-Based Access Control
- **SKU** – Stock Keeping Unit

## 1.5 Document Overview
This SRS describes the overall system purpose, stakeholders, user roles, system features, requirements, use cases, data fields, constraints, assumptions, and acceptance expectations for the Moonlight Warehouse Management System.

---

# 2. Overall Description

## 2.1 Product Perspective
The Moonlight Warehouse Management System is a new standalone web application for warehouse inventory operations. It is designed to replace manual, spreadsheet-based, or disconnected processes with a centralized digital platform.

The system will include:  
[![Frontend](https://img.shields.io/badge/Frontend-React-61DAFB?style=for-the-badge&logo=react&logoColor=white)](https://react.dev/)  
[![Backend](https://img.shields.io/badge/Backend-Node.js%20%26%20Express-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)  
[![Database](https://img.shields.io/badge/Database-PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

- **React frontend** for user interaction  
- **Node.js and Express backend** for business logic and APIs  
- **PostgreSQL database** for secure data storage  

## 2.2 Product Functions
The main functions of the system are:

- Secure user login and role-based access
- Product and category management
- Supplier management
- Warehouse location management
- Inventory tracking
- Stock-in and stock-out management
- Stock adjustment management
- Batch and expiry tracking
- Low-stock and expiry alerts
- Dashboard summaries and reports
- Activity and stock movement history

## 2.3 User Classes and Characteristics

### Administrator
- Manages users and permissions
- Maintains master data
- Has full system access

### Warehouse Manager
- Monitors stock levels and warehouse performance
- Reviews alerts and reports
- Oversees product, supplier, and location data

### Warehouse Staff
- Performs stock-in, stock-out, and inventory updates
- Views relevant product and inventory information
- Uses operational pages for daily warehouse tasks

## 2.4 Operating Environment
The system will operate in the following environment:

- Web browser-based frontend
- Desktop or laptop access
- Backend hosted locally or on cloud/server
- PostgreSQL database environment
- Development on modern operating systems such as Windows, Linux, or macOS

## 2.5 Design and Implementation Constraints

- The project must be completed within the academic project schedule
- The system will use React, Node.js, Express, and PostgreSQL
- The project will focus on core warehouse functions only
- The system will not include customer shopping or payment modules
- Team resources and time are limited

## 2.6 Assumptions and Dependencies

- Users have internet or network access to the system
- Warehouse staff have basic computer literacy
- PostgreSQL is available and properly configured
- The project team has access to GitHub and required development tools
- System data such as products and suppliers will be entered accurately by authorized users

---

# 3. Stakeholders

## 3.1 Business Stakeholders
- Business Owner / Client
- Warehouse Manager
- Warehouse Staff

## 3.2 Project Team Stakeholders
- Product Manager
- Tech Lead
- Backend Developer
- Frontend Developer
- QA Engineer

## 3.3 External Stakeholders
- Project Supervisor / Lecturer
- Academic review team

---

# 4. Business Problem

Moonlight requires efficient warehouse operations to manage inventory, perishable products, stock movement, and order-related preparation. Manual and fragmented processes may lead to inaccurate stock records, limited inventory visibility, expiry management problems, and warehouse inefficiency. In the Australian e-commerce grocery market, these issues can affect profitability, customer satisfaction, and business growth. Therefore, a centralized warehouse management system is required to improve accuracy, reduce waste, and support better operational control.

---

# 5. Project Objectives

- Develop a secure and user-friendly warehouse management system
- Centralize inventory and warehouse data management
- Improve stock visibility and record accuracy
- Support batch and expiry tracking for perishable goods
- Reduce manual errors and operational delays
- Provide useful reports and dashboard insights
- Apply structured software engineering practices across development

---

# 6. In Scope

The project includes:

- User authentication and role-based access control
- Product management
- Category management
- Supplier management
- Warehouse location management
- Inventory management
- Stock-in and stock-out processing
- Stock adjustment
- Batch tracking
- Expiry tracking
- Low-stock alerts
- Dashboard and reports
- Testing, deployment planning, and project documentation

---

# 7. Out of Scope

The project excludes:

- Customer-facing e-commerce shopping website
- Online payments
- Delivery route optimization
- Mobile application
- AI demand forecasting
- Accounting and payroll features
- ERP integration
- IoT sensors and robotics
- International multi-warehouse logistics
- Advanced supplier portal integration

---

# 8. Functional Requirements

## 8.1 Authentication and Authorization

**FR-01** The system shall allow users to log in using valid credentials.  
**FR-02** The system shall restrict access based on user roles.  
**FR-03** The system shall allow authorized users to log out securely.  
**FR-04** The system shall protect secure pages from unauthorized access.  
**FR-05** The system shall store passwords securely using hashing.  

## 8.2 User Management

**FR-06** The system shall allow administrators to create user accounts.  
**FR-07** The system shall allow administrators to edit user accounts.  
**FR-08** The system shall allow administrators to delete user accounts.  
**FR-09** The system shall allow administrators to assign roles to users.  
**FR-10** The system shall display a list of users with role information.  

## 8.3 Product and Category Management

**FR-11** The system shall allow authorized users to create products.  
**FR-12** The system shall allow authorized users to edit product details.  
**FR-13** The system shall allow authorized users to delete products.  
**FR-14** The system shall store SKU, barcode, name, category, supplier, and reorder level for products.  
**FR-15** The system shall allow category creation, editing, and deletion.  
**FR-16** The system shall display a product list page.  

## 8.4 Supplier Management

**FR-17** The system shall allow authorized users to add suppliers.  
**FR-18** The system shall allow authorized users to edit supplier details.  
**FR-19** The system shall allow authorized users to delete suppliers.  
**FR-20** The system shall store supplier contact details.  
**FR-21** The system shall link suppliers to products where applicable.  

## 8.5 Warehouse Location Management

**FR-22** The system shall allow creation of warehouse locations.  
**FR-23** The system shall support rack/bin/shelf-style location structure.  
**FR-24** The system shall allow products to be assigned to warehouse locations.  
**FR-25** The system shall display product storage locations.  

## 8.6 Inventory Management

**FR-26** The system shall maintain inventory records for each product.  
**FR-27** The system shall display current stock quantity.  
**FR-28** The system shall display available stock quantity.  
**FR-29** The system shall display reserved stock quantity where applicable.  
**FR-30** The system shall allow inventory search and filtering.  
**FR-31** The system shall display inventory details for selected products.  

## 8.7 Stock-In and Stock-Out

**FR-32** The system shall allow authorized users to record stock-in transactions.  
**FR-33** The system shall allow authorized users to record stock-out transactions.  
**FR-34** The system shall validate stock movement quantities.  
**FR-35** The system shall update inventory automatically after stock-in.  
**FR-36** The system shall update inventory automatically after stock-out.  
**FR-37** The system shall record movement type, date, time, and responsible user.  

## 8.8 Stock Adjustment

**FR-38** The system shall allow authorized users to adjust stock quantities.  
**FR-39** The system shall require a reason for stock adjustment.  
**FR-40** The system shall log stock adjustment history.  

## 8.9 Batch and Expiry Management

**FR-41** The system shall store batch numbers for relevant products.  
**FR-42** The system shall store manufacture dates where required.  
**FR-43** The system shall store expiry dates for perishable products.  
**FR-44** The system shall associate batch records with products and inventory.  
**FR-45** The system shall identify near-expiry products.  
**FR-46** The system shall identify expired products.  

## 8.10 Alerts and Notifications

**FR-47** The system shall generate low-stock alerts when stock is below reorder level.  
**FR-48** The system shall generate expiry-related alerts.  
**FR-49** The system shall display active alerts on the dashboard.  
**FR-50** The system shall allow alerts to be reviewed and resolved where appropriate.  

## 8.11 Dashboard and Reporting

**FR-51** The system shall provide a dashboard showing key warehouse summaries.  
**FR-52** The dashboard shall show total products count.  
**FR-53** The dashboard shall show total suppliers count.  
**FR-54** The dashboard shall show low-stock item count.  
**FR-55** The dashboard shall show expired and near-expiry counts.  
**FR-56** The system shall generate stock summary reports.  
**FR-57** The system shall generate low-stock reports.  
**FR-58** The system shall generate expiry reports.  
**FR-59** The system shall generate stock movement reports.  

## 8.12 API and Integration

**FR-60** The system shall provide backend API endpoints for frontend communication.  
**FR-61** The system shall validate API requests before processing.  
**FR-62** The system shall return appropriate success and error responses.  

---

# 9. Non-Functional Requirements

## 9.1 Usability
**NFR-01** The system should have a clean, user-friendly interface.  
**NFR-02** Users should be able to perform common tasks with minimal training.  
**NFR-03** Forms and pages should be easy to navigate and understand.  

## 9.2 Performance
**NFR-04** The system should load common pages within an acceptable time under normal usage.  
**NFR-05** Search and filtering should respond quickly for typical warehouse data volume.  

## 9.3 Security
**NFR-06** The system must require authentication for protected features.  
**NFR-07** Passwords must not be stored in plain text.  
**NFR-08** Role-based access must restrict unauthorized actions.  
**NFR-09** Sensitive operations should be logged where appropriate.  

## 9.4 Reliability
**NFR-10** The system should maintain consistent data across frontend, backend, and database.  
**NFR-11** The system should reduce the chance of data loss through proper validation and storage practices.  

## 9.5 Maintainability
**NFR-12** The codebase should be modular and organized.  
**NFR-13** The project should include documentation for setup, deployment, and testing.  
**NFR-14** The system should be designed for future enhancement.  

## 9.6 Scalability
**NFR-15** The system should support future expansion of products, users, and inventory data.  
**NFR-16** The architecture should allow additional features to be added later.  

## 9.7 Compatibility
**NFR-17** The system should work on current modern web browsers.  
**NFR-18** The system should support typical desktop screen sizes used in business environments.  

## 9.8 Accessibility
**NFR-19** The user interface should follow clear accessibility practices such as readable text, labels, and usable navigation.  

---

# 10. User Stories

- As an administrator, I want to manage users and roles so that only authorized people can access system functions.
- As a warehouse staff member, I want to record stock-in transactions so that inventory stays accurate.
- As a warehouse staff member, I want to record stock-out transactions so that warehouse movement is tracked correctly.
- As a warehouse manager, I want to see low-stock alerts so that I can plan replenishment on time.
- As a warehouse manager, I want to monitor expiry dates so that product wastage is reduced.
- As a user, I want to search products and inventory quickly so that I can perform tasks efficiently.
- As a manager, I want to view dashboard summaries and reports so that I can make informed decisions.

---

# 11. Use Cases

## UC-01 User Login and Role-Based Access
**Actors:** Administrator, Warehouse Manager, Warehouse Staff  
**Description:** A user selects a role, enters login credentials, and accesses the system based on the authenticated account role. If the user account does not exist, the system provides an option to create a new account.  
**Preconditions:**  
- The login page is available  
- The user must select a role before attempting login  
- Existing users must already have an account in the system  
**Postconditions:**  
- Valid users are redirected to the correct dashboard based on their role  
- Invalid users are shown an appropriate error message  
- New users may create an account and return to the login page  
**Detailed UI/UX Reference:**  
- [View UC-01 in UI/UX Design](ui-ux-design.md#uc-01-user-login-and-role-based-access)

## UC-02 Manage Products
**Actors:** Administrator, Warehouse Manager  
**Description:** User creates, updates, views, or deletes product information, including assigning products to categories and maintaining key product details required for warehouse inventory management.  
**Preconditions:**  
- User is authenticated and authorized  
- The product management page is available  
- Categories required for assignment are available in the system  
**Postconditions:**  
- Product data is stored or updated successfully  
- Product-category assignment is saved correctly  
- The updated product list is displayed to the user  
**Detailed UI/UX Reference:**  
- [View UC-02 in UI/UX Design](ui-ux-design.md#uc-02-manage-products)

## UC-03 Manage Suppliers
**Actors:** Administrator, Warehouse Manager  
**Description:** User creates, updates, views, or deletes supplier records, including maintaining supplier contact details and supporting supplier-product relationships required for warehouse inventory operations.  
**Preconditions:**  
- User is authenticated and authorized  
- The supplier management page is available  
**Postconditions:**  
- Supplier data is stored or updated successfully  
- Supplier contact details are maintained correctly  
- The updated supplier list is displayed to the user  
**Detailed UI/UX Reference:**  
- [View UC-03 in UI/UX Design](ui-ux-design.md#uc-03-manage-suppliers)

## UC-04 Record Stock-In
**Actors:** Warehouse Staff, Warehouse Manager  
**Description:** User records newly received inventory into the system by entering product, quantity, warehouse location, batch details, and other receiving information.  
**Preconditions:**  
- User is authenticated and authorized  
- The stock-in page is available  
- Product exists in the system  
- A valid warehouse location is available for storing the received stock  
**Postconditions:**  
- Inventory quantity increases successfully  
- Stock movement is logged in the system  
- Batch and expiry information is recorded where required  
- Updated stock is reflected in the inventory page  
**Detailed UI/UX Reference:**  
- [View UC-04 in UI/UX Design](ui-ux-design.md#uc-04-record-stock-in)

## UC-05 Record Stock-Out
**Actors:** Warehouse Staff, Warehouse Manager  
**Description:** User records inventory leaving the warehouse by selecting the product, quantity, and warehouse location so that stock levels are updated accurately and outgoing movement is tracked.  
**Preconditions:**  
- User is authenticated and authorized  
- The stock-out page is available  
- Product exists in the system  
- Sufficient stock is available in the selected location  
**Postconditions:**  
- Inventory quantity decreases successfully  
- Stock movement is logged in the system  
- Updated stock quantity is reflected in the inventory page  
**Detailed UI/UX Reference:**  
- [View UC-05 in UI/UX Design](ui-ux-design.md#uc-05-record-stock-out)

## UC-06 Adjust Inventory
**Actors:** Warehouse Manager  
**Description:** User adjusts stock levels for correction purposes by updating the inventory quantity for a selected product and location, while recording the reason for the change.  
**Preconditions:**  
- User is authenticated and authorized  
- The inventory adjustment page is available  
- The selected product exists in the system  
- The selected warehouse location exists in the system  
**Postconditions:**  
- Inventory quantity is updated successfully  
- The adjustment is logged with a reason  
- The updated quantity is displayed in the inventory page  
**Detailed UI/UX Reference:**  
- [View UC-06 in UI/UX Design](ui-ux-design.md#uc-06-adjust-inventory)

## UC-07 Track Expiry and Batches
**Actors:** Warehouse Manager, Warehouse Staff  
**Description:** User views batch and expiry data for perishable goods so that expired and near-expiry items can be identified quickly and managed appropriately.  
**Preconditions:**  
- User is authenticated and authorized  
- The batch and expiry tracking page is available  
- Batch data exists for relevant products  
**Postconditions:**  
- User can identify expired or near-expiry items  
- Batch and expiry details are displayed clearly  
- Users can review products that require follow-up action  
**Detailed UI/UX Reference:**  
- [View UC-07 in UI/UX Design](ui-ux-design.md#uc-07-track-expiry-and-batches)

## UC-08 View Reports
**Actors:** Administrator, Warehouse Manager  
**Description:** User views stock, alert, and movement reports to monitor warehouse performance, inventory status, and operational activity.  
**Preconditions:**  
- User is authenticated and authorized  
- The reports page is available  
- Relevant report data exists in the system  
**Postconditions:**  
- User can review operational performance and stock status  
- Selected report data is displayed in a readable format  
- User may filter or export report results where supported  
**Detailed UI/UX Reference:**  
- [View UC-08 in UI/UX Design](ui-ux-design.md#uc-08-view-reports)

---

# 12. Data Requirements

## 12.1 Main Data Entities

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

## 12.2 Key Data Fields

### Users
- user_id
- full_name
- email
- password_hash
- role_id
- created_at

### Roles
- role_id
- role_name

### Products
- product_id
- sku
- barcode
- product_name
- category_id
- supplier_id
- reorder_level
- image_url
- created_at

### Categories
- category_id
- category_name

### Suppliers
- supplier_id
- supplier_name
- contact_person
- phone
- email
- address

### Warehouse Locations
- location_id
- location_code
- rack
- bin
- shelf
- description

### Inventory
- inventory_id
- product_id
- location_id
- quantity_on_hand
- quantity_available
- quantity_reserved
- updated_at

### Stock Movements
- movement_id
- product_id
- movement_type
- quantity
- user_id
- movement_date
- reason

### Batches
- batch_id
- product_id
- batch_number
- manufacture_date
- expiry_date

### Alerts
- alert_id
- product_id
- alert_type
- alert_message
- status
- created_at

---

# 13. Business Rules

- Only authorized users may access restricted modules.
- Product stock cannot go below zero during stock-out unless adjustment is explicitly allowed by role.
- Stock adjustment requires a valid reason.
- Perishable products should include expiry-related data where applicable.
- Low-stock alerts should trigger when quantity falls below reorder level.
- Critical operational data should be stored consistently and accurately.

---

# 14. System Constraints

- System must be built with React, Node.js, Express, and PostgreSQL.
- The project is constrained by academic timeline and team size.
- The project focuses on warehouse inventory operations only.
- Advanced enterprise integrations are excluded from the first version.

---

# 15. Acceptance Criteria

The system will be considered acceptable when:

- Users can log in securely based on role permissions
- Products, categories, suppliers, and locations can be managed successfully
- Inventory updates correctly after stock-in, stock-out, and adjustments
- Batch and expiry details are stored and displayed correctly
- Low-stock and expiry alerts are visible
- Dashboard summaries and reports are available
- Major workflows pass functional testing
- Core project documentation is completed

---

# 16. Risks and Considerations

- Risk of incorrect data entry by users
- Risk of delays in development due to time constraints
- Risk of database design changes during development
- Risk of integration issues between frontend and backend
- Risk of incomplete testing before final demonstration
- Risk of legal and compliance gaps if privacy and security controls are ignored

Mitigation will include validation rules, modular design, regular team review, structured testing, and secure handling of data.

---

# 17. Future Enhancements

Potential future improvements may include:

- Barcode scanner integration
- Purchase order management
- Mobile application support
- Advanced analytics and forecasting
- Email or SMS notifications
- Multi-warehouse support
- Supplier portal integration

---

# 18. Conclusion

This Software Requirements Specification defines the requirements for the Moonlight Warehouse Management System, a web-based solution for warehouse inventory management in an Australian e-commerce grocery business. The system is intended to improve accuracy, reduce manual effort, support perishable goods management, and enhance warehouse operations through secure, centralized, and scalable software. This document will guide the design, development, testing, and deployment of the project.
