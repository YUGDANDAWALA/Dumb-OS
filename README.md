# Dumb_OS Java Project

## Overview
Dumb_OS is a feature-rich Java-based console application that simulates an operating system environment. It integrates multiple modules, including classic games, a robust file management system, a phonebook with database support, and a mini e-commerce (Amazon-like) platform. The project is designed for learning, demonstration, and as a foundation for more advanced Java/database applications.

## Key Features & Modules

### 1. Games
- **Tic Tac Toe**: Play in single or double player mode. Features synchronized gameplay, toss logic, and win/draw detection.
- **Digital Cricket**: Simulates a cricket match with batting and bowling logic, randomization, and score tracking.
- **Hangman**: Single and double player modes. Includes hints, point system, and word selection from a database.
- **Game Engine Classes**: Includes custom stack and queue implementations for game logic.

### 2. File Management System (Drive)
- **User Registration & Login**: Secure registration and login with username, password, and profile details.
- **File Operations**:
  - Upload files (stores name, type, size, content as BLOB, creation date)
  - Delete files by name
  - Update file names
  - List all files for a user (with metadata)
  - Download files (restore from database to disk)
  - Read file content directly from the database
- **Database Design**: Each user has a dedicated table for their files. File metadata and content are stored in MySQL.
- **File Metadata**: Uses Java NIO to fetch file attributes (creation time, etc.).

### 3. Phonebook
- **Binary Search Tree (BST) Implementation**: Contacts are managed in-memory using a BST for fast search, insert, and delete.
- **Database Integration**: Contacts are also persisted in MySQL for durability.
- **Features**:
  - Add, update, delete, search, and display contacts
  - Input validation for phone numbers (custom exceptions)
  - Sorted display of contacts

### 4. Amazon-like E-Commerce System
- **Product Browsing**: View products by category (Fashion, Grocery, Electronics, Beauty, Footwear). Product details and images are fetched from the database.
- **Cart Management**: Add products to cart, view cart, remove items, and calculate total.
- **Order Placement**: Place orders, view order history, and simulate payment (with card validation and input checks).
- **Product Images**: Download and view product images stored as BLOBs in the database.
- **Database Tables**: `Products`, `Cart`, `Orders` with appropriate fields and relationships.
- **Order Delivery Simulation**: Delivery date is set 5 days after order date.

### 5. Account Management
- **Registration**: Collects user details (first/last name, gender, DOB, phone, email, username, password).
- **Login**: User authentication with credential checks.
- **Profile Management**: View and print user details after login.
- **Username Generation**: Username is auto-generated based on user details.

## Technologies Used
- **Java**: JDBC, Threads, File I/O, Collections, Synchronization, NIO
- **MySQL**: Database for all persistent storage (user data, files, products, contacts, game words)
- **Console-based UI**: All interactions are via the command line

## How to Run
1. **Clone the repository** (see GitHub instructions below)
2. **Set up MySQL database:**
   - Create a database named `Dumb_OS` (and others as needed, e.g., `console_chaos` for Hangman).
   - Import/create tables as per the code (tables are auto-created if not present).
   - Update the database connection strings in the code if needed (default: user `root`, no password).
3. **Compile the Java code:**
   - Open terminal in the `src` directory.
   - Run: `javac Dumb_OS.java`
4. **Run the application:**
   - Run: `java Dumb_OS`
5. **Follow the on-screen instructions** to use the various modules.

## Database Schema (Summary)
- **Account**: Stores user registration details (name, gender, DOB, phone, email, username, password)
- **User File Tables**: Each user has a table for their files (name, type, size, content, a_id, date_created)
- **Products**: Product catalog for Amazon module (id, name, price, photo, stock, description, section)
- **Cart**: User shopping cart (product_name, product_price, quantity, user_id)
- **Orders**: Order history (order_id, order_date, total_amount, delivery_date, user_id)
- **contacts**: Phonebook contacts (phone number, name)
- **hangman_words**: Words and hints for Hangman game

## Project Structure
```
project-root/
│
├── src/
│   └── Dumb_OS.java

## Example Usage
- **Play Games**: Choose from Tic Tac Toe, Digital Cricket, or Hangman from the main menu.
- **Manage Files**: Register/login, then upload, download, or view files in your personal drive.
- **Phonebook**: Add, update, search, or delete contacts; view all contacts in sorted order.
- **Shop Online**: Browse products, add to cart, checkout, and view order history in the Amazon module.

## Notes & Tips
- Make sure MySQL is running and accessible.
- Update database credentials in the code as needed.
- For any issues, check the stack trace printed in the console.
- The application is modular; you can use only the modules you need.
- File operations require files to be present on the local drive.
- Payment simulation in Amazon module is for demonstration only.
- Exception handling is implemented for most user and database operations.
- Some modules (like Hangman) require additional tables (e.g., `console_chaos` database for words).
- The code is designed for educational purposes and can be extended for more advanced use cases.
**Author:** Your Name  
**Date:** August 2025
