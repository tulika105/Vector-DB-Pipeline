# **Working with FAISS**

- **Objective**: The tutorial demonstrates how to collect data, generate vector embeddings using Sentence Transformers, and query a vector database (FAISS) for semantic search tasks.

- **Step 1: Library Installation**
  - Installs required libraries: `sentence-transformers` (for generating embeddings) and `faiss-cpu` (for vector indexing and search).

- **Step 2: Import Libraries**
  - Imports `faiss` for vector search/indexing, `numpy` for array operations, and `SentenceTransformer` from `sentence-transformers` for embedding generation.

- **Step 3: Data Collection**
  - Defines a sample list of sentences (`texts`) to be embedded and searched.

- **Step 4: Data Preprocessing**
  - This step is mentioned but intentionally skipped for the demonstration.

- **Step 5: Convert Data to Vector Embeddings**
  - Loads a pre-trained sentence embedding model: `'paraphrase-MiniLM-L6-v2'`.
  - Converts each sentence in the sample data into a 768-dimensional vector using the model.

- **Step 6: Print Embeddings**
  - Displays the generated vector embeddings for each sentence.

- **Step 7: Initialize FAISS Index**
  - Converts embeddings to `float32` numpy arrays.
  - Initializes a FAISS index (`IndexFlatL2`) using L2 (Euclidean) distance for similarity search.

- **Step 8: Add Embeddings to Index**
  - Adds the sentence vector embeddings to the FAISS index for searchability.

- **Step 9: Query Preparation**
  - Defines a text query (`'what is machine learning?'`).
  - Converts the query into its corresponding vector embedding using the same model.

- **Step 10: Perform Search in FAISS**
  - Searches for the top-2 closest vectors in the FAISS index to the query embedding.
  - Retrieves both the distances and the indices of the closest vectors.

- **Step 11: Display Results**
  - Prints the original query.
  - For each of the top-2 results:
    - Prints the rank, the matching sentence from the original data, and the distance (similarity score).

- **Key Outcomes**:
  - Demonstrates a full pipeline for semantic search with vector databases.
  - Shows how to embed text, index embeddings, and perform nearest neighbor search for question-answering or information retrieval tasks.
  - Example output matches semantically relevant sentences to the query "what is machine learning?".
