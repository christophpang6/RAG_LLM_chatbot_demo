# Multi-Turn RAG Chatbot

A **Retrieval-Augmented Generation (RAG)** chatbot (conversational AI) that answers questions based on a curated set of documents. Combines **FAISS semantic search**, **SentenceTransformer embeddings**, and **OpenAI GPT-4** to provide context-aware responses for multi-turn conversations.

![Multi-Turn RAG Demo](multi-turn_RAG_demo.png)


---

## Features

- **RAG Retrieval System**  
  - Semantic search over a custom corpus using **FAISS**.  
  - Retrieves top-k relevant document chunks for any user query.  
  - Considers last 3 conversation turns for multi-turn context.

- **Context-Aware Chat with GPT-4**  
  - Generates answers strictly based on retrieved content.  
  - Responds “I don’t know” if the context lacks an answer.  

- **Custom Embeddings**  
  - Uses **SentenceTransformer (`all-MiniLM-L6-v2`)** for high-quality text embeddings.  
  - Supports diverse topics: space missions, programming, science, history, architecture.  

- **Interactive Gradio Interface**  
  - User-friendly chat interface with adjustable chatbox height.  
  - Preloaded example queries for quick testing.  
  - Supports sharing via Gradio links.  

- **Extensible & Modular**  
  - Easy to add new documents to the knowledge base.  
  - Retrieval, embedding, and chat components are modular.  

- **Debugging & Transparency**  
  - Optional verbose mode shows retrieved chunks and L2 distance scores. See example_chat_debugging_retrieval.txt for an example

---

## Tech Stack

- Python  
- **OpenAI API (GPT-4)**  
- **Gradio** for interactive UI  
- **FAISS** for fast similarity search  
- **Hugging Face SentenceTransformers** for embeddings  

---

## Quick Start

1. Clone the repository:

```bash
git clone <your-repo-url>
cd <repo-folder>
```

2. Ensure dependencies are installed:

```python
!pip install -q sentence-transformers faiss-cpu torch datasets evaluate rouge-score openai gradio
```
3. Set your OpenAI API key:

```python
import os
os.environ["OPENAI_API_KEY"] = "your-api-key-here"
```

## Extending the Knowledge Base

1. Add new documents to the `enhanced_sample_texts` dictionary.  
2. Each document should have a title and content.  
3. The system will automatically embed and index the new content on startup.  


## Skills Demonstrated

- Multi-turn conversation management  
- RAG architecture design to reduce hallucinations (will return "I don't know" instead)
- Embedding-based semantic search  
- Building interactive applications with Gradio  
- Integration of OpenAI GPT-4 API  
- Modular and extensible Python code  
