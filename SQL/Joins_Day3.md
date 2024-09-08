## Questions
### Customer Who Visited but Did Not Make Any Transactions- Write a solution to find the IDs of the users who visited without making any transactions and the number of times they made these types of visits.
```SQL
SELECT V.customer_id, COUNT(V.visit_id) AS "count_no_trans" 
FROM Visits V
LEFT JOIN Transactions T
ON V.visit_id = T.visit_id
WHERE T.visit_id IS NULL
group by V.customer_id
```
### Rising Temperature - Write a solution to find all dates' id with higher temperatures compared to its previous dates (yesterday). Return the result table in any order.

```SQL
SELECT w1.id
FROM Weather W1
JOIN Weather W2
ON w1.recordDate = w2.recordDate - INTERVAL '1' DAY
WHERE w1.temperature < w2.temperature
```

### Average Time of Process per Machine - There is a factory website that has several machines each running the same number of processes. Write a solution to find the average time each machine takes to complete a process.

```SQL
SELECT A1.machine_id,
ROUND(AVG(CAST(A2.timestamp - A1.timestamp AS DECIMAL)), 3) AS processing_time
FROM activity A1
JOIN activity A2
ON A1.machine_id = A2.machine_id
AND A1.process_id = A2.process_id
AND A1.activity_type = 'start'
AND A2.activity_type = 'end'
group by A1.machine_id
```
