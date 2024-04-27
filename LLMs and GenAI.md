##### Understanding LLMs in 5 formulas
- How can we reason about the behaviour of the LLMs ?
- The 5 Baseholders:
  1. `Generation`
  2. `Memory`
  3. `Efficiency`
  4. `Scaling`
  5. `Reasoning`
- Ref : https://www.youtube.com/watch?v=KCXDr-UOb9A

##### LLMs with Semantic Search

==Understanding Keyword Search== --> 
  - Count the number of shared/common words between the `query` and the `documents` which will help in framing the relevant response.
  - The document with maximum number of matches will be given higher priority for the query response. The more the # of matches, the higher is the matching score or relevancy score.
  - Workflow :
    ==Query passed to the search system --> Search system has accesss to processed documents catalog/archive where relevancy score wrt query is measured for each document --> filter/ fetch documents with maximum relevancy score to the query are returned ==
    Modifying this search system with multiple stages :
    1. Retrieval --> same as above, assign score to each document, retrieve the ones with maximum score and pass to the next stage.
       - **Inverted Index - used in this stage**
    2. Reranking --> Includes additional signals rather than just text relevancy to the query
  - *Does not include semantic meaning / conceptual meaning of the query.*
  - #TODO  CODE THIS UP AS WELL AND ADD THE NOTEBOOK LINK HERE

==Embeddings and Reranking== -->

**Embeddings** --> numeric representations of a natural language( can be a token or a sentence )
- similar words are grouped together in the vector space. 
- Understand `Sentence Embedding` and `Word Embedding` and code it up 
- visualize the vector space using `from utils import umap_plot, umap_plot_big` or `t-SNE`
**Use embeddings for dense retrieval and semantic search**
- Connect to a vector database and define a query and documents
- Project the query into the vector space to visualise the nearest documents --> Programmatically extract those documents
- Search and explore using semantic search with embeddings
- We were consuming a Vector DB until now
- Lets try to build one : 
  - use `Annoy` library
  - Break your corpus into chunks--> either  by sentences or paragraphs --> depending on the use case
  - Embed each of the chunks into it's respective vector representation
  - Use a search library like `Annoy` to create a search index on the document chunks.
  - Vector search using Approximate Nearest Neighbor Vector search libraries vs Vector search using vector databases --> whats the diff ?
    1. ![[Pasted image 20240313011342.png]]

- **Use Hybrid search( keyword + vector)**
  1. Calculate Keyword Search Relevance score and Vector search relevance score 
  2. Add other signals score ( page-ranking score and what not)
  3. Aggregate the scores 
- #TODO Read up : `Pretrained Transformers for Text Ranking : BERT and Beyond`

==Apply Reranking on top of Dense Retrieval to improve the Semantic search ==
Reranking - A way by which an LLM sorts search results from best to worst based on the relevance they have to the query.
- Rerrank  - model which is trained with labelled data of `queries - correct answers` and `queries - wrong answers`
- Rerank the responses and pass the query and re-ranked results to the LLM for response generation

==Evaluating Search Models==
- Mean Average Prescision (MAP)
- Mean Reciprocal Rank (MRR)
- Normalized Discounted Cumulative Gain(NDCG)



**==Defining my own LLM Tech Stack==**

**Preprocessing/ETL** :
**Embedding Model :**
**Vector Database :**
**LLM :**
**LLM Framework / LLM Orchestration Framework :**
**LLM Monitoring :**



##### LLM Questions to answer:
1. potential issue when an LLM is trained with Few shot learning approach ?
2. recommended strategy for refining the prompts of a model ?
3. how to improve the llm chatbot's reasoning abilities ?
4. factors affecting the optimal chunk size ?
5. "goal hijacking" --> how to avoid it in an llm built for translation task ?
6. Why do we use dense, rather than sparse, embedding vectors for semantic search?
7. What metrics are involved in evaluating an embedding model?
8. Which one of the following is NOT an approximate nearest neighbour search algorithm? 
- Hierarchical Navigable Small Worlds (HNSW)
- Facebook AI Similarity Search (FAISS)
- K-nearest neighbours (KNN)
- Locality-Sensitive Hashing (LSH)
9.  Enhancing a Legal Document Retrieval System  
   - You are part of a legal tech startup that aims to build an efficient document retrieval system for legal professionals. The system needs to retrieve relevant legal documents based on complex semantic queries. However, the team is concerned about the effectiveness of certain vector search strategies.
   - **_Considering the legal document retrieval system, which vector search strategy would you expect to be less effective when dealing with fine-grained semantic nuances in legal texts?_**
     - Vector compression-based ANN (like ScaNN) 
     - Tree-based ANN (like ANNOY)
     - Clustering-based ANN (like FAISS)
     - K-Nearest Neighbor

10. When would you be MOST likely to prefer a Cross-encoder model over a Bi-encoder?
11. LLMs perform optimally when relevant context is available in which positions within the input? - Refer needle in a haystack challenge
12. What is the purpose of nucleus sampling in language models? 
13. What is order of execution when you set both top-k and top-p together.
14. Is LLM inference memory-io bound or compute bound ?
15. To create an unbiased model, it’s sufficient to keep collecting more data and train bigger models on it.
    - True
    - False

16. Which is the correct sequential workflow of retrieval-augmented generation?  
- User submits query-> Search for relevant documents-> Language model converts query to embeddings-> Pass context to language model-> Language model outputs response
- Search for relevant documents -> Pass context to language model -> User submits query-> Language model converts query to embeddings-> Language model outputs responses
- Search for relevant documents -> User submits query -> Language model converts query to embeddings -> Pass context to language model -> Language model outputs responses
- User submits query -> Language model converts query to embeddings -> Search for relevant documents -> Pass context to language model -> Language model outputs responses
17. Which statement is TRUE about the key differences between QLoRA and LoRA in fine-tuning large language models (LLMs)?
    - QLoRA uses 4-bit quantization for higher memory efficiency, while LoRA uses 8-bit.
- QLoRA is less effective than LoRA in fine-tuning tasks.
- QLoRA reduces the number of trainable parameters, while LoRA increases them.
- QLoRA only uses pre-trained models, while LoRA can train from scratch.
18. What is the library, DeepSpeed, most efficient for in terms of cluster configuration?  
19. Which of the following statements is TRUE about the approach used in "LLM.int8()" to maintain performance accuracy during quantization?  

- It quantizes all values to 8-bit integers, regardless of their magnitude.
- It uses a separate normalization constant for each inner product in the matrix multiplication.
- It performs mixed-precision calculations, using 16-bit for outliers and 8-bit for non-outliers.
- It completely ignores outlier values during matrix multiplication.
20. What is the memory requirement for storing the weights of a 1 billion parameter LLM in full precision?
21. What is the memory requirement to fine-tune 13 billion parameter model in full precision?  
22. Why is perplexity important to consider above and beyond accuracy?  
23. What are two task-specific evaluation metrics?  

- [ ] ROUGE - for summarization tasks
- [ ] ROSE - for question/answering
- [ ] VERDE - for translation and summarization tasks
- [ ] BLEU - for translation tasks
24. What are the steps of the ReAct framework for LLM Agents?
25. What is the MAIN advantage of ReAct prompting over "chain-of-thought" reasoning?  

#### Topics to understand in LLMs
##### Prompt Engineering & Basics of LLM
- What is the difference between Predictive/Discriminative AI and Generative AI?
- What is LLM and how are LLMs trained?
- What is a token in a language model?
- How to estimate the cost of running a SaaS-based & Open-source LLM model?
- Explaining the Temperature parameter and how to set it.
- Different decoding strategies for picking an output token.
- Different ways to define stopping criteria in a large language model.
- How to use a stop sequence in LLMs.
- Basic structure of prompt engineering.
- In-Context learning.
- Types of prompt engineering.
- Aspects to keep in mind while using few-shots prompting.
- Strategies to write a good prompt.
- Hallucination & controlling it through prompt engineering.
- Improving the reasoning ability of LLM through prompt engineering.
- Improving LLM reasoning if your COT prompt fails.

##### Retrieval Augmented Generation (RAG) Systems
- Increasing accuracy, reliability & making answers verifiable in LLM.
- How does Retrieval augmented generation (RAG) work?
- Benefits of using a RAG system.
- Architecture patterns for customizing your LLM with proprietary data.
- When to use Fine-tuning instead of RAG.

##### Data Chunking
- What is chunking and why do we chunk our data?
- Factors that influence chunk size.
- Different types of chunking methods.
- Finding the ideal chunk size.

##### Embedding Model
- Vector embeddings and embedding models.
- Using embedding models in the context of LLM application.
- Difference in embedding of short and long content.
- Benchmarking embedding models on your own data.
- Improving a sentence transformer model used for embedding.

##### Vector DB
- What is a vector DB?
- How vector DB is different from traditional databases.
- How a vector database works.
- Difference between vector index, vector DB & vector plugins.
- Different vector search strategies.
- Clustering to reduce search space: when it fails and mitigation.
- Random projection index.
- Locality-sensitive hashing (LHS) indexing method.
- Product quantization (PQ) indexing method.
- Comparing Vector indices for a project.
- Deciding the ideal search similarity metrics.
- Types and challenges of filtering in vector DB.
- Determining the best vector database for your needs.

##### Search
- The importance of very good search.
- Architecture patterns for information retrieval & semantic search.
- Achieving efficient and accurate search results in large-scale datasets.
- Keyword-based retrieval method.
- Fine-tuning re-ranking models.
- Common metric in information retrieval and its failures.
- Evaluating a recommendation system.
- Comparing information retrieval metrics.

##### Large Language Models
- Detailed explanation of self-attention.
- Disadvantages of the self-attention mechanism and overcoming them.
- What is positional encoding?
- Detailed explanation of Transformer architecture.
- Advantages of using a transformer over LSTM.
- Difference between local attention and global attention.
- Addressing transformers' heavy computation and memory usage.
- Increasing the context length of an LLM.
- Optimizing transformer architecture for a large vocabulary.

##### Supervised Fine-tuning (SFT) LLM
- What is fine-tuning and its necessity in LLM.
- Scenarios requiring fine-tuning of LLM.
- Making the decision of fine-tuning.
- Creating a fine-tuning dataset for Q&A.
- Improving the model to answer only with sufficient context.
- Setting hyperparameters for fine-tuning.
- Estimating infra requirements for fine-tuning LLM.
- Fine-tuning LLM on consumer hardware.
- Categories of the PEFT method.
- Different re-parameterized methods for fine-tuning LLM.

##### Deployment
- Why quantization does not decrease the accuracy of LLM.

##### Hallucination
- Different forms of hallucinations.
- Controlling hallucinations at different levels.

##### Evaluation
- Evaluating the best LLM model for your use case.
- Evaluating a RAG-based system.
- Metrics for evaluating LLM.
- The Chain of verification.

##### Agents
- Basic concepts of an agent and strategies for implementation.
- The necessity of agents and common strategies for implementation.
- ReAct prompting with code examples and advantages.
- Plan and Execute prompting strategy.
- OpenAI functions strategy with code examples.
- Difference between OpenAI functions and LangChain Agents.

##### Prompt Hacking
- What is prompt hacking and its significance?
- Different types of prompt hacking.
- Defense tactics against prompt hacking.


