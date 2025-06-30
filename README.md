# Semantic Book Recommender

A fast, flexible book recommendation system powered by modern embedding search and LLM-based classification & sentiment analysis. Users can issue a natural‑language query (e.g. “a story about forgiveness”), filter by genre, and rank by emotional tone—all via a clean Gradio dashboard.

## ⚙️ Features

- **Vector Search**  
  - Uses LangChain + Chroma to index book descriptions as high‑dimensional embeddings  
  - Retrieves the top _K_ semantically similar books to any free‑text query

- **Zero‑Shot Genre Classification**  
  - Leverages 🤗 Hugging Face’s `facebook/bart-large-mnli` for on‑the‑fly “Fiction” vs “Nonfiction” labels  
  - Provides a simple “genre” facet for filtering recommendations

- **Emotion‑Based Ranking**  
  - Applies a fine‑tuned Hugging Face emotion‑classification model (e.g. `distilbert-base-uncased-go-emotions-student`)  
  - Scores each description on emotions like Joy, Anger, Fear, Sadness, Surprise, etc.  
  - Allows sorting results by any selected tone

- **Interactive Gradio Dashboard**  
  - Intuitive web UI for query input, genre & tone selection, and image‑plus‑caption gallery  
  - Instant local deployment with `python gradio-dashboard.py`

## 🚀 Quick Start

1. **Clone the repo**  
   ```bash
   git clone https://github.com/your-username/SemanticBookRecommender.git
   cd SemanticBookRecommender
