# 📄 Novel Office Document RAG System

## NOTE: Kindly add GROQ(name: GROQ_API_KEY) and IMGBB API KEY(name: IMGBB_API_KEY) in the secrets section

Video link: https://drive.google.com/drive/folders/1KrQSYboEEUBL54aVt9vl7tqq4shBOpNU?usp=drive_link

This project is a **Document Question Answering System** built using **LangChain**, **ChromaDB**, **PDF/Markdown loaders**, and **HuggingFace embeddings**. It allows users to **upload documents (PDFs or Markdown)**, extract their contents, create vector embeddings, and **ask questions** interactively using a chatbot interface powered by **Gradio**.

---

## 💡 Tip: If you want to test using your own document, you can provide the Google Drive link with public access to the file in the Document Download section.


## 🚀 Features

- 📥 Upload and process PDF/Markdown documents.
- 🧠 Chunk and embed documents using HuggingFace models.
- 🔍 Store and retrieve embeddings using **ChromaDB**.
- 💬 Interact with the content via a **Gradio chatbot**.
- 🧾 Extract text using `pdfplumber` and `PyMuPDF`.
- 🔄 Clean and transform text for optimized question answering.

---

## 🛠️ Dependencies Installation

Dependencies:

```bash
pip install langchain langchain-community langchain-huggingface langchain-core chromadb pdfplumber pymupdf langchain_chroma gradio
```

---

## 📂 Folder Structure

```plaintext
.
├── Novel_Office_Assign.ipynb                               
├── data/                               # Folder for storing processed documents
└── chroma/                             # Folder for vector DB persistence
```

---

## 📘 How It Works

1. **Upload Document**  
   Users upload a PDF or Markdown file using the Gradio interface.

2. **Text Extraction**  
   - `pdfplumber` and `PyMuPDF` extract raw text from PDF.
   - Markdown files are read using `UnstructuredMarkdownLoader`.

3. **Text Splitting**  
   The document is split into overlapping chunks using `RecursiveCharacterTextSplitter` to preserve context.

4. **Embedding**  
   Each chunk is embedded using HuggingFace models via `HuggingFaceEmbeddings`.

5. **Vector Store**  
   Embeddings are stored in a **ChromaDB** database with persistent storage.

6. **QA Chatbot**  
   A Gradio interface allows users to ask questions. Relevant document chunks are retrieved and used to answer queries.

---

## 🧪 Example Use Case

Upload a document like `policy.pdf`, and ask:
> "What is the refund policy at Novel Office?"

The system will return the answer after fetching relevant sections.

---

## 🧠 Built With

- [LangChain](https://www.langchain.com/)
- [ChromaDB](https://www.trychroma.com/)
- [Gradio](https://www.gradio.app/)
- [HuggingFace Transformers](https://huggingface.co/)
- `pdfplumber`, `PyMuPDF`, `dotenv`

---

## 🙌 Acknowledgments

Developed as part of Novel Office’s document processing automation initiative.
