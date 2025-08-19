A key in a database is an attribute or a set of attributes that uniquely identifies a row/tuple in a table. Keys play a crucial role in ensuring integrity and reliability of a database by enforcing unique constraints on the data and establishing relationship b/w tables.

## Super Key

- **Purpose**: Any set of columns that can uniquely identify a record
- **Properties**: May contain extra columns beyond what's needed for uniqueness
- **Example**: Employee ID + Name + Department (Employee ID alone would suffice)

## Candidate Key

- **Purpose**: Any column or combination of columns that could potentially serve as a primary key
- **Properties**: Must be unique and not null
- **Example**: Both Employee ID and Social Security Number could be candidate keys

## Primary Key
==Most important key of all==

- **Purpose**: Uniquely identifies each record in a table
- **Properties**: Cannot be null, must be unique, only one per table
- **Example**: Employee ID in an Employee table

Mandatory conditions:
- Should not be null
- Should be unique
Good to have
- Numerical
- Small
- Constant (for example Email id may not be constant in a long run)



## Alternate Key

- **Purpose**: Candidate keys that are not chosen as the primary key
- **Properties**: Unique but not designated as the main identifier
- **Example**: If Employee ID is the primary key, then SSN would be an alternate k

## Composite Key

- **Purpose**: A primary key made up of multiple columns
- **Properties**: The combination of all columns must be unique
- **Example**: Order ID + Product ID in an Order Details table

## Surrogate Key

- **Purpose**: An artificial key created by the system (often auto-incrementing)
- **Properties**: Has no business meaning, purely for database purposes
- **Example**: Auto-generated ID numbers

## Foreign Key

- **Purpose**: Creates relationships between tables by referencing the primary key of another table
- **Properties**: Can have duplicate values, can be null (unless specified otherwise)
- **Example**: Department ID in an Employee table that references the Department tab


Database Keys – Example with Employee & Department Tables

Employee Table

| EmployeeID | Name       | Email                                         | SSN         | DepartmentID |
| ---------- | ---------- | --------------------------------------------- | ----------- | ------------ |
| 101        | Alice Roy  | [alice@company.com](mailto:alice@company.com) | 111-22-3333 | 10           |
| 102        | Bob Khan   | [bob@company.com](mailto:bob@company.com)     | 222-33-4444 | 20           |
| 103        | Carol Jain | [carol@company.com](mailto:carol@company.com) | 333-44-5555 | 10           |
Department Table

| DepartmentID | DepartmentName |
| ------------ | -------------- |
| 10           | HR             |
| 20           | IT             |
## **Super Key**

- Any set of columns that uniquely identifies employees.
    
- Examples:
    
    - {EmployeeID}
        
    - {SSN}
        
    - {Email}
        
    - {EmployeeID + Name + DepartmentID} (extra columns included but still unique)
        

---

## **Candidate Key**

- Minimal keys that could act as the primary key.
    
- For Employee:
    
    - {EmployeeID}
        
    - {SSN}
        
    - {Email}
        

---

## **Primary Key**

- One candidate key chosen to uniquely identify each row.
    
- Example: **EmployeeID** in Employee table.
    

---

## **Alternate Key**

- The candidate keys not chosen as the primary key.
    
- Example: In Employee table, **SSN** and **Email** are alternate keys.
    

---

## **Composite Key**

- A key formed by combining multiple columns.
    
- Example: In a separate **EmployeeProject** table:
    
    |EmployeeID|ProjectID|Role|
    |---|---|---|
    |101|P1|Manager|
    |101|P2|Contributor|
    
    - Here **{EmployeeID + ProjectID}** is the **composite primary key**.
        

---

## **Surrogate Key**

- An artificial, system-generated key (not from business data).
    
- Example: Instead of using SSN or Email, we create an **Auto_Increment EmployeeNumber** (e.g., 1, 2, 3 …).
    

---

## **Foreign Key**

- Creates a link between tables.
    
- Example: In Employee table, **DepartmentID** is a foreign key referencing **DepartmentID** in Department table.