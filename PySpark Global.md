Pyspark - The _de facto_ for distributed data processing in big data domain
[[How PySpark Works ? Internals of PySpark]]
[[PySpark Articles and References]]
[[PySpark Optimization]]
[[PySpark RDD]]
[[Pyspark Joins]]

Transformations : operations on dataframe which result in a new dataframe
Actions : operations on dataframe which usually returns a value

Thanks to **lazy evaluation**, transformations are not run until an action is made. When an action is eventually made, Spark doesn’t just run the pending transformations one by one. It looks at all the transformations it has to run, and the catalyst optimizer figures out the most efficient way to combine them.
Due to **lazy evaluation,** what’s happening behind the scenes is that every time an action (green) is called, Spark then runs all the pending transformations (grey) together.

And every time an action is called, Spark is re-evaluating all the transformations (grey) _repeatedly._


**References:** 

https://luminousmen.com/?tag=spark
https://spark.apache.org/docs/latest/rdd-programming-guide.html#transformations