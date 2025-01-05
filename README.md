# SQL Database Schema for Employee and Resurant Management

## Project Overview

This project implements a comprehensive relational database schema designed to manage various aspects of a business environment. The schema includes tables for employees, customers, departments, jobs, orders, items, vendors, and more. It demonstrates the creation of tables with proper constraints, relationships, and normalization to ensure data consistency and integrity.

## Features

### 1. **Employee Management**
   - Tracks employee details such as personal information, job roles, departments, and military status.
   - Includes phone management for employees with support for multiple phone types.

### 2. **Customer and Order Management**
   - Stores customer information and integrates it with orders.
   - Tracks items, quantities, and total price within each order.

### 3. **Department and Job Management**
   - Maintains department details and links employees to their respective departments.
   - Stores job titles and enforces salary constraints.

### 4. **Vendor and Store Management**
   - Handles vendor information, including locations and phone numbers.
   - Tracks store inventory, including items, their status, and expiration dates.

### 5. **Shift Management**
   - Manages employee work shifts with distinct types.

## Key Relationships

- **Employees** are linked to **departments** and **jobs**.
- **Orders** associate customers, employees, and items.
- **Vendors** supply items to the store, with contact information tracked in the vendor phone table.

## Key Constraints

- **Primary Keys:** Ensure unique identification of records in each table (e.g., `employee_id`, `department_id`, `order_id`).
- **Foreign Keys:** Establish relationships between tables to enforce referential integrity (e.g., `department_id` in `employees` references `department_id` in `departments`).
- **Unique Constraints:** Ensure unique values for critical fields like email and SSN in the `employees` table.

## SQL Schema

The database schema includes the following tables:

- **employees**: Stores employee information.
- **employee_phone**: Manages employee phone numbers.
- **customers**: Contains customer details.
- **departments**: Tracks departments and their managers.
- **jobs**: Stores job roles and salary constraints.
- **orders**: Tracks order details including customers and items.
- **items**: Manages items sold and linked to orders.
- **vendors**: Contains vendor information.
- **vendor_phone**: Manages vendor contact information.
- **shift**: Tracks employee shifts.
- **store**: Manages store inventory.

## How to Use

1. Clone this repository to your local machine:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Set up a database in your preferred DBMS (e.g., MySQL, PostgreSQL, Oracle).

3. Execute the SQL script to create tables and constraints.

4. Populate tables with data and test relationships and constraints.

5. Use SQL queries to retrieve and analyze data for your business needs.

## Example Queries

- Retrieve all active employees in a specific department:
  ```sql
  SELECT * FROM employees WHERE status = 'active' AND department_id = 1;
  ```

- Calculate the total sales for each vendor:
  ```sql
  SELECT vendor_id, SUM(total_price) AS total_sales FROM orders
  JOIN store ON orders.item_id = store.item_id
  GROUP BY vendor_id;
  ```

## Conclusion

This project provides a robust foundation for managing employees, customers, vendors, and inventory in a business environment. The schema ensures data integrity, supports complex queries, and demonstrates best practices in relational database design.

