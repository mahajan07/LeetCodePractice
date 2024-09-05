## Replace Employee ID With The Unique Identifier
### Write a solution to show the unique ID of each user, If a user does not have a unique ID replace just show null.

```SQL
SELECT u.unique_id, e.name
FROM Employees e 
LEFT JOIN EmployeeUNI u
ON e.id = u.id
```
### Product Sales Analysis I - Write a solution to report the product_name, year, and price for each sale_id in the Sales table.

```SQL
SELECT p.product_name, s.year, s.price
FROM Sales s 
LEFT JOIN Product p
ON s.product_id = p.product_id;
```
