## codtech-internship-task1-joins-practice
## INTRODUCTION:
This document contains SQL JOIN queries executed as part of Internship Task-1 from CODTECH.The objectives is to perform INNER JOIN,LEFT JOIN,RIGHT JOIN,FULL JOIN to combine data meaningfully using two sample tables.
## SAMPLE TABLES:
**TABLE 1: Employees**
|Employee_id|Employee_name|Department_id|
|-----------|--------------|-------------|
|101        | Ram          | 100          |
|102        | Sita         | 200          |
|103        | Lakshman     | 300          |

**TABLE 2: Departments**
|Department_id|Department_name|Location|
|--------------|---------------|-------|
|100           | HR            | Delhi |
|200           | IT            | Banglore|
|320           | Finance       | Hyderabad|

## JOINS QUERIES WITH OUTPUTS:
**1.INNER JOIN**

SELECT E.Employee_id,E.Employee_name,D.Department_id,D.Location FROM Employees E INNER JOIN Departments D ON E.Department_id=D.Department_id;

**OUTPUT:**
|Employee_id|Employee_name|Department_name|Location|
|-----------|-------------|---------------|--------|
|101        | Ram         | HR            | Delhi  |
|102        | Sita        | Finance       | Hyderabad|

**2.LEFT JOIN**

SELECT e.Employee_id,e.Employee_name,d.Department_name,d.Location FROM Employees e LEFT JOIN Departments d ON e.Department_id=d.Department_id;

**OUTPUT:**
|Employee_id|Employee_name|Department_name|Location|
|-----------|-------------|---------------|---------|
|101        | Ram         | HR            | Delhi   |
|102        | Sita        | IT            | Banglore|
|103        | Lakshman    | NULL          | NULL      |

**3.RIGHT JOIN**

SELECT e.Employee_id,e.Employee_name,d.Department_name,d.Location FROM Employees e RIGHT JOIN Departments d ON e.Department_id=d.Department_id;

**OUTPUT:**
|Employee_id|Employee_name|Department_name|Location|
|-----------|-------------|---------------|---------|
|101        | Ram         | HR            | Delhi   |
|102        | Sita        | IT            | Banglore|
|NULL       | NULL        | Finance       | Hyderabad|

**4.FULL JOIN (UNION)**

(NOTE: In Mysql FULL JOIN is not supported, so we use UNION of LEFT and RIGHT JOIN)

SELECT e.Employee_id,e.Employee_name,d.Department_name,d.Location FROM Employees e LEFT JOIN Departments d ON e.Department_id=d.Department_id;
UNION
SELECT e.Employee_id,e.Employee_name,d.Department_name,d.Location FROM Employees e RIGHT JOIN Departments d ON e.Department_id=d.Department_id;

**OUTPUT:**
|Employee_id|Employee_name|Department_name|Location|
|-----------|-------------|---------------|---------|
|101        | Ram         | HR            | Delhi   |
|102        | Sita        | IT            | Banglore|
|103        | Lakshman    | NULL          | NULL    |
|NULL       | NULL        | Finance       | Hyderabad|





















