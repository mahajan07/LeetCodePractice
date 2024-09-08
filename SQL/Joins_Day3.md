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

### Employee Bonus - Write a solution to report the name and bonus amount of each employee with a bonus less than 1000.

```SQL
SELECT E.name, B.bonus
FROM Employee E
LEFT JOIN Bonus B ON E.empId = B.empId
WHERE B.bonus < 1000 or B.bonus Is Null
```


### Students and Examinations - Write a solution to find the number of times each student attended each exam.

```SQL
SELECT S.student_id, S.student_name, Sub.subject_name, COUNT(Exam.student_id) As attended_exams
FROM Students S
CROSS Join Subjects Sub
LEFT Join Examinations Exam 
ON S.student_id = Exam.student_id
AND Sub.subject_name = Exam.subject_name
Group by S.student_id, S.student_name, Sub.subject_name
```



