#### Cosine Similarity ( an attempt to understand cosine similarity in exhaustive manner )
what is cosine similarity ?
- mathematical attempt to measure or quantify the similarity between two vectors
- quantifies the cosine of the angle between two vectors, focusing on orientation/direction rather than the magnitude. ( #TODO can i define a measure which takes both into consideration --> Read up about Jaccard Similarity? why do i even want that ? will it improve the relevance between the vectors or what ?)
- range of cosine sim is [-1,1] with 1 being identical direction, 0 being perpendicularity( orthogonality) and -1 being complete opposite directions
- since it does not take magnitudes into account, it is robust to them and hence can be used in scenarios where we can encounter varying vector magnitudes like document clustering, document categorization, search engine, text mining etc..
- any data format which can be represented in vector form can leverage cosine similarity
when can I use cosine similarity and when not?
what role does it play in recommendation systems based on unstructured data ( textual data ) or information retrieval ?
what is its role in ranking algorithms ?
- 
where does other techniques which considers semantic similarity / contextual similarity stand with cosine similarity like Latent semantic analysis, t-Distributed Stochastic Neighbour Embedding(t-SNE), lexical similarity?
what are the potential applications of cosine similarity ?
- search engine -> query and results ke beech similarity score calculated using cosine similarity and based on that a ranking algorithm is defined
- clustering analysis
- content-based recommendation system --> recommend items to a user which closely match with the items that user searched previously or bought previously
- plagiarism checker
- classification of genes with similar traits 
- identifying similar protein sequences

