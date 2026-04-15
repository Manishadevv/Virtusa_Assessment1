Banking Management System (JDBC)
A professional console-based application designed to manage core banking operations with high reliability and data persistence. This system implements a robust Three-Tier Architecture, separating the user interface, business logic, and a MySQL data layer to ensure scalable and secure account management.

Key Features:
  *Account Diversification: Implements specific business rules for Savings, Current, and Student accounts using Object-Oriented principles.
  *Persistent Storage: All user and transaction data is stored in a relational database, ensuring information is never lost after system shutdown.
  *Secure Authentication: User-specific login credentials verified directly against database records.
  *Financial Operations: 
    Deposits & Withdrawals: Updates account balances in real-time with atomic database transactions.
    Fund Transfers: Enables secure peer-to-peer transfers between accounts using unique account identifiers.
  *Automated Audit Trail: Every transaction is automatically logged into a historical ledger with precise timestamps.

Technology Stack:

Language: Java (Core Java & JDBC)
Database: MySQL 8.0+
Driver: MySQL Connector/J
Design Patterns: Abstraction, Inheritance, and Encapsulation.

Database Configuration:

      create schema Banking_System;
      use Banking_System;
      create table Accounts(
      account_num varchar(10) primary key,
      name varchar(20),
      balance double,
      username varchar(20),
      password varchar(20),
      acc_type varchar(20)
      );
      
      create table Transactions(
      id int auto_increment primary key,
      account_num varchar(10),
      action varchar(50),
      amount double,
      date datetime,
      foreign key (account_num) references accounts(account_num));	

Architecture Overview:

    DatabaseConnection: Manages the lifecycle of the MySQL connection pool.
    
    Bank: Handles high-level operations like account registration and authentication.
    
    Accounts: The abstract core containing logic for financial calculations and SQL synchronization.
    
    Savings/Current/StudentAccount: Specific implementations of withdrawal logic and limits.
    
    Main: The entry point providing an interactive menu-driven interface for the end-user.

Accounts Table:
<img width="386" height="254" alt="Screenshot 2026-04-15 161700" src="https://github.com/user-attachments/assets/4d13eb28-ed4b-45e5-a300-a2fdfcc2dacc" />

Transactions Table:
<img width="313" height="216" alt="Screenshot 2026-04-15 161705" src="https://github.com/user-attachments/assets/c6b213d1-b7a4-43fc-a672-c965c6da4a55" />
