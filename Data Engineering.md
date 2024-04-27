##### Stream Processing VS Batch Processing
Stream processing or batch processing depends on the data flow, how the data is flowing.
Processing means any transformation or augmentation or running any logic on the data.
- Batch Processing :
  1. ad-hoc or scheduled processing using collection of data ( bulk data )
  2. first landing of data then processing
- Stream Processing :
  1. Real time data processing using continuous data
  2. continuously in-flow of data, (can be from a single source or multiple sources ) in real time.
  3. this follows event driven architecture
      eg. banking, train ticket booking 
  4. first processing then landing or loading of data 

##### Data Pipelines :
(water analogy)
- lake , oceans, rivers, are source of water but we can't use them directly --> so we pass them to Treatment plants via water pipelines, where then get treated and then from there they are transferred for commercial or household uses
  - lake, oceans --> Data Lakes, Databases
  - river --> streaming data
  - water pipeline --> data pipeline
  - processes to use clean the data or process the data : ETL(Extract Transform Load), Data Replication, Data virtualisation ( _understand this_ as here we don't need to build actual pipelines before, we can create virtual data from the source data and run queries and check if the results are consistent with our desired results. )

- Cron jobs are **a standard method of scheduling tasks to run on your server**. Cron is a service running in the background that will execute commands (jobs) at a specified time, or at a regular interval.
- Learn about Schema Drifts and Schema Evolution 


1. main features of Apache Spark:
   - handles big data processing with distributed computing or parallel computing
2. `rdd`  in Apache Spark :
   - building block of data in Spark
3. `Transformation` vs `Action`:
   - former one is a type of operation which are evaluated and processed lazily
   - #TODO  read more on this
4. How will you monitor Apache Spark Jobs/Applications?
   - from the Spark UI ? might be wrong here, need to re-check
5. main functions of Spark Core in Apache Spark :
6. ways to create `rdd` in spark : `parallelize()`  and `df.rdd`
7. shuffle operation in Spark ? How it affects the optimisation? Analogy with mapReduce algorithm ?
8. Columnar storage formats like `Parquet` and `Avro` , their advantages
9. Spark Driver and it's role ?
10. RDD lineage : #TODO  Understand the DAG and `RDD Lineage`
11. what is lazy evaluation in Apache Spark ?
12. core components of a distributed application in Apache Spark
13. difference between cache() and persist() methods in Apache Spark
14. What is Executor Memory in a Spark application?
15. Why should you define your schema and what are the two ways to attain a schema from data ? : `inferSchema()`
16. partitions in Apache Spark ?
17. concept of lineage in Spark and its significance ?
18. how to handle skewed data in PySpark
19.  different caching levels in Spark and when you would use each.
20. purpose and benefits of Spark’s broadcast variables.
21. Spark utilize memory management and storage in its execution model?
22.  Spark handles data serialization and why it is important.
23. You have a large dataset that doesn’t fit in memory. How would you optimize your Spark job to handle this situation?
24. You need to perform a join operation on two large datasets. What strategies would you employ to optimize the join performance?
25. You are working with skewed data partitions in Spark. How would you handle data skewness and ensure optimal processing?
26. You have a Spark job that is taking longer than expected to complete. What steps would you take to identify and troubleshoot performance bottlenecks?
27. You need to process nested JSON data in Spark efficiently. What approaches and techniques would you use to handle the nested structure?
28. You have a Spark job that involves iterative processing. What optimizations would you consider to reduce the overall execution time?
29. You want to efficiently process and aggregate time-series data in Spark. How would you design your Spark job to handle this requirement?
30. You want to implement an incremental data processing pipeline in Spark. How would you design and implement the pipeline to handle incremental updates efficiently?