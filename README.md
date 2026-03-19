E-Commerce Data Model (Week 4 Project)
Objective

The objective of this project is to design a structured and normalized database schema for an e-commerce platform. This includes identifying entities, defining relationships, establishing primary and foreign keys, and representing the system using an Entity-Relationship Diagram (ERD).

Database Tables and Description
1. Customers

This table stores information about users of the platform.

Attributes:

cust_id (Primary Key)

name

email

phone

created_at

2. Addresses

This table stores multiple addresses for each customer.

Attributes:

address_id (Primary Key)

customer_id (Foreign Key → Customers)

street

city

state

postal_code

country

Reason:
A customer can have multiple addresses, so separating this table improves normalization.

3. Orders

This table records all orders placed by customers.

Attributes:

order_id (Primary Key)

customer_id (Foreign Key → Customers)

order_date

total_amount

4. Payments

This table stores payment details for each order.

Attributes:

payment_id (Primary Key)

order_id (Foreign Key → Orders)

payment_method

payment_status

payment_date

amount

Reason:
Separating payment details ensures flexibility and supports multiple payment methods.

5. Products

This table contains all available products.

Attributes:

product_id (Primary Key)

category_id (Foreign Key → Categories)

name

price

6. Categories

This table organizes products into groups.

Attributes:

category_id (Primary Key)

category_name

7. Order_Items

This table acts as a bridge between Orders and Products.

Attributes:

order_item_id (Primary Key)

order_id (Foreign Key → Orders)

product_id (Foreign Key → Products)

quantity

price

Reason:
This resolves the many-to-many relationship between orders and products.

