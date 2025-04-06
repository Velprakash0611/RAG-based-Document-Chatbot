# 📚 RAG based Document Chatbot

A simple yet powerful **Retrieval-Augmented Generation (RAG)** application that allows users to upload PDF documents, process them into embeddings using `nomic-embed-text`, and perform intelligent question-answering using a locally hosted LLM via `Ollama`.

---

## 🚀 Project Overview

This project combines the strengths of **Streamlit** for UI, **Ollama** for local LLM inference, and **ChromaDB** for efficient embedding-based retrieval. It allows you to:

- Upload one or more PDF files
- Automatically chunk and embed the content
- Store embeddings in ChromaDB
- Ask questions about your documents
- Get context-aware responses using a local LLM

All processing happens locally – no internet or cloud APIs required.

---

## 🧠 Tech Stack

| Component   | Purpose                                        |
|-------------|------------------------------------------------|
| Streamlit   | UI and interactivity                           |
| Ollama      | Local large language model inference           |
| ChromaDB    | Vector database for storing/retrieving chunks  |
| nomic-embed-text | Embedding model for semantic search       |
| PyMuPDF     | PDF parsing and text extraction                |
| LangChain   | RAG pipeline and vector store abstraction      |


---

## 🔧 Processing Pipeline

1. **PDF Upload**  
   Users upload one or more PDF documents via the Streamlit interface.

2. **Text Extraction & Chunking**  
   The text is extracted using `PyMuPDF` and split into manageable chunks.

3. **Embedding with nomic-embed-text**  
   Each chunk is embedded using the `nomic-embed-text` model (run locally).

4. **Storage in ChromaDB**  
   The embeddings and original chunks are stored in ChromaDB for fast similarity retrieval.

5. **Querying**  
   When the user submits a query:
   - The query is embedded using the same model.
   - Relevant chunks are retrieved from ChromaDB using similarity search.
   - These chunks are passed as context to a locally running LLM via Ollama.

6. **Answer Generation**  
   The LLM responds with a contextualized answer, shown in the Streamlit UI.

---

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Install Dependencies

Ensure Python 3.10+ is installed.

```bash
pip install -r requirements.txt
```

You will also need to install [Ollama](https://ollama.com/) if not already installed.

### 3. Pull Required Models

- **Ollama LLM (e.g., Mistral or LLaMa3):**

```bash
ollama pull llama3
```

- **nomic-embed-text:**

```bash
ollama pull nomic-embed-text
```

### 4. Run the App Locally

```bash
streamlit run app.py
```

---

## 💡 Applications

This architecture can be used for:

- Legal document summarization and querying
- Academic research tools
- Customer support chatbots over manuals
- Personal knowledge base assistant
- Corporate internal document Q&A

---

## 📂 Project Structure

```
.
├── app.py                # Main Streamlit app
├── requirements.txt      # Python dependencies
├── README.md             # You're reading it!

```

---

## 📌 Notes

- All components run **entirely locally** – great for privacy and offline use.
- You can replace the LLM in `Ollama` or the embedding model as needed.
- For large documents, consider batching or optimizing chunk size and overlap.

---

## 👤 Author

Built with ❤️ by Velprakash

---

## 📜 License

This project is licensed under the MIT License.
```

---

Let me know if you want to include badges, add environment variables, or customize any part further.
