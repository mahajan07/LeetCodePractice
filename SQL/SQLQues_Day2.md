## Questions
### Article Views I - Write a solution to find all the authors that viewed at least one of their own articles.

```SQL
select distinct t.author_id as id
from Views t
where t.author_id = t.viewer_id;
```
### Invalid Tweets - Write a solution to find the IDs of the invalid tweets. The tweet is invalid if the number of characters used in the content of the tweet is strictly greater than 15.
