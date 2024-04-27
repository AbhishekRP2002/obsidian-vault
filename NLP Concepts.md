##### Text Pre-processing
- Cleaning
- Lemmatization
- Stemming
- Removal of Punctuations
- Stopwords Removal
##### Text Representation
- Bag Of Words
- Count Vector
- One-hot encoding
- TF-IDF
- Word2Vec
- Doc2Vec
- Vector Embeddings and Semantic search
##### Information Extraction
- Speech Tagging
- POS Tagging
- NER
- Custom NER
##### Transfer Learning
- Pre-trained model using HuggingFace models or any other Model hub
- Understand Transformers library and fine-tuning language models in HF 
##### LLMs
-  RAG
-  Fine-tuning LLMs
- Creating custom agents
- Creating Pipelines
- Understand Vector DBs and use them to solve traditional problems first then SOTA
- LangChain 
- LlamaIndex
##### Distributed ML and MLOps
- Spark NLP


### NLP Semantic Similarity: Identifying Synonyms in a Large Corpus of Words

Identifying synonyms in a large corpus of words involves natural language processing (NLP) techniques and various methods to capture semantic similarity between words. Here are several approaches that can be used:

### 1. Word Embeddings:

- Train word embeddings using methods like **Word2Vec**, **GloVe**, or **FastText**. These methods represent words as dense vectors in a continuous vector space. Similar words are expected to have similar vector representations.
- Calculate **cosine similarity** between word vectors to measure their similarity. Words with high cosine similarity are likely to be synonyms.

### 2. Distributional Semantics:

- Analyze the distributional patterns of words in the corpus. Words that appear in similar contexts or have similar neighbors are likely to be synonyms.
- Techniques like **Latent Semantic Analysis (LSA)** or **Latent Dirichlet Allocation (LDA)** can be applied to capture the underlying semantic structure of the corpus.

### 3. WordNet:

- **WordNe**t is a lexical database that relates words to one another in terms of synonyms, hypernyms, hyponyms, etc. It can be used to identify synonyms.
- You can leverage WordNet's structure and relationships to find synonyms for a given word.

### 4. Contextual Embeddings:

- Use pre-trained contextual embeddings like **BERT**, **GPT**, or **ELMo** to capture not just word meanings but also their context in a sentence. These embeddings are trained on large corpora and can provide a more nuanced understanding of word similarity.


##### NLI (Natural Language Inference)
NLI is a subset of NLP in which we determine the logical relationship between two texts or text fragments. AKA RTE (Recognising Textual Entailment).The relationship can fall into one of three categories: entailment, contradiction, or neutral.
- Entailment : if meaning of the hypothesis can be inferred or deduced from the premise
- Contradiction : if hypothesis contradicts or is opposite to the premise
- Neutral : if none of the above case
