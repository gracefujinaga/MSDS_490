# Assignment 2 README

## Questions
#### 1. What do the averages of the different similarity methods mean for this dataset (e.g.: are smaller or larger averages better)?
Pearson's similarity measure falls between -1 and 1, where 0 is 100% dissimilar and -1 reflects a perfect negative correlation and 1 reflects a perfect positive correlation. Cosine and Jaccard similarities measures go from 0 to 1, with 0 being zero similarity to 1 being perfectly similar. 

For this assignment, I computed user-user similarity. The average over the pairwise similarities were pretty low. All 6 of the computed averages are listed below:

**Non Normalized Averages:**
average cosine similarity: 0.17206439491686415
average jaccard similarity: 0.07773490395706854
average pearson similarity: 0.13338772873766844


**Normalized Averages**
average cosine similarity: 0.023356441305914803
average jaccard similarity: 0.05781329884415803
average pearson similarity: 0.023356441305914803

The average cosine and pearson similarities are similar in terms of the non normalized average but exactly the same with normalization. They are similar metrics (Falk Chapter 7), so it makes sense they yielded similar similarity averages. The average jaccard similarity was very low and decreased with normalization. Specifically to this dataset, an arbitrary decision of a rating over 2.5 was deemed liked (1) and less than 2.5 was deemed disliked (0). An issue with this is that the user-item matrix entry for an item that the user didn't purchase is also a 0. It would also have been possible to have 1 represent a purchase and 0 to represent an item a user hadn't purchased. I tested both and arbitrarily decided to use the ranking system, but it would be helpful to further test this as other algorithms are applied.

In terms of the different averages, higher averages tend to be better. With that said, averages seem like a difficult way to measure the accuracy of a similarity metric across the whole dataset. We probably want higher similarity averages because if similarity measures are higher, the users are more similar, and we can provide better recommendations. With that said, to provide the best recommendations, we also want to see clusters of users, and an average cannot capture that. There might be some users that are HIGHLY similar that bring that average up, and then some users that are highly dissimilar that bring the average down.

#### 2. Which similarity method would you use in this case?

In this case, I would probably use the non-normalized cosine metric. The sklearn package used applies the L2 normalization in the cosine measurement, but when normalization was applied to the whole dataset (subtracting the row mean from each matrix entry in that row), the average similarity decreased. The cosine and pearson metrics are very close, but cosine slightly outperforms it without normalization. Both are fairly quick to compute, and there was not one that computationally outperformed the other.

#### 3. Is it better to normalize data for this dataset?

It seems like it is better to not normalize the data for this dataset. All 3 metrics decreased across the board, and it looks like normalizing may have taken out some salient features from this dataset.

## References
Falk, K. (2019). Practical recommender systems. Manning Publications. Chapter 7

OpenAI. 2025. ChatGPT (April 13 version). https://chat.openai.com/. Used to describe the differences between the 3 similarity techniques, create matrix from dataframe, seaborn syntax. 

scikit learn. "Pairwise Distances". https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise_distances.html

scikit learn. "Cosine Similarity". https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html

Magiya, Joseph. 2019. "Pearson Coefficient of Correlation with Python." https://levelup.gitconnected.com/pearson-coefficient-of-correlation-using-pandas-ca68ce678c04