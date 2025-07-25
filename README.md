Web Search Engine

A lightweight yet powerful web search engine combining **BM25** (for keyword relevance), **BERT embeddings** (for semantic similarity), and **PageRank** (for link importance). This hybrid approach delivers smarter, more context-aware search results.

## Requirements

To run this project locally, make sure you have:

- Python 3.8+
- `Flask` – for the web server
- `sentence-transformers` – for BERT-based text embeddings
- `rank-bm25` – for BM25 keyword ranking
- `spaCy` with `en_core_web_sm` – for text preprocessing
- `beautifulsoup4` – for HTML cleaning
- `tqdm`, `pickle`, `numpy`, `scikit-learn`

You can install the dependencies with:

bash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
`

---

## Goal

Build a simple, flexible, and intelligent search engine that can:

* Understand query meaning (not just keywords)
* Rank documents based on both relevance and importance
* Be fast and scalable using precomputed indexes

---

## To Get Started

### 1. Prepare your data

* Add your web pages to `url_content.txt` in this format:

  
  @@URL@@ https://example.com
  @@TITLE@@ Example Title
  @@CONTENT@@ Actual page content...
  @@END@@
  

* Prepare your site graph (links between URLs) in `url_graph.json`:

  json
  {
    "https://example.com": ["https://example.com/about", "https://example.com/contact"],
    ...
  }
  

### 2. Run precomputation

bash
python precompute.py


This will generate:

* `bm25_index.pkl` – BM25 keyword index
* `embeddings.pkl` – BERT vector embeddings
* `pagerank.pkl` – PageRank values
* `content.pkl` – cleaned titles and snippets


## Challenges Faced

* Merging results from keyword and semantic engines without bias
* Normalizing and cleaning inconsistent or short content
* Maintaining fast response time even with large datasets


## Features

* 🔍 **BM25 Ranking**: Scores based on keyword overlap and frequency
* 🧠 **Semantic Matching**: Finds meaningfully related results using BERT
* 🔗 **PageRank**: Highlights important or well-connected pages
* ⚡ **Precomputed Indexing**: Faster querying with saved models
* 🔧 **Robust Preprocessing**: Removes HTML noise and applies lemmatization
* 💡 **Simple Flask UI**: Minimal interface with title/snippet display


---

## 🧠 Tech Stack

* **NLP**: SpaCy, BERT (MiniLM)
* **IR**: BM25 (Okapi), Sentence Embeddings
* **Graph Theory**: PageRank Algorithm
* **Web**: Flask + HTML (Jinja templates)

* Contribution 
Pull requests and feature suggestions are welcome!
Feel free to fork, test, and enhance this project.

