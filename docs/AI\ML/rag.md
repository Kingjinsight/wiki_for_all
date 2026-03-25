# RAG(Retrieval-Augmented Generation)

The core idea is to retrieve relevant documents, then feed them as context to the LLM.

## Pipeline

1. Indexing(offline, done once)
   - Take your documents(pdf, code, wikis, etc.)
   - Split them into chunks by chunking strategy
   - Embed each chunk into a vector using an embedding model
   - Store vector in a [Vector Database](vector_database.md)
2. Retrieval (at query time)
   - User asks a question
   - Embed the query using the same embedding model
   - Do a similarity search(cosine/dot product) in the vector DB
   - Get the top-k most relevant chunks by reranking
3. Generation
   - Stuff those chunks into the LLM prompt as context
   - The LLM reads the context and generates an answer grounded in it
  
## Why it works

Embedding models map sematically similar text to nearby vector in high-dimensional space, it enables fuzzy semantic search rather than keyword matching.
