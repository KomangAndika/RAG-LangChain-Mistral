# RAG-LangChain-Mistral
Using RAG(Retrieval-Augmented Generation) to retrieve informationn from 10 LLM research paper, the LLM I am using Mistral 7b with LangChain Framework.
## RAG(Retrieval-Augmented Generation) with LangChain
Rag typically has two main components:
1. Indexing, basically pipeline to ingest data (Usually done Offline).
2. Retrieival + Generation, this is the actual part of the RAG, receive user query and retrieve relevant data from index and passing the model. <br>
### Indexing
- Loading Document, using document loaders, can be from Google Drive, Notion, Slack, but in this case I am using kaggle database(or basically local kaggle notebook).
- Split, using text splitter to break documents into smaller chunks, useful for indexing and feeding the model.
- Store, place to store and index the splits (VectorDB and Embedding model are here), the VectorDB I am using is FAISS and sentence-transformer for embedding.

### Retrieval + Generation
- Retrieve, given the user input, retrieve relevant splits from the VectorDB(FAISS).
- Generate, using chatmodel/LLM(in this case Mistral 7b) to produce respose based on user prompt and retrieved data
