##### SQL Sub queries:

- used with operators mostly - `IN, EXISTS, ANY, ALL` , or any comparison operator as well
- Basic structure : 
  -  `||SELECT column_name(s)|`
	`||FROM table_name|`
	`||WHERE column_name operator (|`
	`||SELECT column_name|`
	`||FROM table_name|`
	`||WHERE condition);|`
- A sub query is executed first and it's result is passed to the main query
- _Innermost subqueries are evaluated before outer queries.Inner Queries Before Outer Queries_
- **`Nested Subqueries`:**
  - Subquery ke andar subquery
  - 
- #TODO Learn about **Correlated Subqueries**
- Using subquery with `FROM` 
  - if we need the result of the subquery as a table and work on top of it with our outer query
  - use by including a subquery in the `FROM` clause of a `SELECT` statement.
- [subqueries ref](https://medium.com/@manutej/mastering-sql-subqueries-comprehensive-guide-633dc50ac294)

==[Read this if you want your SQL queries to run faster on Databricks Platform](https://community.databricks.com/t5/technical-blog/top-10-query-performance-tuning-tips-for-databricks-serverless/ba-p/43218)==
