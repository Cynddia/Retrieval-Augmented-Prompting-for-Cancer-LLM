# Retrieval-Augmented-Prompting-for-Cancer-LLM
Implements a retrieval-augmented approach to enhance language model (GPT-2) performance. Retrieves relevant text chunks from a large corpus to provide context and improve response accuracy for user queries.

## Overview
The project consists of the following main steps:

Text Extraction: Extracts and cleans text from multiple PDF files.
Embedding Generation: Converts text chunks into embeddings using the BioBERT model.
Indexing and Retrieval: Uses FAISS to index embeddings and retrieve relevant text chunks based on user queries.
Prompt Preparation: Creates prompts for a language model by combining retrieved context with user queries.

## Steps
1. Text Extraction and Preprocessing
Extract Text from PDFs:

Uses PyPDF2 to read and extract text from PDF files.
Cleans the extracted text by removing specified sections (e.g., References, Acknowledgements).
Combine and Clean Text:

Merges text from all PDF files into a single string.
Splits the text into chunks for further processing.

2. Embedding Generation
Initialize Model:

Loads the BioBERT model from the SentenceTransformer library.
Generate Embeddings:

Encodes text chunks into embeddings using the BioBERT model.

3. Indexing and Retrieval
Create FAISS Index:

Initializes a FAISS index with the dimensionality of the embeddings.
Adds embeddings to the FAISS index.
Retrieve Relevant Chunks:

Encodes the user query into an embedding.
Searches the FAISS index to find the most relevant text chunks based on the query embedding.

4. Prompt Preparation
Prepare Context:

Combines retrieved text chunks into a coherent context.
Generate LLM Prompt:

Forms a prompt for the language model by including both the context and the user query.
