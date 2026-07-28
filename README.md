# 🛒 Grocery Vector Similarity Search

> **Find the closest grocery items in your database using vector similarity search with ChromaDB & Gradio.**

[![Python](https://img.shields.io/badge/Python-3.11+-blue?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Gradio](https://img.shields.io/badge/Gradio-4.44.0-orange?style=for-the-badge&logo=gradio&logoColor=white)](https://gradio.app)
[![ChromaDB](https://img.shields.io/badge/ChromaDB-0.4.24-yellow?style=for-the-badge)](https://www.trychroma.com/)
[![SentenceTransformers](https://img.shields.io/badge/SentenceTransformers-all--MiniLM--L6--v2-green?style=for-the-badge)](https://www.sbert.net/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

---

## 📌 Overview

**Ever wanted to search for grocery items not by exact keywords, but by meaning?**

This project demonstrates **vector similarity search** using **ChromaDB** and **Sentence Transformers**. Instead of traditional keyword matching, the system converts text into **vector embeddings** and finds the most semantically similar items in the database.

**Real-world analogy:** You search for *"sweet red fruit"* → the system finds *"fresh red apples"* and *"golden apple"* because their embeddings are close in vector space — even though the exact keywords don't match.

---

## 🎯 Features

| Feature | Description |
|---------|-------------|
| 🧠 **Semantic Search** | Uses `all-MiniLM-L6-v2` embeddings to capture meaning, not just keywords |
| 🗄️ **Vector Database** | ChromaDB stores and indexes embeddings for fast similarity search |
| 🖥️ **Interactive UI** | Gradio dashboard with live search, configurable Top-K results |
| 📊 **Distance Scores** | Displays cosine distance scores for each result (lower = more similar) |
| ⚡ **Lightweight** | Runs locally with minimal setup — no cloud dependencies |

---

## 🧠 How It Works

### The Pipeline

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    1. Data Ingestion                                   │
│   Grocery items → Convert to embeddings using Sentence Transformers    │
└────────────────────────────────┬────────────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                    2. Vector Storage                                   │
│   Embeddings stored in ChromaDB with cosine similarity space           │
└────────────────────────────────┬────────────────────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                    3. Query & Retrieval                                │
│   User query → embedded → cosine similarity search → Top-K results    │
└─────────────────────────────────────────────────────────────────────────┘
                                 ▼
                     🛒 Similar Grocery Items Found!
```

### Example Query
- **User Input:** `"sweet red fruit"`
- **Results:**
  1. `"fresh red apples"` — cosine distance: `0.23`
  2. `"golden apple"` — cosine distance: `0.41`
  3. `"red fruit"` — cosine distance: `0.52`

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| **Vector Database** | ChromaDB |
| **Embeddings** | Sentence Transformers (`all-MiniLM-L6-v2`) |
| **Frontend** | Gradio |
| **Language** | Python 3.11+ |
| **Similarity Metric** | Cosine Distance |

---

## 📦 Installation

### Prerequisites

- Python 3.11 or higher

### Step 1: Clone the Repository

```bash
git clone https://github.com/umer302203/grocery-similarity-search.git
cd grocery-similarity-search
```

### Step 2: Create Virtual Environment

```bash
python3.11 -m venv venv
source venv/bin/activate   # Linux/Mac
# venv\Scripts\activate    # Windows
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Run the Application

```bash
python similarity_search.py
```

Open your browser at `http://127.0.0.1:7860` (or the URL shown in terminal).

---

## 🖥️ Usage Guide

1. **Enter a search query** — e.g., *"breakfast food"*, *"meat products"*, *"sweet fruits"*
2. **Select Top-K** — choose how many results to display (1-5)
3. **Click "Search Database"**
4. View results with:
   - Document ID
   - Item description
   - Cosine distance score (lower = more similar)

---

## 📁 Project Structure

```
grocery-similarity-search/
│
├── similarity_search.py      # Main application
├── requirements.txt          # Dependencies
├── README.md                 # Documentation
└── LICENSE                   # MIT License
```

---

## 📋 Requirements (`requirements.txt`)

```
chromadb==0.4.24
gradio==4.44.0
sentence-transformers==2.2.2
```

---

## 🚀 Deployment (Hugging Face Spaces)

1. Go to [huggingface.co/spaces](https://huggingface.co/spaces)
2. Click **"Create new Space"**
3. Select **"Gradio"** as the SDK
4. Upload `similarity_search.py` and `requirements.txt`
5. The Space will auto-build and deploy

---

## 🎬 Demo Video (Coming Soon)

> *Watch the similarity search in action — type a query and see results instantly.*

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing`)
5. Open a Pull Request

---

## 📄 License

This project is distributed under the **MIT License** — free to use, modify, and distribute.

---

## 🙏 Acknowledgments

- **ChromaDB** for the lightweight vector database
- **Sentence Transformers** for `all-MiniLM-L6-v2`
- **Gradio** for the UI framework
- **OpenAI** for embedding function inspiration

---

## 📬 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rana-umer-05a9a9359/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/umer302203)
[![Hugging Face](https://img.shields.io/badge/HuggingFace-FF9D00?style=for-the-badge&logo=huggingface&logoColor=white)](https://huggingface.co/Umer78786)

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=120&section=footer&text=Grocery%20Similarity%20Search&fontSize=24&fontColor=white&fontAlignY=65" />
</p>

> Built with ❤️ by [Umer](https://www.linkedin.com/in/rana-umer-05a9a9359/) 🚀
