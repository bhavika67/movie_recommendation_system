# Movie Recommendation System

## Project Overview
This project builds a recommendation system using the **MovieLens 20M dataset**, which contains 20 million movie ratings from over 138,000 users on 27,000 movies. A **hybrid recommendation approach** is implemented by combining **Collaborative Filtering** and **PageRank** to provide personalized movie recommendations.

**Link to the dataset:** [MovieLens 20M Dataset](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset)

## Techniques Used

### Collaborative Filtering (CF)
Collaborative Filtering relies on past behaviors and preferences of users to make recommendations. It includes:
- **User-based Collaborative Filtering**: Recommending items based on user similarity.
- **Item-based Collaborative Filtering**: Recommending items based on item similarity.

### PageRank
PageRank, traditionally used for ranking webpages, is adapted to rank movies and users based on their interactions in the movie rating network. It calculates the "importance" of movies and users to enhance recommendations.

By combining **Collaborative Filtering** and **PageRank**, this system leverages user-item similarities and network structure insights for better recommendations.

---

## Dataset
The **MovieLens 20M dataset** contains the following files:

- **movies.csv**: Movie data (movieId, title, genre)
- **ratings.csv**: User ratings for movies (userId, movieId, rating, timestamp)
- **tags.csv**: User-generated tags (userId, movieId, tag, timestamp)
- **links.csv**: External database links (movieId, IMDbId, tmdbId)

For this project, the **ratings.csv** file is the primary focus, containing user-item interactions (ratings by users).

---

## Approach

### 1. Data Preprocessing
- Load and clean the **ratings.csv** file.
- Create a **user-item interaction matrix**, where rows represent users, columns represent movies, and values represent ratings.

### 2. Similarity Calculation using Collaborative Filtering
- Compute **Cosine Similarity** between movies.
- Recommend movies based on similarity to movies highly rated by users.

### 3. PageRank Calculation on the User-Item Graph
- Construct a **bipartite graph** with users and movies as nodes, and ratings as edges.
- Apply **PageRank** to calculate the importance of movies (and users).
- Prioritize popular and relevant movies in recommendations.

### 4. Hybrid Model
- Combine recommendations from **Collaborative Filtering** and **PageRank**.
- Rank recommendations using a **weighted combination** of similarity scores and importance scores.

### 5. Evaluation
- Evaluate the model using **Root Mean Squared Error (RMSE)** to assess the recommendation quality.

---

## Key Features
- **Collaborative Filtering** identifies similar movies based on user ratings.
- **PageRank** ranks movies based on their importance in the interaction network.
- Hybrid approach integrates **content-based** and **graph-based** insights.

---

## Future Improvements
- **Tune Weighting**: Optimize weights for cosine similarity and PageRank scores.
- **Additional Features**: Incorporate movie genres and time-based patterns.
- **Advanced Models**: Explore Matrix Factorization or Deep Learning-based approaches.

---

## Dependencies
- Python (3.x)
- Libraries: Pandas, NumPy, NetworkX, Scikit-learn, Matplotlib

---

## Usage
1. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset).
2. Install required libraries:
   ```bash
   pip install pandas numpy networkx scikit-learn matplotlib
   ```
3. Run the notebook or script containing the recommendation system implementation.

---

## Conclusion
This project demonstrates the effectiveness of a **hybrid recommendation system** that combines **Collaborative Filtering** and **PageRank** to provide personalized and high-quality movie recommendations. By leveraging user-item interactions and graph-based rankings, the system delivers more accurate and relevant suggestions for users.

