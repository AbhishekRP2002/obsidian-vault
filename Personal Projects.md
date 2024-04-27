##### project idea 1

- https://huggingface.co/datasets/RayBernard/leetcode
- https://github.com/alirezadir/leetcode-summerizer/blob/main/main.py

- collect leetcode data, understand the data properly define problem statements that can be solved using machine learning :
  - predict the level of difficulty of the problem ( multilabel classification)
  - can I use ML to predict the acceptance rate ? What are the features that I need to consider ?
  - given a problem, can I identify the algorithm that can be used to solve it ?
  - given a leetcode problem, can we generate an proposed algorithm to solve it ? ( maybe try using LLMs ) --> NA
  - ==Leetcode problems recommendation system ==
    - Fetch user's recent data using Leetcode GraphQL API
    - Based on the user's data recommend top 10 problems

2. https://www.kaggle.com/datasets/andrewmvd/data-engineer-jobs


##### project idea 2

**problem statement :** 
- #TODO given a job description, find the relevant skills that are required for the job role. Do i need  the skills to also have descriptions ?
- scope this project to understand about vector databases and semantic search, showcase an comparative analysis of multiple vector databases, note your results and understandings in a blog on medium or hashnode platform
- Project workflow : Define the problem statement clearly with OKRs  --> Define the requirements and pre-requisites --> create an high level proposal or flow of your solution --> implement the solution
- **define the dataset** --> 
- **vector DBs to consider** --> 
  1. qdrant
  2. opensearch
  3. weaviate
  4. pinecone
  5. deeplake by activeloop
  6. pgvector by postgres
  7. milvus
  can i use more ? refer to the Vector DB comparison web page
- [ref article](https://adamsblum.medium.com/comparing-vector-databases-feedfb92c6f1)

##### project 3
topic : **research paper recommendation system**
objective : 
- try to create a research paper recsys that recommends similar research papers based on abstract text of the papers.
- try to expose this as an api end point or as a streamlit application
effectiveness of the solution:
- 
approach : 