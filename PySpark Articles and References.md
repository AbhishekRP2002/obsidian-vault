- https://www.legendu.net/en/blog/pyspark-udf/
- https://medium.com/@uzzaman.ahmed/pyspark-string-functions-a-comprehensive-guide-842c3d68351b
- https://medium.com/@uzzaman.ahmed/pyspark-normal-and-misc-functions-a-comprehensive-guide-fb6e2c61fb77#:~:text=SPARK_PARTITION_ID&text=In%20this%20example%2C%20we%20use%20the%20repartition()%20function%20to,each%20row%20in%20the%20DataFrame.
- https://ai.gopubby.com/pyspark-dataframes-a-comprehensive-guide-6cac34964c02

Notes : 
- [[PySpark Optimization]]



#### How to apply functions on pyspark dataframe ?

- Pandas UDFs / Vectorized UDFs
- UDFs - Python UDFs
- `mapInPandas()`
- `rdd.map()` - create an rdd partition and apply the function to each element of the partition independently
  - rdd operations are implemented row wise generally
- `rdd.mapPartitions()` - applies a function to each partition of an RDD ( more like aggregator functions `groupBy` n all)
- `rdd.mapPartitionsWithIndex()` - similar to `mapPartitions` but also includes the partition’s index.
- `rdd.flatMap()` - similar to `map` but each element can be mapped to an output of 0 or more elements (a sequence)
- `apply()` after converting the spark DataFrame to pandas-on-spark DataFrame
  - runs Pandas API built on top of Spark
    - Ref : [applying a function against pandas-on-Spark DataFrame](https://spark.apache.org/docs/latest/api/python/user_guide/pandas_on_spark/transform_apply.html)
- `df.groupBy(spark_partition_id()).apply(function_name)`
- 