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
### Invalid Tweets - Write a solution to find the IDs of the invalid tweets. The tweet is invalid if the number of characters used in the content of the tweet is strictly greater than 15.

```SQL
select t.tweet_id
from Tweets t
where length(t.content) >=15;
```
