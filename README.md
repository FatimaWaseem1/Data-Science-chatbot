# Data-Science-chatbot
Acknowledgement

This project was inspired by existing open-source(https://github.com/rachelhuddles/daisy-chatbot)
 implementations available on GitHub,
 which served as a learning reference during development. The codebase was significantly
 modified, refactored, and extended by adding custom document preprocessing, chunking logic
,FAISS-based vector search, and an improved Retrieval-Augmented Generation (RAG)
 workflow tailored for large PDF documents.
I am grateful to the open-source community for sharing knowledge and resources that
supported my learning and experimentation with applied AI systems.
AI-Powered PDF Chatbot (RAG-based)

An AI-powered chatbot that allows users to ask questions over multiple Data Science PDFs using
Retrieval-Augmented Generation (RAG)**.
The system retrieves relevant content from uploaded PDFs using vector similarity search
 (FAISS) and generates accurate answers using a Large Language Model (LLM).
 Features
 Load and process **multiple PDF documents**
-  Automatic **text chunking** for efficient retrieval
-Semantic search using **vector embeddings**
- Fast similarity search with **FAISS**
- Interactive **Streamlit chatbot UI**
- Secure API key handling using `.env`
-  Designed to be simple, readable, and student-friendly
System Architecture (RAG Pipeline)

1. **PDF Ingestion**
   - PDFs are read using `pypdf`
   - Text is extracted page-by-page

2. **Text Chunking**
   - Long text is split into overlapping chunks
   - Improves retrieval accuracy

3. **Embedding Generation**
   - Each chunk is converted into a numeric vector
   - Uses OpenAI embedding models (or alternatives)

4. **Vector Indexing**
   - Embeddings are stored in a FAISS index
   - Enables fast cosine similarity search

5. **Retrieval**
   - User query is embedded
   - Top-K most relevant chunks are retrieved

6. **Answer Generation**
   - Retrieved context is passed to the LLM
   - Final response is generated using both query + context

Project Structure
rag_new/
│
├── data/ # PDF documents (knowledge base)
│ └── *.pdf
│
├── index/ # Generated FAISS index
│ ├── faiss.index
│ └── meta.json
│
├── app.py # Streamlit chatbot app
├── build_index.py # PDF processing + FAISS index builder
├── requirements.txt # Project dependencies
├── .env # API keys (NOT pushed to GitHub)
└── README.md
OPENAI_API_KEY=your_api_key_here
EMBED_MODEL=text-embedding-3-small
CHUNK_SIZE=1200
CHUNK_OVERLAP=200


🎓 Academic Relevance

This project demonstrates:
Practical NLP pipeline design
Retrieval-Augmented Generation (RAG)
Vector databases for semantic search
Real-world use of LLM APIs
End-to-end AI application development
🔮 Future Improvements

Replace OpenAI with local embeddings (SentenceTransformers)
Add PDF upload via UI
Chat history memory
Source citation highlighting
Evaluation metrics (precision@k)




