# CineMood_v3 🎮🎭

**CineMood_v3** is a movie recommendation system that leverages embeddings and a vector database to suggest movies based on user preferences, trends, and semantic similarity.

---

## ✨ Overview
CineMood_v3 fetches trending movie data from public sources, generates vector embeddings for each movie, and stores those embeddings in a ChromaDB instance for fast similarity-based lookups. A Streamlit web application provides an interactive user interface to browse and discover movies based on various criteria.

---

## 🚀 Features
1. **Fetch latest movies** 🎮  
   Retrieves trending movies from online sources (e.g., TMDB API).

2. **Generate embeddings** 🧠  
   Uses NLP techniques (e.g., OpenAI embeddings) to create vector representations of movie overviews/descriptions.

3. **Store and search efficiently** 🔍  
   Utilizes [ChromaDB](https://docs.trychroma.com/) to manage and query embeddings at scale.

4. **Auto-update database** 🔄  
   Automated GitHub Actions keep the movie data and embeddings fresh.

5. **Streamlit-based Web App** 🌐  
   Offers a user-friendly interface to browse, search, and discover movie recommendations.

---

## 📚 Project Structure
```
CineMood_v3
├── .github/workflows/
│   └── update_db.yml         # GitHub Actions workflow for auto-updates
├── chroma_db/                # Directory where ChromaDB stores vectors
├── LICENSE                   # MIT License
├── README.md                 # This file
├── app.py                    # Main Streamlit application
├── config.py                 # Configuration settings (e.g., API keys)
├── fetch_movies.py           # Script to fetch trending movies from APIs
├── generate_embeddings.py    # Script to generate vector embeddings
├── movie_embeddings.json     # Generated embeddings in JSON format
├── requirements.txt          # Project dependencies
├── store_in_chromadb.py      # Script to store embeddings into ChromaDB
└── trending_movies.json      # Latest trending movies data
```

---

## 🛠 Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/thanhtungvudata/CineMood_v3.git
   cd CineMood_v3
   ```

2. **Create and activate a virtual environment** (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up API keys or configuration** (if required):
   - Open `config.py` (or `.env` if you're using dotenv) and add any necessary API keys (e.g., TMDB API key, OpenAI API key, etc.).

---

## 🏃 Usage

1. **Fetch the latest trending movies**:
   ```bash
   python fetch_movies.py
   ```
   - This will retrieve fresh movie data (e.g., from TMDB) and store it in `trending_movies.json`.

2. **Generate embeddings**:
   ```bash
   python generate_embeddings.py
   ```
   - This script reads from `trending_movies.json`, generates vector embeddings, and writes them to `movie_embeddings.json`.

3. **Store embeddings in ChromaDB**:
   ```bash
   python store_in_chromadb.py
   ```
   - This script populates the ChromaDB instance (in `chroma_db/`) with your newly generated embeddings.

4. **Run the Streamlit app**:
   ```bash
   streamlit run app.py
   ```
   - This will launch the CineMood_v3 web interface in your browser.  
   - Explore trending movies, search via semantic similarity, and find recommendations.

---

## 🤖 Automation
- A GitHub Actions workflow (`.github/workflows/update_db.yml`) is configured to:
  - Periodically run `fetch_movies.py` and `generate_embeddings.py`.
  - Commit any changes to `movie_embeddings.json` or `trending_movies.json`.
  - This ensures your movie database is always up to date without manual intervention.

---

## 🐟 License
This project is licensed under the **MIT License**.  
See [LICENSE](LICENSE) for full details.

---

## 💡 Future Enhancements
1. **User Feedback Integration**  
   Allow users to rate or save favorite movies, improving recommendations over time.
2. **Additional Metadata**  
   Integrate cast, crew, and genre data for more refined search and filtering.
3. **Model Fine-Tuning**  
   Experiment with different embedding models or fine-tune existing ones for higher recommendation accuracy.
4. **Deployment Options**  
   Deploy the app to platforms like Hugging Face Spaces, AWS, or Heroku for broader access.

---

## 🙌 Contributing
Pull requests are welcome! If you have ideas for improvements, open an issue to discuss what you’d like to change.

---

## ❤️ Acknowledgments
- [TMDB](https://www.themoviedb.org/) for movie data and trending API.
- [OpenAI](https://platform.openai.com/) or other NLP libraries for embedding generation.
- [ChromaDB](https://docs.trychroma.com/) for vector database services.
- [Streamlit](https://streamlit.io/) for the interactive UI framework.

---

### 🚀 Enjoy discovering and recommending movies with **CineMood_v3**!

