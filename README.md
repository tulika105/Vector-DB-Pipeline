<img width="1889" height="847" alt="Screenshot 2025-08-15 165816" src="https://github.com/user-attachments/assets/0151c6c8-4131-4d7c-a13b-2f54a85358f5" />

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

---

# Working with ChromaDB 

This tutorial demonstrates how to process a text data file, split it into chunks, convert those chunks into vector embeddings, and then add and query them from ChromaDB using Python.

**Step 1: Library Installation**

- Installs required packages:  
  - `chromadb`
  - `langchain`
  - `langchain-community`
  - `sentence-transformers`

**Step 2: Import Libraries**

- Imports relevant modules from LangChain:
  - Chroma vectorstore
  - Text splitter
  - Document schema
  - HuggingFace embeddings

**Step 3: Access and Read File**

- Sets the file path for the text data (e.g., `/content/AI.txt`).
- Defines a function to read the file and split the text into chunks using `RecursiveCharacterTextSplitter`.
- Converts each chunk into a `Document` object with associated metadata (chunk ID).

**Step 4: Chunking and Viewing Chunks**

- Processes the file into document chunks with specified chunk size and overlap.
- Prints each chunk to visualize how the text was split.

**Step 5: Embedding Model Initialization**

- Defines a function to initialize the HuggingFace embeddings model (`all-MiniLM-L6-v2`).
- Embeddings are generated on CPU for demonstration.

**Step 6: Generating Embeddings**

- Function generates vector embeddings for each text chunk using the initialized model.
- Embedding vectors are combined with their corresponding text and metadata.

**Step 7: Viewing Embeddings**

- Prints summary statistics (number of embeddings, embedding dimension).
- Shows a sample embedding, with text preview, metadata, and a sample of embedding vector values.

**Step 8: Adding Embeddings to ChromaDB**

- Initializes a ChromaDB client and creates/gets a collection named `"my_documents"`.
- Prepares the data:
  - Texts
  - Embeddings
  - Metadatas
  - Unique IDs for each chunk
- Adds the data into the ChromaDB collection for storage and retrieval.

**Step 9: Querying ChromaDB**

- Defines a query text (e.g., `"What is AI?"`) and generates its embedding.
- Queries ChromaDB for the top 3 most similar chunks to the query embedding.
- Prints the most relevant document chunks found.

**Key Concepts Demonstrated**

- **Text Chunking:** Breaking down large documents for efficient embedding and retrieval.
- **Embeddings:** Transforming text into numerical vectors using transformer models for semantic similarity.
- **Metadata:** Keeping track of original chunk indices for traceability.
- **Vector Database (ChromaDB):** Storing and efficiently querying embeddings to find semantically similar text.
- **Retrieval:** Demonstrates how to fetch the most relevant text chunks for a given natural language query.

**General Flow**

1. Install dependencies.
2. Import libraries.
3. Read and preprocess the input text file.
4. Chunk text and assign metadata.
5. Generate embeddings for all chunks.
6. Store embeddings and metadata in ChromaDB.
7. Query the database with a text prompt to retrieve relevant information.
