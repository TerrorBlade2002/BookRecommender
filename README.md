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

## 🚀 Install Dependencies

```bash
pip install -r requirements.txt

## Project Structure
🗂 Project Structure
bash
Copy
.
├── books_with_emotions.csv     # Book metadata, thumbnails, and precomputed emotion scores
├── tagged_description.txt      # Raw descriptions tagged with ISBN prefixes
├── gradio-dashboard.py         # Main app: embeddings, classification, sentiment, Gradio UI
├── vector-search.ipynb         # How vector DB is built with Chroma & OpenAIEmbeddings
├── text-classification.ipynb   # Zero‑shot genre labeling with Hugging Face
├── sentiment-analysis.ipynb     # Sentence‑level emotion scoring pipeline
├── data-exploration.ipynb       # Exploratory analysis & cleaning steps
├── requirements.txt            # All Python package dependencies
└── .env.example                # Template for your environment variables

🔧 Dependencies
Python 3.11+

pandas, numpy — data manipulation

langchain-community, langchain-chroma, langchain-openai — embedding & vector DB

transformers — zero-shot classification & emotion analysis

gradio — interactive UI

python-dotenv — load API keys

notebook, ipywidgets, matplotlib, seaborn — development notebooks

📈 Future Plans
Full‑Stack Web UI
Migrate from Gradio to a React‑Next.js frontend with Tailwind for production

User Accounts & Feedback
Allow users to save favorites, rate recommendations, and refine the ranking models

Expanded Facets
Add filters for length, publication date, reading level, and community tags

Deployment & Scaling
Dockerize the API & Web UI, deploy on AWS/GCP with autoscaling vector DB
