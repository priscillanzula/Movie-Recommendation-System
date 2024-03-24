# Recommendation_System_movies
PROJECT OVERVIEW

Jaba Movie Shop endeavors to optimize user engagement and satisfaction through the implementation of a recommendation system. Jaba Movie Shop seeks to leverage on the extensive database of movieLens, to ensure that clients are paired with films that resonate with their preferences. The movies with high ratings are likely to be the mostly watched movies indicating customer satisfaction.


Objective
The objective of this project is build a model that provides the top movie recommendations to a user, based on their ratings of other movies. By leveraging machine learning algorithms, collaborative filtering and content-based filtering the project aims to:

Enhance user engagement by providing a platform where they get best recommendations based on their reviews, tags and ratings.
Build a model that provides the top movie recommendations to a user.
Enhance customer satisfaction.

The libraries we will need;

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.metrics.pairwise import cosine_similarity
from sklearn.neighbors import NearestNeighbors
from sklearn.preprocessing import LabelEncoder
from sklearn.decomposition import TruncatedSVD
from sklearn.metrics import mean_squared_error
import warnings
warnings.filterwarnings("ignore")



```





![movie distribution by year](https://github.com/priscillanzula/Movie-Recommendation-System/assets/144167777/2c35da1a-5238-4b64-95f4-718172dfaafc)

The above distribution is a gaussian distribution.It is symmetrical about the mean and is rightly skewed. There’s a gradual increase from 1900 to 1980, a significant rise from 1980 to 2010, and a decline after 2010The long tail on the right suggests that there are a few years with exceptionally high movie production as seen in year 2000.



![movie ratings box-plot](https://github.com/priscillanzula/Movie-Recommendation-System/assets/144167777/c8fc1349-1787-412e-9166-cc8615a928e0)


The box plot above is a summary of ratings. It shows that most ratings are between 3 and 4, and there are a few very low ratings (1), which are unusual or “outliers”. The people simply gave ratings from okay to good.




![Count movies by genre](https://github.com/priscillanzula/Movie-Recommendation-System/assets/144167777/b5958925-1d63-4300-bda6-69d3c1364382)

The above bar shows how many movies have been made in different genres. The most movies have been made in the Drama genre, followed by Comedy, Romance, and Thriller. Fewer movies have been made in genres like Western and Film-Noir


![Rating distribution](https://github.com/priscillanzula/Movie-Recommendation-System/assets/144167777/2a6a08fd-3bb7-442f-affa-27d36813c96a)

The graph shows a distribution of ratings. It tells us that the data is not centered around a single value. The peaks at ratings 1, 2, 4, and 5 suggest that these ratings are the most common or frequent. The areas where the graph is low indicate ratings that are less common.


![popularityby rating](https://github.com/priscillanzula/Movie-Recommendation-System/assets/144167777/02157da1-b1b9-4ec2-9506-97f98e8a95b3)

The scatter plot shows the distribution of movies based on their popularity and average ratings. Movies with a higher number of ratings are more popular. The concentration of points indicates that movies with an average rating between 3 and 4 are the most popular. This could be because these movies are generally well-received by the audience, leading to more people watching and rating them. 

![average rating by year](https://github.com/priscillanzula/Movie-Recommendation-System/assets/144167777/3c0e6281-13f9-4dfc-854e-5331727f5e70)


The line graph above tracks the average movie rating for each year from 1900 to 2020. The line goes up and down, which means the average rating changes every year. Some years have higher ratings, and some years have lower ratings.

DATA MODELLING

We trained the recommendation model using Pearson Correlation Coefficient (PCC) collaborative
filtering and the nearest neighbors algorithm with cosine similarity.

 Pearson Correlation Coefficient (PCC)
 
This pivot table essentially organizes the data to facilitate correlation analysis between users’ ratings
of different movies.

```
def recommend_movie(movie):
movie_watched = userid_pivot[movie]
similarity_with_other_movies = userid_pivot.corrwith(movie_watched)
similarity_with_other_movies = similarity_with_other_movies.
↪sort_values(ascending=False)
return similarity_with_other_movies.head()

```

The recommend_movie function takes a movie title as input and returns a list of movies that are
most similar to the input movie based on user ratings. It first retrieves the ratings of the input
movie from a pivot table containing user ratings for all movies. Then, it calculates the correlation
(similarity) between the input movie’s ratings and all other movies, sorting them in descending
order of similarity. Finally, it returns the top similar movies along with their similarity scores,
allowing for easy recommendation of movies that share similar ratings patterns with the input
movie.

Recommendation

We hereby, k-nearest neighbours becuase it is simple yet effective.
It is based on the intuitive concept that similar users have similar preferences. It works by finding
similar users based on their ratings and recommends items(in our case movies) liked by those similar
users.

Conclusions:

1. Effectiveness of K-Nearest Neighbors (KNN) Approach: The decision to utilize the KNN algorithm for movie recommendations proved to be justified, as evidenced by the project's RMSE score of 1.033. KNN's simplicity and reliance on user similarity facilitated the accurate prediction of movie preferences, aligning well with the project's objective of enhancing user satisfaction through personalized recommendations.

2. Personalized Recommendations Enhance User Engagement: The implementation of personalized movie recommendations based on user reviews, tags, and ratings significantly improved the overall user experience. Through leveraging machine learning algorithms such as KNN, the system was able to suggest top movie recommendations tailored to individual user preferences, increasing the likelihood of user interaction and satisfaction.





~~~Group 6.
