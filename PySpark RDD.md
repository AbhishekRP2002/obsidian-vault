RDD - Resilient Distributed Datasets -->Fundamental data structure of Apache Spark which allows distributed memory abstractions and disitributed colleection of immutable objects.
- Mainly used for faster I/O operations with in-memory computations
- Done by using `parallelize()`  method and `df.rdd` for DataFrame objects
- RDD is a distributed collection of data elements spread across many machines in the cluster.
- We can move from RDD to DataFrame (If RDD is in tabular format) by **toDF()** method or we can do the reverse by the **.rdd** method.

RDD is an abstraction by Spark engine to handle and represent large collection of data which is distributed across the cluster.
- Spark Dataframe - built on top of RDDs
  - A spark DataFrame is a distributed collection of data organized into named columns. It is conceptually equal to a table in a relational database.
  - logically equivalent to relational tables
- RDDs --> Immutable in nature [ref](https://luminousmen.com/post/why-apache-spark-rdd-is-immutable#why-are-rdds-immutable)
- RDD does not infer schema like DataFrames and Datasets in Spark, user has to specify it.
- RDD provides `compile-time type safety` unlike Dataframe APIs ( if you try to access a column which DNE in the table ,DataFrame API wont show the compile-time error , will show run-time error only)
- **Note**
  - No built in Optimization engine for RDD(like `catalyst optimizer and Tungsten execution engine which are available for DataFrame API and Dataset API.`)
  - RDD - Efficiency is decreased as serialization is performed individually on a java and scala object which takes lots of time
  - Lazy evaluation common across all the three formats
  - Although RDDs provide low-level functionality and control, they are pretty low and cause overhead


REF :
https://www.databricks.com/blog/2016/07/14/a-tale-of-three-apache-spark-apis-rdds-dataframes-and-datasets.html