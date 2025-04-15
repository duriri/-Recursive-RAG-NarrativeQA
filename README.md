# 🧩 Markdown Chunking with LangChain

This project implements **recursive text chunking** using `LangChain`’s `RecursiveCharacterTextSplitter`, tailored for **Markdown** and other structured documents. It focuses on breaking long documents into semantically meaningful pieces to improve downstream tasks such as embedding, retrieval, or language model processing.

---

## 📌 Project Overview

- **Objective**: Split long Markdown documents into smaller, coherent chunks using a hierarchy of separators (headers, code blocks, etc.).
- **Method**: Uses `RecursiveCharacterTextSplitter` from LangChain with a custom list of Markdown-specific separators.
- **Use Case**: Preprocessing for large language models (LLMs), retrieval-augmented generation (RAG), text summarization, and semantic search.

---

## 📂 Features

- ✅ Recursive character-based chunking with custom Markdown separators  
- ✅ Preserves context while avoiding hard character limits  
- ✅ Includes start index metadata for mapping back to original documents  
- ✅ Easy to extend or adapt for different document formats  

---

## 🧪 Example Markdown Separators Used

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

## 📊 **Use Cases**
✅Preprocessing documents for vector search and RAG

✅Enhancing semantic relevance in chunk-based LLM pipelines

✅Visualizing or evaluating chunking strategies

✅Preparing long-form content like articles, books, or scripts



🙋‍♀️ **Author**
Faeze Abdoli Nejad
👩‍💻 Master's in AI (NLP & LLMs)
📢 Telegram: @Ml_duriri – Simplifying AI for Everyone
