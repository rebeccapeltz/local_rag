# Local RAG App (FAISS + LangChain + Docker Model Runner)

This project is a lightweight Retrieval-Augmented Generation (RAG) system 
that runs entirely locally using:

- FAISS for vector search
- LangChain v2 for chaining
- Docker Model Runner (DMR) for both embeddings and LLM inference
- Local HR policy documents as the knowledge base

The app loads a FAISS index, retrieves relevant chunks, and answers user questions 
using a local LLM.

## Requirements
- Python 3.11
- LangChain v2 packages:
- langchain-core
- langchain-community
- langchain-openai
- faiss-cpu
- Docker Model Runner with:
- ai/embeddinggemma
- ai/llama3.2 (or your chosen LLM)