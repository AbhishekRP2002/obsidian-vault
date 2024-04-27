1. Serialization Optimisation
		- What is serialisation in the first place ? --> converting data into a format that can be easily transmitted usually byte format.
		- By default - Tungsten engine and Catalyst Optimiser is used in Spark
		- Methods :
			- use `Binary Formats like Avro or Parquet` , why though ? --> these formats are more compact and efficient as compared to CSV or JSON
			- Kyro Serialization : use this instead of Java Ser. but caveat is it may not support all data types.
			  `conf = SparkConf().set("spark.serializer", "org.apache.spark.serializer.KryoSerializer")`  
			- Use custom serialisation as per your need in the code
2. Data Partitioning
   -  #TODO: Add more here 
		- play with `repartition()` and `coalesce()` and understand them clearly
		- data partitioning helps in parallelizing data processing tasks
		- it involves dividing a dataset into smaller chunks or partitions to distribute the workload across multiple nodes in a spark cluster.
		- data partitioning strategies : 
		  1. `partitionBy` : allows users to partition data based on one or more columns. It's commonly used for partitioning DataFrames before writing them to disk using formats like Parquet or Hive. improves query performance and optimize data retrieval in downstream tasks
		     `# Partition data by 'year'
		     `df.partitionBy('year').write.parquet('partitioned_data/')`
		     `
		  2. `repartition` method in PySpark DataFrame allows users to explicitly control the partitioning of data by specifying the desired number of partitions.
		     - triggers full shuffle of the data across the cluster nodes
		     - `df.repartition(10).write.parquet('repartitioned_data/')`
		3. `coalesce` method in PySpark DataFrame allows users to reduce the number of partitions in a DataFrame without triggering a full shuffle. Unlike `repartition`, which involves a full shuffle operation, `coalesce` minimizes data movement by merging partitions on the same executor node whenever possible.	
1. Try to reduce the number of shuffles across multiple executors or worker nodes 
   - use Broadcast variables, considering the variable size is not too big
   - Understand `MapReduce`  paradigm and how shuffling occurs 
   - don't use aggregate functions much --> they lead to shuffling 
2. Persisting intermediates -- Utilise the caching mechanism
3. Use correct `Join Strategy`
   - #TODO add more notes here about Joins and understand about Joins, it's types and the pros and cons
4. Avoid using `collect()`  --> it brings all the data to the driver node, which involves data transfer overhead and can cause out-of-memory errors.
5. Understand the execution plan of SQL queries and figure how you can leverage them.
6. Shuffle has a high cost associated with it due to movement of data between the nodes. Between two stages, one shuffle occurs : Use `explain()` for explainability in your code and code exection plan.
   - In Spark, the reason for shuffle are transformations like _join_, _groupBy_, _reduceBy_, _repartition_, and _distinct_.
     - Aim to decrease network I/O by using less number of machines in the cluster and large resources in each -- A design decision
7. Replace **Joins & Aggregations with Windows** - for a operation consisting of aggregation followed by a join , `window functions`  are more optimised 
8. Use **Bucketing** --> Learn more about it -- Bucketing VS Partitioning
9. _checkpointing_ the data frame, you don't need to recalculate all of the previous transformations applied on the data frame, it is stored on disk forever.Caching is also an alternative for a similar purpose in order to increase performance. It obviously requires much more memory compared to _checkpointing_. There is a good comparison between _caching_ and _checkpointing_, and when to prefer one of them to the other. You can take a look at [here](https://medium.com/@adrianchang/apache-spark-checkpointing-ebd2ec065371).
    - This is also an opinion [here](https://medium.com/tblx-insider/how-we-reduced-our-apache-spark-cluster-cost-using-best-practices-ac1f176379ac), where to place the _checkpoints_ in the data pipeline
10. Don't  use UDFs instead use Pandas UDFs or mapInPandas () or any other better approach
11. Handle the **skewed data** by `Salting` (adding randomization to the data to help it to be distributed more uniformly.)
12. Use proper file formats like [Apache Parquet](https://parquet.apache.org/) which is a columnar storage format designed to select only queried columns and skip over the rest. It gives the fastest read performance with Spark. _Parquet_ arranges data in columns, putting related values close to each other to optimize query performance, minimize I/O, and facilitate compression. Furthermore, it implements [column pruning and predicate pushdown](https://umbertogriffo.gitbook.io/apache-spark-best-practices-and-tuning/storage/use-the-best-data-format) (filters based on stats) which is simply a process of only selecting the required data for processing when querying a huge table. It prevents loading unnecessary parts of the data in-memory and reduces network usage.
13. **Speed up and Optimize Spark Joins **
    - [[Pyspark Joins]]
14. **Avoid Wide Transformations (Narrow vs. Wide Transformations):**
    - Spark distinguishes between narrow and wide transformations. Narrow transformations (e.g., `map`, `filter`) do not require data shuffling and can be executed in parallel.
    - Wide transformations (e.g., `groupByKey`, `reduceByKey`, `join`) involve data shuffling and can be more expensive in terms of computation and network I/O.
    - Minimize the use of wide transformations when possible to improve parallelism.

15.  **Optimising Output File Size in Apache Spark** :
    - use `coalesce()` over `repartition()` 
    - Use `repartition` when you need to control the number of partitions in a DataFrame and potentially redistribute data across partitions. This will do partition in memory only.  
	- Use `coalesce` when you want to reduce the number of partitions without shuffling data. This will do partition in memory only.  
	- Use `partitionBy` when writing data to a partitioned file format, organising data based on specific columns for efficient querying. This will do partition at storage disk level
16. See if you have enough partitions in your dataframe. even if you have a lot of resources but less number of Partitions then your parallelism will be restricted with the number of Partitions you have.
17. use `cache()` or `persist()` wherever required : Spark provides an optimization mechanism to store the intermediate computation of a Spark DataFrame so they can be reused in subsequent actions.
    - Caching or persisting of Spark DataFrame or Dataset is a lazy operation, meaning a DataFrame will not be cached until you trigger an action.
    - cache() calls persist() under the hood
    - Difference between both:
      1. `cache` is  `persist` with the default storage level `MEMORY_ONLY`
         - `cache` prioritises memory pehle then uske baad on disk if memory is full completely
      2. in `persist()` we can save the intermediate results in 5 storage levels. `MEMORY_ONLY, MEMORY_AND_DISK, MEMORY_ONLY_SER, MEMORY_AND_DISK_SER, DISK_ONLY`
	- Unlike a dataframe, which has a .cache() default of disk and storage, an RDD has a default of 100% memory.
      
      
20. **Predicate Pushdown**  
    - an optimisation strategy that pushes filtering predicates (conditions in WHERE clauses) as close to the data source as possible. By doing so, it minimises the amount of data that needs to be loaded into memory and processed, resulting in improved performance and resource utilisation. 
    - Reduced Data Movement
    - Enhanced CPU efficiency
    - Storage Optimization
21. **Join Strategies**
    - Broadcast Hash Join --> effective when one of the dataframes' is smaller in size such that it fits into the memory of each executor ( default size is 10MB ). This minimizes data shuffling and accelerates the join operation, as the join occurs within the same node, resulting in a decrease in network overhead.
    - Shuffle Hash Join --> if neither of the tables can fit in the memory. **Be careful when using this strategy**, as it may incur higher network and disk I/O costs, which largely decreases the performance due to the full shuffle. This method involves shuffling or redistribution of data based on join key.
    - Cartesian Product Join -->  involves joining every row from the first table with every row from the second table, making it highly resource-intensive. This strategy should be avoided for large datasets due to a significant increase in the number of records.
    - Sort Merge Join --> used when both tables are large and cannot fit in the memory. It Involves sorting both tables based on the join key and then merging them. It provides good performance for certain types of queries but requires sorting, which can be computationally expensive.
22. Methods for Parallelization in Spark:
    - **Native Spark:** if you’re using Spark data frames and libraries (e.g. MLlib), then your code we’ll be parallelized and distributed natively by Spark.
    - **Thread Pools:** The [multiprocessing library](https://docs.python.org/3/library/multiprocessing.html) can be used to run concurrent Python threads, and even perform operations with Spark data frames. --> avoid this as it does not leverage multiple worker nodes
    - **Pandas UDFs**
      
##### Caching

- Cache or persist smaller tables in memory if they are reused in multiple stages of a Spark application.
- Reduces the need to recompute the smaller table for each operation.

##### Broadcasting

- Use broadcast joins whenever applicable to leverage the benefits of data locality and reduce network overhead.

References :
[[PySpark Global]]
