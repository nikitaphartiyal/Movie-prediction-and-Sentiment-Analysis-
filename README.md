Movie Recommendation System (TMDB 5000 Dataset)

This project builds a Movie Recommendation System using the TMDB 5000 Movies & Credits dataset. The notebook walks through data loading, cleaning, preprocessing, feature extraction, and building a content-based movie recommendation model.

📌 1. Dataset Description

The project uses the following datasets:

tmdb_5000_movies.csv

tmdb_5000_credits.csv

The movies dataset contains 4803 rows and 20 columns, including:

Title

Genres

Overview

Keywords

Cast & Crew

Popularity

Budget

Revenue

Release Date

etc.

📌 2. Data Preprocessing & Cleaning

Key steps performed:

Removed unnecessary columns (homepage, etc.)

Handled missing values

Converted JSON-like string columns (e.g., genres, keywords, production_companies) into lists using ast.literal_eval

Converted release_date to datetime

Merged movies and credits datasets using the movie_id column

Extracted important fields:

Top 3 cast members

Director

Keywords

Genres

Each textual field was cleaned by:

Removing spaces

Joining list elements into a single text blob

A new combined text column (tags) was created for vectorization.

📌 3. Feature Engineering

To compute movie similarities:

Applied CountVectorizer to convert text tags into feature vectors.

Used Porter Stemmer for stemming to reduce word variations.

Created a similarity matrix using cosine similarity.

📌 4. Recommendation System

A function was built to recommend similar movies based on title input:

def recommend_movie(movie_title):
    # returns top 5 similar movies


The system works by:

Locating the movie index

Fetching similarity scores

Sorting and returning top recommendations

Example:

Input: Avatar

Output: Movies with similar genres, keywords, cast, and story styling.

📌 5. Exporting Model Files

The project saves:

movie_dict.pkl → dictionary of movie metadata

similarity.pkl → cosine similarity matrix

These can be used in a web app (Streamlit/Flask) later.

📌 6. Libraries Used

numpy

pandas

seaborn

ast

nltk

sklearn (CountVectorizer, cosine similarity)

pickle

🎯 Final Outcome

✔ Fully functional content-based movie recommendation system
✔ Preprocessed and cleaned TMDB dataset
✔ Feature extraction using NLP techniques
✔ Cosine similarity for movie matching
✔ Exported model files for deployment
