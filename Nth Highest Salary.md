# Intuition
The minimum of the top N if there more than N-1 salaries

# Code
```mysql []
CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN
  RETURN (
    # Write your MySQL query statement below.
    WITH salaries AS (
        SELECT
            DISTINCT(salary) AS sal
        FROM Employee
        ORDER BY sal DESC
        LIMIT N
    )
    SELECT (
        SELECT min(sal) FROM salaries 
        WHERE (SELECT count(sal) FROM salaries) = N
    ) AS value
  );
END
```
