# Movie-Recommendation-System
## Group 1
## Authors:
JUSTIN MBUGUA

DENNIS MWANIA

SHARON MOMANYI

STEPHEN MUNYIALA

TABBY MIRARA

## Overview.
The goal of this project is to build a Movie Recommender System using data mining techniques. The system is designed to assist users in selecting movies that match their preferences based on past user ratings.

## Problem Statement.

The modern film enthusiast faces an overwhelming decision - a wealth of cinematic options, yet a struggle to find films that align with their preferences. The challenge lies in the initial selection as well as finding movies within the same niche or genre. Users often find themselves lost in the vast sea of content, seeking a solution that not only recommends the first movie but also facilitates a smooth journey through related titles.

## Objectives

To create a Collaborative Filtering based Movie Recommendation System.

Predict the rating that a user would give to a movie that they have not yet rated.

Minimize the difference between predicted and actual rating (RMSE and MAE)

## Data Understanding
This dataset (ml-20m) utilizes information from IMDband TMDb and describes 5-star rating and free-text tagging activity from MovieLens, a movie recommendation service. It contains 100836 ratings and 3683 tag applications across 9742 movies.(MovieLens)
## Data Cleaning and preparation
Data Description
The project focused on the following two separate files:
1. Ratings Data (ratings.csv)

•	This dataset contains the primary information used to build the recommendation system with 100,000 rows and 4 columns Each row represents a user's rating for a specific movie, where:

	userId: Unique identifier for each user.

	movieId: Unique identifier for each movie.

	rating: User’s rating of the movie on a scale from 0.5 to 5.0 (in increments of 0.5).

	timestamp: The time when the rating was provided.

2. Movies Data (movies.csv)

•	This dataset provides details on movies with 1,682 rows and 3 columns:

	movieId: Unique identifier for each movie (matches the movieId in ratings).

	title: Name of the movie.

	genres: Movie genres (a movie can belong to multiple genres).

## Exploratory Data Analysis
Checking User Distribution Rating

![image alt](https://github.com/StephenMuuo/Movie-Recommendation-System/blob/b0491f52d8de32498f2ed9d2f669bc0f333c8f2c/Distribution%20of%20user%20rating%20count..PNG)

We can see that most users rate very few movies, and few users rate many movies.
This shows that the dataset has a lot of users with little interaction.

Checking Movie rating Counts

![image alt](https://github.com/StephenMuuo/Movie-Recommendation-System/blob/24da8c7d5718117cb9c249edf22a845f876d741f/Distribution%20of%20movie%20rating%20counts..PNG)

From this plot, it is evident that, very many movies have few ratings while few movies have many ratings.

Checking Ratings distribution

![image alt](https://github.com/StephenMuuo/Movie-Recommendation-System/blob/053dc27f9d5a8ce649667deddcc2fe77b2c4d0ef/Ratings%20distribution..PNG)

Most movies recieve a rating of 4.0 followed by 3.0.
It is possible that users are generous with their ratings, giving a 3 if they don't really like a movie, 4 if the movie was alright and 5 if they really enjoyed the movie.

Checking for rating Count.

![image alt](https://github.com/StephenMuuo/Movie-Recommendation-System/blob/42c6a5ac540dbe38d72f6da932e25e54f5d81d21/Genre%20count.PNG)

Drama has the highest ratings followed by comedy while film-Noir has the least count of ratings.

Checking for average rating per genre

![image alt](https://github.com/StephenMuuo/Movie-Recommendation-System/blob/342100aec28804db77abd17041e6898d8ff7370c/Average%20rating%20per%20genre.PNG)

Film-Noir, War, and Documentary have the highest average ratings although they appear least frequently in the previous graph.
This implies that these genres have niche audiences, who enjoy these movies and rate them highly.

## Modeling

Collaborative Filtering (SVD)
This was used to recommend movies based on user behaviour.

Content-Based Filtering
This was used to compute the similarity between movies based on their genres. It allows us to recommend movies that share similar genre characteristics.

Hybrid Recommendation System
This was used to improve recommendation quality, CF (SVD) is blended with CBF (genre similarity).
This approach balances personalized predictions with genre- based similarities, helping address the cold start problem for new users.

### Model comparison
SVD consistently has a lower RMSE and MAE compared to the Hybrid system. This suggests that, in this particular evaluation, SVD is making more accurate predictions than the Hybrid approach.

The Hybrid system shows significantly higher RMSE and MAE. This indicates that its predictions are further from the actual ratings than those of SVD.

![image alt](https://github.com/StephenMuuo/Movie-Recommendation-System/blob/3b4151617609f8d98455110a63d153fb97186ac4/Compa.PNG)

### Error Distribution

The Hybrid Model appears to be biased negatively but appears to be more consistent and has lower error variance. Since the goal is to have errors closer to zero on average, the SVD model is more preferable but its spread suggests that it's inconsistent.

![image alt](https://github.com/StephenMuuo/Movie-Recommendation-System/blob/9db04cf81f4000c8ecee03d279d2dd2af9efacb4/error%20distri.PNG)

## Recommendations

Collaborative filtering (SVD) is the best model for the recommender system since it has a lower RMSE and MAE compared to the hybrid recommendation system.

When a user is new, recommend movies based on their popularity while, for a current user, use their previous information on movie ratings and genres preferred to tailor recommendation.

## Conclusions

In this Analysis, we evaluated the performance of different models for predicting movie ratings; SVD and a Hybrid model. Though the hybrid model was more consistent, the goal was to have errors close to zero on average which is why the SVD model is more preferable.

## Next Steps

Model Tuning: Further hyperparameter tuning for both models.

Hybrid model enhancements: Advanced hybridization techniques such as weighted blending or even adding more CBF should be considered to help reduce hybrid model's bias and improve performance.

Cold-Start Problem: In the analysis, we attempted to solve the problem using global genre preference. Popularity-Based Recommendations should also be considered to try and address the problem.
