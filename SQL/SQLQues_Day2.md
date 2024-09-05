## Questions
### Article Views I - Write a solution to find all the authors that viewed at least one of their own articles.

```SQL
select distinct t.author_id as id
from Views t
where t.author_id = t.viewer_id;
```
