# 🧠 Ollama + Postgres pgvector RAG Chatbot

![Workflow Diagram](./image.png)

This project implements a **Retrieval-Augmented Generation (RAG) chatbot** using:

- **Ollama** for embeddings + LLM responses
- **PostgreSQL with pgvector** for vector storage
- **Automated workflows** for embedding documents and answering chat queries

---

## 📌 Overview

### Workflow #1 — **Document Embedding & Storage**

This workflow handles:

1. Reading document files from disk  
2. Chunking and embedding content using an **Ollama embedding model**  
3. Storing vectors and documents inside **Postgres pgvector**  
4. Making data available for similarity search during chatbot queries  

This workflow is executed manually to refresh or add new knowledge.

---

### Workflow #2 — **Chat Retrieval & Response Generation**

Triggered when a new chat message arrives (Telegram, API, UI, etc.).

It performs:

1. Fetching relevant embeddings from the vector DB  
2. Passing the context into an Ollama chat model  
3. Using embedded memory to maintain conversation flow  
4. Executing JS-based business logic  
5. Returning the final message to the user

This allows the chatbot to answer with **real knowledge** extracted from your documents.

---

## 🧩 Components

### 🗂️ Document Loader  
Reads documents from disk for embedding.

### 🔡 Ollama Embeddings  
Generates vector encodings using an Ollama model such as `llama2`, `nomic-embed`, etc.

### 🗄️ PostgreSQL + pgvector  
Stores embeddings:  
- `embedding` (VECTOR)  
- `content` (TEXT)  
- `metadata` (JSONB)

### 🤖 AI Agent  
Core brain of the system:
- Retrieves context  
- Sends it to the LLM  
- Produces final answers  

### 🧪 JavaScript Logic  
Optional post-processing and formatting.

---

## ▶️ How To Use

### **1. Prepare environment**
- Install PostgreSQL  
- Install the `pgvector` extension  
- Install Ollama  
- Add your embedding model (e.g., `ollama pull nomic-embed-text`)  

### **2. Add documents**
Place files into the directory your loader expects.

### **3. Run Workflow #1**
This stores embeddings into Postgres.

### **4. Connect your chat platform**
Telegram / web UI / API request → triggers Workflow #2.

### **5. Chat**
Your bot now responds using the embedded company knowledge.

---

## 📦 Tech Stack

| Component | Purpose |
|----------|---------|
| **Ollama** | Embedding + Chat Model |
| **pgvector** | Vector similarity search |
| **PostgreSQL** | Long-term storage |
| **JavaScript Tool** | Business logic |
| **Workflow engine** | Automation & orchestration |

---

## 📑 License

MIT (or project-specific license).