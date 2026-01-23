# Intuition
Remove duplicate means the first one is the only survivor, and the first one is the lowest id


# Code
```mysql []
# Write your MySQL query statement below
WITH ids AS (
    SELECT MIN(id) AS id
    FROM   Person
    GROUP BY email
)
DELETE FROM Person
WHERE
    id not IN (SELECT id FROM ids);
```

```psql []
-- Write your psql query statement below
DELETE FROM Person
WHERE
    id not IN
(
    SELECT DISTINCT ON (email)
       id
    FROM   Person
    ORDER  BY email, id
);
```
