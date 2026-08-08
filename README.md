# Movie Recommendation Engine

This project is a Machine Learning-based Movie Recommendation Engine. By utilizing natural language processing and similarity metrics, the system suggests movies that are similar to a user's favorite choices. It can be implemented using Content-Based Filtering (analyzing genres, cast, and plot descriptions) or Collaborative Filtering (analyzing user ratings).

---

## Features

*   **Content-Based Filtering:** Recommends movies by calculating the cosine similarity between movie tags (overview, genres, cast, crew).
*   **Text Vectorization:** Uses CountVectorizer or TF-IDF to convert textual data into mathematical vectors.
*   **Web Application Interface:** Includes a front-end interface (e.g., built with Streamlit or Flask) allowing users to easily search for a movie and see recommended posters.
*   **Efficient Processing:** Uses optimized data structures like sparse matrices or pickled similarity arrays for fast recommendations.

---

## Dataset

This project is typically built using the **TMDB 5000 Movie Dataset** (available on Kaggle) or the **MovieLens Dataset**. 

*   **Movies Data:** Contains metadata for thousands of movies (id, title, overview, genres, keywords).
*   **Credits Data:** Contains the cast and crew information for the movies.

> **Note:** Due to size limits, the raw datasets and the generated similarity matrix (`similarity.pkl`) are ignored by Git. You must download the datasets and place them in the `data/` folder before running the scripts.

---

## Project Structure

```text
movie_recommendation_engine/
│
├── app/                    # Web application files (e.g., app.py for Streamlit/Flask)
├── data/                   # Raw datasets (tmdb_5000_movies.csv, etc.) - ignored in git
├── models/                 # Pickled files (movie_list.pkl, similarity.pkl) - ignored in git
├── notebooks/              # Jupyter notebooks for data preprocessing and exploration
├── src/                    # Source code for the recommendation logic
│   ├── preprocess.py       # Script to clean data and generate vectors
│   └── recommend.py        # Script containing the recommendation function
│
├── .gitignore              # Files and directories to be ignored by Git
├── requirements.txt        # Python dependencies (pandas, scikit-learn, streamlit, etc.)
└── README.md               # Project documentation
```

---

## Installation

**1. Clone the repository**
```bash
git clone https://github.com/yourusername/movie_recommendation_engine.git
cd movie_recommendation_engine
```

**2. Create a virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

---

## Usage

**1. Data Preprocessing & Model Generation**
First, ensure your raw dataset is in the `data/` folder. Run the preprocessing script to clean the data and generate the similarity matrix. This will create `.pkl` files in your `models/` directory.
```bash
python src/preprocess.py
```

**2. CLI Recommendation Testing**
You can test the recommendation engine directly from the command line. For example, to find titles similar to a specific movie or series like Death Note:
```bash
python src/recommend.py --movie "Death Note"
```

**3. Running the Web App**
To launch the interactive web interface, navigate to the app directory and start the server. If using Streamlit:
```bash
streamlit run app/app.py
```

---
INTERN ID-: CITS6361

*   Implement **Collaborative Filtering** to recommend movies based on user viewing history and ratings.
*   Integrate the **TMDB API** to dynamically fetch high-quality movie posters and details in the web app.
*   Add user authentication to allow individuals to save their favorite recommendations.
