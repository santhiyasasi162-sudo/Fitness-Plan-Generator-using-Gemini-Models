README.md


ER Diagram Project
Project Overview
This project contains the Entity-Relationship (ER) Diagram and database schema for a basic order management system.

The system manages:

Users

Products

Orders

Order Items

Payments

The ER diagram shows the relationships between these entities and helps in designing the relational database.

Project Structure
project/
│
├── README.md
│
├── diagrams/
│   └── er-diagram.mmd
│
└── database/
    └── schema.sql

Files Description
README.md
Contains the project description, database structure, setup instructions, and file information.

diagrams/er-diagram.mmd
Contains the ER diagram written in Mermaid syntax.

The diagram represents:

USER
  │
  │ places
  ▼
ORDER
  │
  │ contains
  ▼
ORDER_ITEM
  │
  │ refers to
  ▼
PRODUCT

ORDER
  │
  │ has
  ▼
PAYMENT

database/schema.sql
Contains the SQL commands required to create the database and tables.

Database Entities
1. USER
Stores information about system users.

Important attributes:

user_id - Primary Key

name

email

password

role

created_at

2. PRODUCT
Stores information about products.

Important attributes:

product_id - Primary Key

name

description

price

stock

created_at

3. ORDER
Stores customer order information.

Important attributes:

order_id - Primary Key

user_id - Foreign Key

total_amount

status

order_date

4. ORDER_ITEM
Stores the individual products included in an order.

Important attributes:

order_item_id - Primary Key

order_id - Foreign Key

product_id - Foreign Key

quantity

price

5. PAYMENT
Stores payment information for orders.

Important attributes:

payment_id - Primary Key

order_id - Foreign Key

amount

payment_method

payment_status

payment_date

Relationships
Relationship	Description
User → Order	A user can place multiple orders
Order → Order Item	An order contains one or more order items
Product → Order Item	A product can appear in multiple order items
Order → Payment	An order can have a payment

Technologies
Database: MySQL

Database Design: ER Diagram

Diagram Format: Mermaid

SQL: MySQL-compatible SQL

Installation
Step 1: Create the Database
Open MySQL or MySQL Workbench.

Run:

CREATE DATABASE project_db;

Step 2: Select the Database
USE project_db;

Step 3: Execute the Schema
Run the contents of:

database/schema.sql

This creates all required tables and relationships.

Viewing the ER Diagram
The file:

diagrams/er-diagram.mmd

contains the Mermaid ER diagram.

You can open the Mermaid code using a Mermaid-compatible Markdown editor or Mermaid Live Editor.

Database Relationship Summary
USER
  |
  | 1 : N
  |
ORDER
  |
  | 1 : N
  |
ORDER_ITEM
  |
  | N : 1
  |
PRODUCT

ORDER
  |
  | 1 : 0..1
  |
PAYMENT

Purpose
The purpose of this ER diagram is to provide a clear database design before implementation. Primary keys uniquely identify records, while foreign keys establish relationships between related tables.

Future Enhancements
The database can be extended with additional entities such as:

Categories

Reviews

Shopping Cart

Addresses

Delivery

Notifications

Coupons

Refunds

License
This project is intended for educational and project-development purposes.
