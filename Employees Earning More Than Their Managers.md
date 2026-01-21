# Intuition
Join each row to its manager having less salary

# Code
```mysql []
# Write your MySQL query statement below
SELECT
emp.name AS Employee
FROM
Employee AS emp
JOIN Employee AS manager 
ON manager.id=emp.managerId AND emp.salary > manager.salary;
```
