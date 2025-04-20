# Assignment 3 README

## Questions
#### 1. In this module with MovieLens dataset, we predicted ratings. If user's predicted rating is low, then would you show it in your recommendation to the user? What can you do to address this issue?

It should not be shown to the user. If ALL of the predicted ratings are low, such as when n_neighbors = 2, that system shouldn't be used. We want to use the recommender system to predict things that the user will actually like. To address this issue, adjustments to the recommender system need be created. One adjustment might be adding a cut off rule so that instead of always showing 10 recommendations, at most 10 recommendations are made and they are only shown if the predicted rating is over a cutoff value. This would be a higher rating, so probably something like 3.5. 

#### 2. How do you find an optimal number of neighbors to pick for this model?

In this model, we could test an increasing number of neighbors and plot the resulting error metric. We can see how the error metric changes with the increase in neighbors. While in this model, computational efficiency was not a huge factor, in larger systems, memory and time could become a constraint with increased neighbor parameters. 

#### 3. While RMSE is a measure we can use to compare whether predicted ratings match actual ratings and see improvements after adding new features, it is not a robust metric for recommender systems. What are couple of limitations of using RMSE to evaluate recommender systems.

In this exploration, the lowest RMSE was when n_neighbors = 2. This model resulted in ratings close to 2 or 2.5. RMSE penalizes big errors, so it makes sense that predictions close to the middle of the range of ratings would result in a lower RMSE. With an increase in n_neighbors, the rmse increased along with the predicted ratings. With this said, a predicted rating of 2 or 2.5 feels too low to present that item to a user. Beyond penalizing outliers, RMSE also measures prediction errors across all items, which includes items that users might never see. 

## References
Falk, K. (2019). Practical recommender systems. Manning Publications. Chapter 9

Geeks for Geeks. 2024. "Recommender Systems using KNN." https://www.geeksforgeeks.org/recommender-systems-using-knn/. Accessed April 15th, 2025.

OpenAI. 2025. ChatGPT (April 20 version). https://chat.openai.com/. Comparing RMSE to other error metrics.

scikit learn. "NearestNeighbors". https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.NearestNeighbors.html. Accessed April 15th, 2025.
