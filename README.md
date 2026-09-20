# SecureShop-Database-Security-Project

# SecureShop Database Security Project

A hands-on project completed as part of the IBM Cybersecurity Analyst Professional Certificate (Coursera), focused on database design, data protection, access control, and SQL injection testing using a mock e-commerce database.

## Overview
SecureShop is a sample e-commerce database containing customer, order, product, and payment data. This project walks through importing the database, querying it, protecting sensitive data, managing user permissions, and identifying/exploiting a SQL injection vulnerability — then understanding how to prevent it.

## What I did

### 1. Database Setup & Exploration
- Imported the SecureShop schema and data into MySQL via phpMyAdmin
- Explored core tables: `customers`, `orders`, `products`, `payment_details`
- Wrote SQL queries to retrieve specific records (e.g. payment details by order ID, orders by customer name)

### 2. Data Protection
- Used MySQL's built-in encryption functions to encrypt and decrypt sensitive customer data (phone numbers)
- Applied data masking so only partial information (e.g. last two digits of a postal code) is visible, balancing privacy with operational access

### 3. Database Security & User Management
- Created a restricted "Delivery Executive" user role
- Granted SELECT, DELETE, and UPDATE permissions, verified with `SHOW GRANTS`
- Revoked the DELETE permission to enforce least-privilege access, and re-verified

### 4. SQL Injection Testing
- Identified a vulnerable query joining `orders` and `customers` on unsanitized `order_id` input
- Demonstrated a classic SQL injection attack (e.g. `1 OR 1=1`) to retrieve unauthorized records
- This highlighted why parameterized queries and input validation are non-negotiable in production systems

## Key takeaways
- Encryption and masking are complementary — one protects data at rest, the other protects it during display/operational use
- The principle of least privilege matters in practice, not just in theory — granting and revoking permissions per role is a core defensive habit
- SQL injection is still trivially exploitable when queries concatenate raw user input, which is why this remains a top OWASP risk

## Tools
MySQL, phpMyAdmin, SQL

---
*Completed as part of the IBM Cybersecurity Analyst Professional Certificate on Coursera.*
