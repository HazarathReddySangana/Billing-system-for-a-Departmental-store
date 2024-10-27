# Billing-system-for-a-Departmental-store

Here’s a summary you can use to document this database schema on GitHub, explaining its structure, relationships, and purpose:

---

# E-commerce Database Schema

This project defines a basic relational database schema for an e-commerce system. The schema includes tables to manage stores, products, customers, orders, and order details. This setup enables tracking of customer orders across multiple stores, keeping records of available products, and calculating order subtotals and totals. 

## Database Structure

### 1. **store**
   - Holds information about stores where products are sold.
   - **Columns:**
     - `store_id` (INT, Primary Key): Unique identifier for each store.
     - `name` (VARCHAR(100)): Name of the store.
     - `location` (VARCHAR(255)): Physical location of the store.

### 2. **product**
   - Stores information about products available for purchase.
   - **Columns:**
     - `product_id` (INT, Primary Key): Unique identifier for each product.
     - `name` (VARCHAR(100)): Product name.
     - `price` (DECIMAL(10,2)): Price per unit of the product.
     - `stock` (INT): Quantity of product available in stock.

### 3. **bill_customer**
   - Manages customer information.
   - **Columns:**
     - `customer_id` (INT, Primary Key): Unique identifier for each customer.
     - `name` (VARCHAR(100)): Customer name.
     - `contact_info` (VARCHAR(255)): Contact details (e.g., phone number).

### 4. **bill_orders**
   - Contains information about customer orders.
   - **Columns:**
     - `order_id` (INT, Primary Key): Unique identifier for each order.
     - `customer_id` (INT, Foreign Key): References `bill_customer(customer_id)` to identify the ordering customer.
     - `store_id` (INT, Foreign Key): References `store(store_id)` to identify the store where the order was placed.
     - `order_date` (DATE): Date the order was placed.
     - `total_amount` (DECIMAL(10,2)): Total amount for the order.

### 5. **order_details**
   - Tracks the specific products included in each order, allowing multiple products per order.
   - **Columns:**
     - `order_id` (INT, Foreign Key): References `bill_orders(order_id)`.
     - `product_id` (INT, Foreign Key): References `product(product_id)`.
     - `quantity` (INT): Quantity of the product ordered.
     - `subtotal` (DECIMAL(10,2)): Subtotal cost for the quantity ordered.
   - **Primary Key:** Composite of `order_id` and `product_id`.

## Sample Data

Sample entries for each table are included to demonstrate the relationships between tables. Here’s a brief overview:

- **Stores**: Contains records of stores in different locations.
- **Products**: Lists products with prices and stock levels.
- **Customers**: Holds basic customer information.
- **Orders**: Stores order details, including customer, store, date, and total amount.
- **Order Details**: Tracks individual products within orders, quantities, and subtotals.

## SQL Code for Data Insertion and Queries

The script includes:
1. SQL code for creating each table.
2. Sample data insertion for each table.
3. Queries to retrieve data from each table.

## Usage

Run the SQL script in a MySQL or compatible database environment to create the tables, insert the sample data, and test the queries.

---

This should provide a comprehensive summary for anyone browsing your GitHub repository!


![Screenshot 2024-10-27 085505](https://github.com/user-attachments/assets/b570d2bf-db3a-4e51-b06d-5cf18084965d)
![Screenshot 2024-10-27 085533](https://github.com/user-attachments/assets/a9ef3368-3146-4dd7-845e-fd632da4f746)
![Screenshot 2024-10-27 085551](https://github.com/user-attachments/assets/1bab15b3-1b62-485c-ab37-9cf6169b1123)
![Screenshot 2024-10-27 085643](https://github.com/user-attachments/assets/647185e9-66b6-4c03-a863-492ab79284ca)
![Screenshot 2024-10-27 085745](https://github.com/user-attachments/assets/4e2f4250-da41-494f-bb50-13e36dad0736)
