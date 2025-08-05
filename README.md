# 🧠 Multimodal RAG System: Text + Image QA using Cohere, ChromaDB & Gemini

This project builds a **Multimodal Retrieval-Augmented Generation (RAG)** system capable of answering questions from **PDFs containing both text and images** using state-of-the-art tools like:

- 🧠 **Cohere** – for embedding both text and image content  
- 💬 **Gemini (Google Generative AI)** – for question answering  
- 🗃️ **ChromaDB** – for vector storage and retrieval  
- 🔗 **LangChain** – for orchestration

---

## 📦 Dependencies

Install the required packages:

```bash
pip install cohere google-generativeai pillow tqdm PyMuPDF chromadb langchain langchain-google-genai
```

| Package                    | Purpose                                                  |
|---------------------------|----------------------------------------------------------|
| `cohere`                  | Text + image embeddings (via `embed-v4.0` API)           |
| `google-generativeai`     | Gemini SDK for LLM-based reasoning                       |
| `pillow`                  | Image resizing and processing                            |
| `tqdm`                    | Progress bar support                                     |
| `PyMuPDF (fitz)`          | PDF text/image parsing                                   |
| `chromadb`                | Vector DB for retrieval                                  |
| `langchain`               | LLM chains, templates, parsers                           |
| `langchain-google-genai`  | Gemini integration via LangChain                         |

---

## 📚 How It Works

1. **PDF Upload**: 
   - Extracts both text and images from the PDF using `PyMuPDF`.

2. **Embedding**:
   - Uses **Cohere's embed-v4.0** to generate vector representations of:
     - Page-wise text
     - Extracted images

3. **Vector Storage**:
   - Saves these embeddings into **ChromaDB** (local vector database).

4. **Question Answering**:
   - Given a user query, retrieves relevant image/text chunks.
   - Uses **Gemini** (via LangChain) to generate answers.

---

## 🚀 Usage Flow

```python
# 1. Extract text & images from PDF
# 2. Get embeddings from Cohere
# 3. Store them in ChromaDB
# 4. Run a QA chain using Gemini LLM
```

---

## 📁 File Structure

```
.
├── Multi_modal_rag_system.ipynb   # Main notebook (step-by-step logic)
├── data/                          # Folder for PDFs and extracted images
└── README.md                      # Project documentation (this file)
```

---

## 🔐 API Keys Required

Make sure to set the following environment variables or configure your notebook securely:

- `COHERE_API_KEY`
- `GOOGLE_API_KEY` (for Gemini)

---

## 📌 Notes

- Designed to work with **PDFs containing images** (e.g., slides, diagrams, manuals).
- **All processing is done locally**, except for the LLM/API calls.

---

## 📤 Future Improvements

- Add support for audio/video extraction
- Switch to other vector DBs (e.g., Pinecone)
- Enhance multimodal reasoning with hybrid search
