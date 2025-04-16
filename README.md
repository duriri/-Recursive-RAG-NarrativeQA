# 🧩 Markdown Chunking with LangChain

This project implements **recursive text chunking** using [LangChain](https://github.com/langchain-ai/langchain)’s `RecursiveCharacterTextSplitter`, tailored for **Markdown** and other structured documents. It focuses on breaking long texts into semantically meaningful pieces to improve downstream tasks such as embedding, retrieval, or large language model (LLM) processing.

---

## 📌 Project Overview

- **Objective**: Split long Markdown documents into smaller, coherent chunks using a hierarchy of separators (e.g., headers, code blocks).
- **Method**: Utilizes `RecursiveCharacterTextSplitter` from LangChain with a custom list of Markdown-specific separators.
- **Target Use Cases**: Preprocessing for large language models (LLMs), retrieval-augmented generation (RAG), semantic search, summarization, and content alignment.

---

## 🚀 Installation & Usage

### 🧰 Requirements

- Python 3.8+
- langchain
- tiktoken (for token counting, optional)
- numpy, tqdm, or other standard libraries (if extended)

```bash
pip install langchain
```

### 🏃‍♀️ Quick Start

```python
from langchain.text_splitter import RecursiveCharacterTextSplitter

MARKDOWN_SEPARATORS = [
    "\n#{1,6} ",
    "```\n",
    "\n\\*\\*\\*+\n",
    "\n---+\n",
    "\n___+\n",
    "\n\n",
    "\n",
    " ",
    "",
]

splitter = RecursiveCharacterTextSplitter(
    separators=MARKDOWN_SEPARATORS,
    chunk_size=500,
    chunk_overlap=50,
    length_function=len,
    add_start_index=True,
)

chunks = splitter.create_documents([markdown_text])
```

---

## 📂 Features

- ✅ Recursive, hierarchical chunking with Markdown-aware separators  
- ✅ Preserves semantic coherence instead of naive character splits  
- ✅ Adds metadata like `start_index` for traceability  
- ✅ Easy to adapt for other structured formats (HTML, LaTeX, etc.)  
- ✅ Modular and extendable for other LLM workflows

---

## 📊 Use Cases

- 🔍 Preprocessing documents for vector search and RAG pipelines  
- 🧠 Enhancing semantic relevance in chunk-based LLM tasks  
- 🧪 Evaluating chunking strategies for custom datasets  
- 📚 Preparing long-form content (articles, books, scripts)  
- 📈 Improving embedding quality and context retention in LLMs  

---

## 🧪 Example Markdown Separators

```python
MARKDOWN_SEPARATORS = [
    "\n#{1,6} ",
    "```\n",
    "\n\\*\\*\\*+\n",
    "\n---+\n",
    "\n___+\n",
    "\n\n",
    "\n",
    " ",
    "",
]
```

---

## 🙋‍♀️ Author

**Faeze Abdoli Nejad**  
🎓 M.Sc. in AI (specialized in NLP & LLMs)  
📢 [Telegram: @Ml_duriri](https://t.me/Ml_duriri) – *Simplifying AI for Everyone*

---

## 📄 License

MIT License – free to use, share, and modify with attribution.

---

## 🧠 Contribution

Feel free to open issues or submit pull requests if you'd like to improve the chunking logic, add more formats, or integrate with downstream tools like FAISS, Weaviate, or Haystack.
