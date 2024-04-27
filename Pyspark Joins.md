- `df1.join(df2, on = <matching_key> , how = <type_of_join>)`
- `df1.join(df2, join_condition, join_type)`

- **Types of Joins **:
  - Inner Join: Returns only the rows with matching keys in both DataFrames.
  - Left Join: Returns all rows from the left DataFrame and matching rows from the right DataFrame.
    - All columns from both left and right are returned as an output
  - Right Join: Returns all rows from the right DataFrame and matching rows from the left DataFrame.
  - Full Outer Join: Returns all rows from both DataFrames, including matching and non-matching rows.
  - Left Semi Join: Returns all rows from the left DataFrame where there is a match in the right DataFrame.
    - Note that it ignores all the columns from the right DataFrame.
    - this join only provides columns from the left dataset for records that meet the join expression/condition in the right dataset; it eliminates records that do not fit the join expression from both the left and right datasets.
  - Left Anti Join: Returns all rows from the left DataFrame where there is no match in the right DataFrame.

Speed Up the Joins :
- [ref link](https://freedium.cfd/https://towardsdatascience.com/the-art-of-joining-in-spark-dcbd33d693c)


- Broadcast Join --> if one table is smaller than the other, then the smaller table is broadcasted to each node in the cluster for join operations
- 
