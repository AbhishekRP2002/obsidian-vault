**PySpark** - Python API for Spark
##### Primer :
- Speed of data-related ops taking place on a system: _processor > memory > disk > network_
- Parallel Computing vs Distributed Computing - Understand the core differences

Main: 
- PySpark = Python + JVM programme named Spark(can be written in Scala or Java) 
- `spark` connects to `sparkContext` which is a Python object from PySpark Library
- A `SparkContext` represents the connection to a Spark cluster, main entry point of Spark functionality
- Py4j - Python for Java, using this PySpark /Python programs can communicate with Java Processes and start JVM programs as well
- Using PySpark makes your Spark-based applications slower but this cant be helped , considering the low learning curve of Python

Ref: 
- [Link 1](https://medium.com/analytics-vidhya/how-does-pyspark-work-step-by-step-with-pictures-c011402ccd57)
- 