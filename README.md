
---

# 🎬 Movie Recommendation System

This project implements a movie recommendation system using **unsupervised learning (K-Means Clustering)** in a **Jupyter Notebook** environment. It clusters movies based on genres, ratings, and popularity, and then recommends similar movies within the same cluster.

---

## 📂 Project Structure

* `movies_metadata.csv` - Contains movie metadata including title, genres, rating, etc.
* `movie_recommendation.ipynb` - Jupyter Notebook implementing the entire pipeline from data cleaning to recommendation.

---

## 🛠️ Installation

Install the required Python libraries using:

```bash
pip install pandas numpy scikit-learn seaborn matplotlib
```

---

## 📥 Data Loading & Preprocessing

* Load `movies_metadata.csv`
* Extract relevant features:

  * `title`, `genres`, `overview`, `poster_path`, `release_date`, `vote_average`, `popularity`
* Drop rows with missing essential data
* Construct full poster image URLs using TMDB's base URL (`https://image.tmdb.org/t/p/w500`)

---

## 🧠 Feature Engineering

* **Genre Parsing**: Convert genre strings into Python lists of genre names
* **One-Hot Encoding**: Encode genres with `MultiLabelBinarizer`
* **Normalization**: Scale `vote_average` and `popularity` with `MinMaxScaler`
* **Final Features**: Concatenate genre and numeric features into one DataFrame for clustering

---

## 📊 Clustering

* Apply **KMeans** clustering (k = 2 to 20) to find optimal clusters
* Evaluate using:

  * **Inertia (Elbow Method)**
  * **Silhouette Score**
* Visualize both to choose the best number of clusters

---

## 🧼 Cluster Analysis

* Apply final KMeans model (default: `k=10`)
* Assign each movie to a cluster
* Visualize movie count per cluster to assess distribution

---

## 📈 Genre Distribution

* Explode the genre lists and count each genre’s frequency
* Visualize as a bar chart using Seaborn

---

## 🤖 Movie Recommendation Function

A simple content-based recommendation using clustering:

### Testing:

```python
recommend_movies("Iron Man", n=5)
```

Returns:

* Title
* Overview
* Release Date
* Vote Average
* Popularity
* Poster Image URL

Example output:

```
🎬 Say Nothing (2001-08-01)
⭐ Rating: 9.0 | 🔥 Popularity: 0.22
📝 Housewife Grace Needham has a one-night stand...
🖼️ Poster: https://image.tmdb.org/t/p/w500/e5zFhKKniiiep8oM7Y3g6gLygHS.jpg
```

---

## 📌 Notes

* All code is contained in a single Jupyter Notebook.
* Ensure that `movies_metadata.csv` is in the same directory.
* Ideal for content-based recommendation systems where genre similarity is key.

---

## 📷 Screenshots (Optional)

Include charts like:

* Elbow Plot
* Silhouette Score Plot
* Cluster Distribution
* Genre Frequency Plot

---

## 📜 License

MIT License — free to use and modify with credit.

---
