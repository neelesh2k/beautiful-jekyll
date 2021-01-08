---
layout: post
title: Movie Recommender based on User Rating
cover-img: /assets/img/movie-recommendation.jpg
thumbnail-img: /assets/img/movie-recommendation.jpg
---

### Overview :
Recommender systems are widely used in product recommendations such as recommendations of music, movies, books, news, research articles, restaurants, etc.
There are two popular methods for building recommender systems: Collaborative filtering Content-based filtering

**Collaborative filtering** : The collaborative filtering method predicts (filters) the interests of a user on a product by collecting preferences information from many other users (collaborating). The assumption behind the collaborative filtering method is that if a person P1 has the same opinion as another person P2 on an issue, P1 is more likely to share P2’s opinion on a different issue than that of a randomly chosen person.

**Content-based filtering method** : Content-based filtering method utilizes product features/attributes to recommend other products similar to what the user likes, based on other users’ previous actions or explicit feedback such as rating on products. 

The idea of content-based filtering is that, if one person gave a rating of 4/5 for a movie, and another person also gave 4/5 for the same movie, then these two movies have high correlation. A pivot table is created to show the corresponding movie_rating and the corresponding user_id. If a user did not watch/rate that movie, 'NaN' will be shown. A pivot table is then converted to a csr_matrix. This is to save space as most of the values will be NaN. 


### Dataset Source : 
<a href = "https://www.kaggle.com/prajitdatta/movielens-100k-dataset">Kaggle Link</a>

### Jupyter Notebook : 
<a href = "https://github.com/neelesh2k/Movie-Recommender-based-on-User-Rating/blob/master/Movie%20Recommender%20based%20on%20User%20Rating.ipynb"> GitHub Link</a>

### Problem statement :
To build a Movie Recommender System based on the Customer ratings.
The n number of Movie are recommended based on the similarity of the movie ratings.

### Data Description :
MovieLens datasets were collected by the GroupLens Research Project at the University of Minnesota. This data set consists of:
- 100,000 ratings (1-5) from 943 users on 1682 movies.
- Each user has rated at least 20 movies.
- Simple demographic info for the users (age, gender, occupation, zip)

### The three datasets which have been used are:
- u.user : The user’s data file which contains 943 rows and 5 columns. The features are : 'user_id', 'age', 'sex', 'occupation', and 'zip_code'
- u.data : The rating’s data file which contain 100000 rows and 4 columns. The features are : 'user_id', 'movie_id', 'rating', and 'unix_timestamp'
- u.item : The movie’s data file which contains 1682 rows and 5 columns. The features are : 'movie_id', 'title', 'release_date', 'video_release_date', and 'imdb_url'

### Recommender system :
1. Find the pearson coefficient value between the selected Movie and all other Movies.
2. Neglet NaN values.
3. Create a list containing the coefficient value and sort it in descending order.
4. The number of recommendations are given based on the mentioned number.

### Pearson correlation coefficient :
Correlation is a technique for investigating the relationship between two quantitative, continuous variables, for example, age and blood pressure. Pearson's correlation coefficient (r) is a measure of the strength of the association between the two variables.

### Testing :
**Enter Movie Name : Toy Story (1995)**
**Enter number of recommendations : 10**

**Recommended Movies :**
- Beauty and the Beast (1991)
- Aladdin (1992)
- Craft, The (1996)
- Transformers: The Movie, The (1986)
- Lion King, The (1994)
- That Thing You Do! (1996)
- Raiders of the Lost Ark (1981)
- Apollo 13 (1995)
- Jurassic Park (1993)
- E.T. the Extra-Terrestrial (1982)

**Toy Story is a 1995 American produced by Pixar Animation Studios and released by Walt Disney Pictures.**

**Most of the recommended movies ( Beauty and the Beast, Aladdin, Lion King, etc. ) are . Thus we can say that our recommender system is working correctly.**

### KNN Item-Based Collaborative Filtering
Collaborative filtering systems use the actions of users to recommend other movies. In general, they can either be user-based or item-based. Item based approach is usually preferred over user-based approach. User-based approach is often harder to scale because of the dynamic nature of users, whereas items usually don’t change much, and item based approach often can be computed offline and served without constantly re-training.
To implement an item based collaborative filtering, KNN is a perfect go-to model and also a very good baseline for recommender system development.
kNN is a machine learning algorithm to find clusters of similar users based on common movie ratings, and make predictions using the average rating of top-k nearest neighbors.
We convert our table to a 2D matrix, and fill the missing values with 0 (since we will calculate distances between rating vectors). Since 0 is also a rating value, we will add 8 to the actual rating values. So a rating of 0 becomes 8 , a rating of 1 becomes 9, and a rating of 2 becomes 10.

### Converting the matrix to CSR Matrix (Compressed Sparse Row)
The compressed sparse row (CSR) or compressed row storage (CRS) or Yale format represents a matrix M by three (one-dimensional) arrays, that respectively contain nonzero values, the extents of rows, and column indices. It is similar to COO, but compresses the row indices, hence the name.


### Creating an instance of KNN :
- We use unsupervised algorithms with sklearn.neighbors.
- The algorithm we use to compute the nearest neighbors is “brute”.
- We specify “metric=cosine” so that the algorithm will calculate the cosine similarity between rating vectors.
- Finally, we fit the model.

### Cosine Similarity :
Let us take one movie as 'Kungfu Panda', and another movie be 'Avengers'. The movies can be represented in vectors. Let one movie be at (4,10) and another movie be at (7,3). We know that, cos(0) = 1 and cos(90) = 0. If both movies are in same plane, the similarity is 100%. Similarly, if two movies are at an angle of 45 degrees, the similarity is 53%. 

### Implementing KNN Algorithm:
In this step, the kNN algorithm measures distance to determine the “closeness” of instances. It then classifies an instance by finding its nearest neighbors, and picks the most popular class among the neighbors

### Testing:
**Enter Movie name : 101 Dalmatians (1996)**
**Enter number of recommendations : 10**
**Recommendations for 101 Dalmatians (1996):**
- Jack (1996)
- Twister (1996)
- Willy Wonka and the Chocolate Factory (1971)
- Independence Day (ID4) (1996)
-  Toy Story (1995)
-  Father of the Bride Part II (1995)
-  Hunchback of Notre Dame, The (1996)
-  Lion King, The (1994)
-  Mrs. Doubtfire (1993)
-  Jungle Book, The (1994)

**101 Dalmatians is a 1996 American live-action comedy adventure film.**

**Most of the recommended movies ( Jack , Father of the Bride Part II, Toy Story, etc. ) are . Thus we can say that our recommender system is working correctly.**

