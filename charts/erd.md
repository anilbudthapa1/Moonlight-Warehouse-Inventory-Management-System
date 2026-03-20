# ERD and Database Design

## Tools Used

- **[PostgreSQL](https://www.postgresql.org/)** — used as the main relational database management system for storing warehouse data
- **[pgAdmin 4](https://www.pgadmin.org/)** — used to create the database, run SQL scripts, and manage PostgreSQL objects
- **[DBeaver Community](https://dbeaver.io/)** — used to connect to the PostgreSQL database and generate the ER diagram through reverse engineering
- **[GitHub](https://github.com/)** — used for repository management, project documentation, version control, and backlog tracking

---

## Overview

The Entity Relationship Diagram (ERD) for the **Moonlight Warehouse Management System** was designed to represent the database structure for a warehouse inventory system used by an Australian e-commerce grocery business. The database was first implemented in **PostgreSQL**, where all tables, primary keys, foreign keys, and constraints were created using SQL. After the schema was successfully created in **pgAdmin 4**, the database was connected to **DBeaver**, which was used to reverse engineer the schema and automatically generate the ER diagram. This process made it easier to visualize the entities, their attributes, and the relationships between them.

The ERD is important because it provides a clear picture of how data is organized in the system. It helps developers, designers, and stakeholders understand how different business objects such as users, products, suppliers, inventory, and stock movements are connected. It also supports accurate database development, improves data consistency, and ensures that the system structure matches the functional requirements of the project.

---

## What is an ERD

An **Entity Relationship Diagram (ERD)** is a visual model used to show the structure of a database. It represents:

- **Entities** — the main objects or tables in the system
- **Attributes** — the fields or columns inside each table
- **Relationships** — the connections between one table and another

In this project, the ERD helps explain how warehouse data is stored and how the different parts of the system interact with each other.

---

## Explanation of Entity, Attribute, and Relationship

### Entity
An **entity** is a major object in the database that represents something important in the system. In relational databases, an entity is usually represented as a table.

Examples of entities in this project include:

- `users`
- `roles`
- `products`
- `suppliers`
- `categories`
- `inventory`
- `batches`
- `stock_movements`
- `warehouse_locations`
- `alerts`

For example, the `products` entity stores all information about the items managed in the warehouse.

### Attribute
An **attribute** is a property or field that belongs to an entity. In a database table, attributes are the columns.

For example, the `products` table contains attributes such as:

- `product_id`
- `sku`
- `barcode`
- `product_name`
- `category_id`
- `unit_price`
- `selling_price`
- `reorder_level`

These attributes describe each product stored in the system.

### Relationship
A **relationship** shows how one entity is connected to another. Relationships are usually created using **foreign keys**.

For example:
- a role can be assigned to many users
- a category can contain many products
- a product can have many batches
- a warehouse location can store many inventory records

Relationships are important because they ensure that related data is connected properly and stored consistently.

---

## Database Design Process

The database design process for the Moonlight Warehouse Management System followed these steps:

1. The project requirements were analysed to identify the main data needed by the system.
2. Core entities such as users, products, suppliers, inventory, and stock movements were identified.
3. Attributes were defined for each entity based on warehouse and inventory management needs.
4. Relationships between entities were planned using primary keys and foreign keys.
5. The schema was implemented in **PostgreSQL** using SQL.
6. The SQL was executed in **pgAdmin 4** to create the actual database tables.
7. The completed schema was connected to **DBeaver**.
8. DBeaver was used to reverse engineer the database and generate the ER diagram automatically.
9. The final ERD was reviewed to ensure the structure matched the project requirements.

---

## Main Entities in the System

The following entities are included in the database design:

- `roles`
- `users`
- `categories`
- `suppliers`
- `products`
- `product_suppliers`
- `warehouse_locations`
- `batches`
- `inventory`
- `stock_movements`
- `alerts`
- `customer_orders`
- `order_items`
- `purchase_orders`
- `purchase_order_items`

These entities support both core warehouse inventory management and advanced business operations such as supplier ordering and customer order fulfilment.

---

## Relationship Types in the ERD

The ERD for this project includes both **one-to-many** and **many-to-many** relationships.

### One-to-Many Relationships

A one-to-many relationship means one record in one table can be linked to many records in another table.

Examples in this project:

- **roles → users**  
  One role can be assigned to many users.

- **categories → products**  
  One category can include many products.

- **products → batches**  
  One product can have many batches.

- **products → inventory**  
  One product can appear in many inventory records.

- **warehouse_locations → inventory**  
  One location can contain many inventory records.

- **products → stock_movements**  
  One product can have many stock movement records.

- **users → stock_movements**  
  One user can perform many stock movement actions.

- **products → alerts**  
  One product can generate many alerts.

- **customer_orders → order_items**  
  One customer order can have many order items.

- **purchase_orders → purchase_order_items**  
  One purchase order can have many purchase order item records.

### Many-to-Many Relationship

A many-to-many relationship means many records in one table can be linked to many records in another. In relational databases, this is implemented using a **junction table**.

Example in this project:

- **products ↔ suppliers** through `product_suppliers`  
  One product may be supplied by multiple suppliers, and one supplier may provide multiple products.

This relationship is handled using the `product_suppliers` table.

---

## Main Table Explanations

### Roles
The `roles` table stores user role types such as Admin, Warehouse Manager, and Warehouse Staff.

### Users
The `users` table stores login and account information for system users. Each user belongs to one role.

### Categories
The `categories` table stores product categories such as vegetables, dairy, or beverages.

### Suppliers
The `suppliers` table stores supplier business information and contact details.

### Products
The `products` table stores product master data including SKU, barcode, product name, price, reorder level, and perishability.

### Product Suppliers
The `product_suppliers` table connects products and suppliers in a many-to-many relationship.

### Warehouse Locations
The `warehouse_locations` table stores the physical storage areas such as zone, rack, bin, and shelf.

### Batches
The `batches` table stores batch numbers and expiry information for products.

### Inventory
The `inventory` table stores product stock details by location and batch.

### Stock Movements
The `stock_movements` table records stock-in, stock-out, transfer, adjustment, and damage actions.

### Alerts
The `alerts` table stores system-generated low-stock, near-expiry, expired, or damaged stock alerts.

### Customer Orders
The `customer_orders` table stores basic customer order details for warehouse fulfilment support.

### Order Items
The `order_items` table stores product-level details for each customer order.

### Purchase Orders
The `purchase_orders` table stores supplier order records.

### Purchase Order Items
The `purchase_order_items` table stores item-level details for purchase orders.

---

## Why the ERD is Important for This Project

The ERD is important for the Moonlight Warehouse Management System because it:

- provides a clear visual representation of the database structure
- helps developers understand how tables are connected
- supports implementation of foreign key constraints
- improves data consistency and integrity
- reduces duplication and poor schema design
- makes development, testing, and maintenance easier
- ensures that the database supports the business requirements of the warehouse system

Because this project involves inventory, suppliers, products, expiry tracking, and stock movement, a well-designed ERD is essential for accurate and scalable database implementation.

---

## Short Technical Summary

The Moonlight Warehouse Management System database was implemented in **PostgreSQL** and managed through **pgAdmin 4**. The schema included all required entities, attributes, primary keys, foreign keys, and constraints. The database was then connected to **DBeaver**, which was used to reverse engineer the schema and generate the ER diagram automatically. The final ERD clearly shows the one-to-many and many-to-many relationships needed for warehouse inventory management.

---

## Conclusion

In conclusion, the ERD for the Moonlight Warehouse Management System provides a complete representation of the database design required to support warehouse inventory operations. It was created by first designing and implementing the schema in PostgreSQL, then generating the visual diagram through reverse engineering in DBeaver. The diagram includes key entities such as users, roles, products, suppliers, batches, inventory, stock movements, and alerts, along with their relationships. This ERD serves as an important reference for database development, system implementation, testing, and project documentation.
