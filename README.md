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

## Docker Model Runner
Two models are used one as the primary LLM and one to hold embeddings.

- ai/llama3.2
- ai/embeddinggemma

## Data Flow

1. Raw data (.pdf's) are located in ./data/raw
2. Processed data (.md) is generated using ./scripts/convert.py
3. Data is loaded into embeddings using scripts/ingest.py which creates ./faiss_index
4. Prompt is created and serviced in ./app.py