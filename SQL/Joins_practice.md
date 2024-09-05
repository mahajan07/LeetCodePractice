## Replace Employee ID With The Unique Identifier
### Write a solution to show the unique ID of each user, If a user does not have a unique ID replace just show null.

```SQL
SELECT u.unique_id, e.name
FROM Employees e 
LEFT JOIN EmployeeUNI u
ON e.id = u.id
```
