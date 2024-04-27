Distributed ML --> multi-node ML system
Need --> if the  algorithm’s computational complexity outpaces the main memory, the algorithm will not scale well due to memory restrictions.
--> if the dataset if too large for the memory then it will spill off the memory and will throw error
--> for efficient hyper parameter tuning and scope of scalability

Data Parallelism and Model Parallelism:
- in data parallelism, the data is divided depending on the number of worker nodes present in the system and each worker node is used for processing the partitions of data. In this approach:

1. We partition the data into n parts, where n is the total number of workers in the compute cluster that are accessible.  
2. Each worker node contains a copy of the model, and each one trains the model using a different subset of the data.
3. Either synchronously or asynchronously, training loops are run.


- in model parallelism, we try to distribute the params of the model(eg. neural networks of large size with higher no of parameters, When the neural network model is too huge to fit into the memory of a single computer, model parallelism is often utilized.)

Distributed ML Frameworks:
- Apache Spark MLlib
- Ray
- PyTorch (offers assistance for utilizing the torch—distributed package for dispersed training.)
- TensorFlow ( built-in support for distributed training and is frequently used to construct and train deep neural networks.)
- H2O.ai
- CNTK by Microsoft (open-source deep learning framework that supports distributed training over multiple GPUs and workstations.)

Federated Learning - centralised server approach first. ( [google blog](https://research.google/blog/federated-learning-collaborative-machine-learning-without-centralized-training-data/))
It works like this: your device downloads the current model, improves it by learning from data on your phone, and then summarizes the changes as a small focused update. Only this update to the model is sent to the cloud, using encrypted communication, where it is immediately averaged with other user updates to improve the shared model. All the training data remains on your device, and no individual updates are stored in the cloud.

- Ray on Databricks
  - why need another distributed framework on top of Spark ?
    - two ways to distribute a function across a cluster.
    1. data parallelism : parts of a dataset are split up and a function acts on each part and collects the results.This is what happens in Apache Spark
    2. task parallelism / logical parallelism : multiple functions can be run concurrently and are set up in complicated pipelines using parameter servers and schedulers to coordinate dependencies. Examples include physics simulations, financial trading algorithms and advanced mathematical computations.

**what can i achieve with Ray ?**
- Scaling up Python code (ray.remote)
- Launching clusters
- RayTune
- RLlib
- Distributed Deep Learning Training
- Batch Inference / Data Processing
- Ray Serve (Model Scoring/Online Serving)
- LLM and Generative AI models for training/serving
#### Ray vs PySpark
Given a user defined custom Python Function, how can I use it on large Dataset / dataframe to leverage distributed computing or how can I handle large workloads ?
- understand what are the different ways by which I can apply or use the function the dataframe 
- do I need to convert the Spark dataframe to pandas Dataframe or pandas-on-spark dataframe to apply the functions ?
- what the ways by which I can pass a `dataframe` directly as argument in the function and perform operations or implement the custom logic ?
- how can I use Ray to perform the operations on the dataframe?
- can i use Ray on spark dataframe and pandas dataframe or any one of the two ?
- what are the industry best practices while applying custom functions on dataframes for leveraging parallel processing or distributed computing ?
- what is the existing method we are using in our pipelines ?

##### Understanding when to use GPU enabled computing for ETL Pipelines in Databricks
