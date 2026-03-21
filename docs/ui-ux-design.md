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

This document explains the user interface and user experience design of the Moonlight Warehouse Management System. It focuses on how users interact with the system through key workflows such as login, product management, supplier management, stock movement, inventory adjustment, expiry tracking, and reporting. Each use case below includes a short explanation of how the workflow supports the system from a UI/UX perspective, followed by a reference screenshot or diagram stored in the repository.

---

# 2. Use Cases

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

### Main Flow
1. The user opens the login page
2. The user selects a role
3. The user enters email and password
4. The system checks whether the account exists
5. The system validates the password
6. The system checks whether the selected role matches the registered account role
7. The system creates a session or token
8. The system redirects the user to the correct dashboard

### Alternative Flows
- If no role is selected, the system asks the user to select a role
- If the account does not exist, the system offers account registration
- If the password is incorrect, the system displays an invalid credentials message
- If the selected role does not match the account role, the system displays a role mismatch message

### Explanation
This use case is important because login is the first interaction point between the user and the system. The UI must make role selection, credential input, and error handling clear and simple. From a user experience perspective, this workflow ensures that different user roles are redirected to the correct dashboard and are only allowed to access features relevant to their responsibilities.

### Reference Screenshot / Diagram
[View UC-01 User Login and Role-Based Access](../charts/resources/diagram/uc-01-user-login-and-role-based-access.png)

---

## UC-02 Manage Products

**Actors:** Administrator, Warehouse Manager  
**Description:** User creates, updates, views, or deletes product information.

**Preconditions:**
- User is authenticated and authorized

**Postconditions:**
- Product data is stored or updated successfully

### Main Flow
1. The user opens the product management page
2. The user views the list of products
3. The user selects add, edit, view, or delete
4. The system displays the product form or product details
5. The user submits the data
6. The system validates the input
7. The system saves the product data
8. The updated list is displayed

### Alternative Flows
- If required product fields are missing, the system shows validation errors
- If duplicate SKU or barcode is entered, the system displays an error
- If the user cancels the action, the system returns to the product list

### Explanation
This use case supports one of the most important administrative functions in the system. The UI must allow authorized users to manage product data efficiently and accurately. Product forms should be well structured, validation messages should be clear, and the product list should be easy to search and review so that warehouse operations remain organized and consistent.

### Reference Screenshot / Diagram
[View UC-02 Manage Products](../charts/resources/diagram/uc-02-manage-products.png)

---

## UC-03 Manage Suppliers

**Actors:** Administrator, Warehouse Manager  
**Description:** User creates, updates, views, or deletes supplier records.

**Preconditions:**
- User is authenticated and authorized

**Postconditions:**
- Supplier data is updated successfully

### Main Flow
1. The user opens the supplier management page
2. The user views the supplier list
3. The user selects add, edit, view, or delete
4. The system shows the supplier form
5. The user enters or updates supplier details
6. The system validates the entered data
7. The system saves the supplier record
8. The updated supplier list is displayed

### Alternative Flows
- If required fields are missing, the system shows validation errors
- If invalid supplier contact details are entered, the system displays an error
- If the user cancels, the system returns to the supplier list

### Explanation
This use case ensures that supplier information is managed in a structured and accessible way. From a UI/UX perspective, supplier pages should make it easy to view contact details, maintain records, and support relationships between suppliers and products. A clear layout and simple forms reduce errors and improve data quality.

### Reference Screenshot / Diagram
[View UC-03 Manage Suppliers](../charts/resources/diagram/uc-03-manage-suppliers.png)

---

## UC-04 Record Stock-In

**Actors:** Warehouse Staff, Warehouse Manager  
**Description:** User records newly received inventory into the system.

**Preconditions:**
- Product exists in the system

**Postconditions:**
- Inventory quantity increases and movement is logged

### Main Flow
1. The user opens the stock-in page
2. The user selects the product
3. The user enters quantity, location, batch details, and other required data
4. The system validates the stock-in details
5. The system updates inventory quantities
6. The system creates a stock movement log
7. The updated stock is reflected in the inventory page

### Alternative Flows
- If the selected product does not exist, the system prevents submission
- If quantity is invalid, the system shows an error
- If batch details are needed for perishable items, the system requests batch information

### Explanation
This use case is central to warehouse receiving operations. The user interface should allow staff to quickly enter received stock while reducing mistakes in quantities, product selection, and batch data. Good UI design in this workflow improves operational speed and helps ensure that inventory records remain accurate after goods are received.

### Reference Screenshot / Diagram
[View UC-04 Record Stock-In](../charts/resources/diagram/uc-04-record-stock-in.png)

---

## UC-05 Record Stock-Out

**Actors:** Warehouse Staff, Warehouse Manager  
**Description:** User records inventory leaving the warehouse.

**Preconditions:**
- Sufficient stock is available

**Postconditions:**
- Inventory quantity decreases and movement is logged

### Main Flow
1. The user opens the stock-out page
2. The user selects the product
3. The user enters quantity and location information
4. The system checks whether enough stock is available
5. The system validates the request
6. The system decreases inventory quantity
7. The system logs the stock-out movement
8. The updated stock quantity is displayed

### Alternative Flows
- If stock is insufficient, the system shows an error
- If invalid quantity is entered, the system requests correction
- If the user cancels, no changes are saved

### Explanation
This workflow supports the outgoing movement of warehouse stock. The UI should help staff perform this action accurately by clearly displaying available quantities, product details, and validation messages. This reduces the chance of over-issuing stock and ensures that every stock-out action is properly recorded for traceability.

### Reference Screenshot / Diagram
[View UC-05 Record Stock-Out](../charts/resources/diagram/uc-05-record-stock-out.png)

---

## UC-06 Adjust Inventory

**Actors:** Warehouse Manager  
**Description:** User adjusts stock levels for correction purposes.

**Preconditions:**
- User is authorized

**Postconditions:**
- Inventory is updated and adjustment is logged with reason

### Main Flow
1. The warehouse manager opens the inventory adjustment page
2. The manager selects the product and location
3. The manager enters the corrected quantity
4. The manager enters a reason for adjustment
5. The system validates the adjustment details
6. The system updates the inventory record
7. The system logs the adjustment activity
8. The updated quantity is displayed

### Alternative Flows
- If no reason is given, the system prevents submission
- If the quantity is invalid, the system shows an error
- If the user exits without saving, no change is made

### Explanation
Inventory adjustment is a sensitive workflow because it changes stock records directly. The interface should therefore require a clear reason, confirm the change, and make the action traceable. From a UX perspective, this supports accountability and reduces the risk of accidental or unsupported inventory changes.

### Reference Screenshot / Diagram
[View UC-06 Adjust Inventory](../charts/resources/diagram/uc-06-adjust-inventory.png)

---

## UC-07 Track Expiry and Batches

**Actors:** Warehouse Manager, Warehouse Staff  
**Description:** User views batch and expiry data for perishable goods.

**Preconditions:**
- Batch data exists

**Postconditions:**
- User can identify expired or near-expiry items

### Main Flow
1. The user opens the batch and expiry tracking page
2. The system displays batch-based product records
3. The user searches or filters batch records
4. The system shows batch number, manufacture date, and expiry date
5. The system highlights near-expiry and expired products
6. The user reviews the results and plans action

### Alternative Flows
- If no batch data exists, the system shows a no-data message
- If no matching product is found, the system shows an empty result

### Explanation
This use case is especially important for grocery warehouse operations because many products are perishable. The UI should make expiry information easy to identify through filters, labels, and highlighted warning states. This helps users quickly find products that require urgent attention and reduces the risk of wastage.

### Reference Screenshot / Diagram
[View UC-07 Track Expiry and Batches](../charts/resources/diagram/uc-07-track-expiry-and-batches.png)

---

## UC-08 View Reports

**Actors:** Administrator, Warehouse Manager  
**Description:** User views stock, alert, and movement reports.

**Preconditions:**
- Relevant data exists in the system

**Postconditions:**
- User can review operational performance and stock status

### Main Flow
1. The user opens the reports page
2. The user selects a report type
3. The system retrieves the relevant report data
4. The report is displayed in a readable format
5. The user may apply filters or export the result
6. The user reviews warehouse performance and stock details

### Alternative Flows
- If no report data exists, the system shows an empty-state message
- If invalid filters are selected, the system requests correction

### Explanation
Reports support decision-making by giving managers and administrators a clear overview of stock, alerts, and movement history. The interface should present this information in a readable format with helpful filters and summaries. Good reporting UI helps users understand operational status quickly and supports better planning.

### Reference Screenshot / Diagram
[View UC-08 View Reports](../charts/resources/diagram/uc-08-view-reports.png)

---

# 3. Summary

The UI/UX design of the Moonlight Warehouse Management System is intended to support efficient and role-based interaction for the main warehouse workflows. Each use case above explains not only the functional flow, but also the user experience purpose behind the interface design. The linked diagrams and screenshots provide visual evidence of each workflow and help keep the project documentation organized and easy to follow.
