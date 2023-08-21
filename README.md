# **Movie Recommender System Readme**  
This code provides a simple movie recommender system using collaborative filtering and popularity-based recommendations. The system uses a user-item matrix and a k-nearest neighbors (KNN) algorithm to find similar movies for existing users and recommends popular movies for new users. Below is a breakdown of the key components and functions in the code:  

## **Libraries Used**  
numpy: A library for numerical computations in Python.  
pandas: A library for data manipulation and analysis.  
scipy.sparse: A module for sparse matrix operations.  
sklearn.neighbors: Part of the scikit-learn library used for K-nearest neighbors implementation.  

##  **Data Loading**  
The code loads movie and rating data from URLs using pandas. The movie data contains information about movies, while the rating data contains user ratings for movies.  

## **User-Item Matrix Creation**
The function create_matrix(df) constructs a user-item matrix in sparse format. This matrix represents user ratings for movies. It maps user and movie IDs to corresponding indices and constructs the matrix using the csr_matrix class from the scipy.sparse module.  

## **Finding Similar Movies using KNN**  
The function find_similar_movies(movie_id, X, k, metric='cosine', show_distance=False) takes a movie ID and finds similar movies using KNN. It calculates similarity based on a specified metric (default: cosine similarity) and returns a list of similar movie IDs.  

## **Popularity-Based Recommendations for New Users**
The function recommend_popular_movies(n_recommendations) recommends popular movies for new users. It groups movies by their ID, calculates their average rating, and filters out less popular movies. Then, it sorts movies by mean rating and returns a list of recommended movie IDs.  

## **Recommendations for Users (Both Old and New)**  
The function recommend_movies_for_user(user_id, n_recommendations) recommends movies for a user, whether existing or new. If the user is existing, it uses collaborative filtering to find similar movies. If the user is new, it uses the popularity-based recommendations.  

## **Testing Recommendation Functions**  
The code tests the recommendation functions for both an existing user and a new user. It demonstrates how to get recommendations for both cases and prints out the recommended movie titles.  

## **Movie Titles Dictionary**  
The code creates a dictionary movie_titles that maps movie IDs to their corresponding titles.  

## **Usage**  
Load the movie and rating data using the provided URLs.  
Create the user-item matrix using the create_matrix function.  
Utilize the recommend_movies_for_user function to get movie recommendations for both existing and new users.  

## **Note**  
The provided URLs for data loading may need to be updated if the data sources change.  
Ensure that required libraries (numpy, pandas, scipy, sklearn) are installed.  
