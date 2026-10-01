# MySQL-DDL-commands-and-constraints
# MySQL Assignment 1

## 📌 Overview

This repository contains my **MySQL Assignment 1**, focused on fundamental SQL concepts including database creation, table creation, table modification, constraints, and relationships.

The project uses an **Employee Database** to demonstrate practical implementation of SQL and relational database concepts.

---

## 🛠️ Technologies Used

* **MySQL**
* **SQL**
* MySQL Workbench

---

## 🎯 Concepts Covered

* Database creation and selection
* Table creation
* Data types
* Primary Key
* Foreign Key
* `NOT NULL`
* `UNIQUE`
* `CHECK`
* `DEFAULT`
* `AUTO_INCREMENT`
* `ENUM`
* Adding columns
* Modifying columns
* Dropping columns
* Renaming columns
* Renaming tables
* `TRUNCATE TABLE`
* `DROP TABLE`
* `DROP DATABASE`

---

## 🗄️ Database Structure

The project creates an `employee` database with the following tables:

### 1. Departments

Stores department information.

| Column          | Data Type    | Constraint       |
| --------------- | ------------ | ---------------- |
| department_id   | INT          | PRIMARY KEY      |
| department_name | VARCHAR(100) | NOT NULL, UNIQUE |

### 2. Location

Stores employee location information.

| Column      | Data Type   | Constraint                  |
| ----------- | ----------- | --------------------------- |
| location_id | INT         | AUTO_INCREMENT, PRIMARY KEY |
| location    | VARCHAR(30) | NOT NULL, UNIQUE            |

### 3. Employees

Stores employee details and connects employees with departments and locations.

| Column        | Data Type     | Constraint           |
| ------------- | ------------- | -------------------- |
| employee_id   | INT           | PRIMARY KEY          |
| employee_name | VARCHAR(50)   | NOT NULL             |
| gender        | ENUM('M','F') | NOT NULL             |
| age           | INT           | CHECK(age >= 18)     |
| hire_date     | DATE          | DEFAULT CURRENT_DATE |
| designation   | VARCHAR(100)  | —                    |
| department_id | INT           | FOREIGN KEY          |
| location_id   | INT           | FOREIGN KEY          |
| salary        | DECIMAL(10,2) | —                    |

The `employees` table establishes relationships with both the `departments` and `location` tables using foreign keys.

---

## 🔑 Constraints Demonstrated

### Primary Key

Used to uniquely identify records.

```sql
department_id INT PRIMARY KEY
```

### Foreign Key

Used to establish relationships between tables.

```sql
FOREIGN KEY (department_id)
REFERENCES departments(department_id)
```

```sql
FOREIGN KEY (location_id)
REFERENCES location(location_id)
```

### NOT NULL

Ensures that required values are provided.

```sql
employee_name VARCHAR(50) NOT NULL
```

### UNIQUE

Prevents duplicate values.

```sql
department_name VARCHAR(100) NOT NULL UNIQUE
```

### CHECK

Validates data based on a condition.

```sql
age INT CHECK(age >= 18)
```

### DEFAULT

Provides a default value when no value is specified.

```sql
hire_date DATE DEFAULT(CURRENT_DATE)
```

### AUTO_INCREMENT

Automatically generates numeric IDs.

```sql
location_id INT AUTO_INCREMENT PRIMARY KEY
```

---

## 🔧 Table Modification

The assignment also demonstrates how existing tables can be modified.

### Add Column

```sql
ALTER TABLE employees
ADD COLUMN email VARCHAR(50);
```

### Modify Column

```sql
ALTER TABLE employees
MODIFY COLUMN designation VARCHAR(200);
```

### Drop Column

```sql
ALTER TABLE employees
DROP COLUMN age;
```

### Rename Column

```sql
ALTER TABLE employees
RENAME COLUMN hire_date TO date_of_joining;
```

### Rename Table

```sql
RENAME TABLE departments TO depatments_info;
```

```sql
RENAME TABLE location TO locations;
```

---

## 🗑️ Table and Database Operations

The project also demonstrates:

```sql
TRUNCATE TABLE employees;
```

```sql
DROP TABLE employees;
```

```sql
DROP DATABASE employee;
```

These commands were included to practice different database and table management operations.

---

## 📂 Project File

```text
MySql assignment 1.sql
```

---

## ▶️ How to Run

1. Install **MySQL** and **MySQL Workbench**.
2. Open the SQL file in MySQL Workbench.
3. Execute the queries sequentially.
4. Review the database and table structures using `DESC` commands.

> **Note:** This assignment contains `TRUNCATE`, `DROP TABLE`, and `DROP DATABASE` commands. Run the script only in a practice/development environment.

---

## 📚 Learning Outcomes

Through this assignment, I gained practical experience in:

* Designing basic relational database structures
* Creating and modifying MySQL tables
* Applying SQL constraints
* Creating relationships using foreign keys
* Understanding primary and foreign keys
* Working with different SQL data types
* Managing database and table structures using DDL commands

---

## 👩‍💻 Author

**Anju Das M**
Data Analyst Trainee

### Skills

`SQL` • `MySQL` • `Excel` • `Power BI` • `Power Query` • `Python` • `Pandas` • `DAX`

---

⭐ **If you find this project useful, feel free to star the repository!**

