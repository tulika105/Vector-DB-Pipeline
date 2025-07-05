# Vector-DB-Pipeline
This tutorial demonstrates how to convert text data into embeddings using a pre-trained embedding model and store them for similarity search using FAISS. Here's a summary of the steps:
- Install Libraries: The necessary libraries (sentence-transformers and faiss-cpu) are installed to handle embedding generation and similarity search.
- Import Libraries: Required libraries are imported, including faiss for managing the vector database and SentenceTransformer for creating sentence embeddings.
- Text Data: A set of example sentences is defined for embedding generation.
- Generate Embeddings: A pre-trained model (paraphrase-MiniLM-L6-v2) is used to convert the sentences into 768-dimensional vectors.
- Print Embeddings: The resulting embeddings are printed, representing the sentences in a high-dimensional vector space.
- Query and Relevant Vector Retrieval: After generating the embeddings, you can perform a similarity search. A query sentence is converted into an embedding, and then FAISS is used to find the most relevant vectors from the database. This allows for efficient retrieval of similar sentences based on semantic meaning.
