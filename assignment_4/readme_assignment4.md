# Assignment 4 README

## Questions
#### For each of the following metrics, provide a business justification as to why you would use this metric to evaluate your model? RMSE, Precision@K, Recall@K, nDCG, MAP and AUC

- RMSE: RMSE measures how close the model's predicted ratings were to the actual user ratings. A low RMSE means better personalization, but as we've seen throughout the weeks, it is not infallible. A predicted rating of 2 or 2.5 on a scale of 1 to 5 across a whole dataset might reduce RMSE, but not accurately predict a rating. With that said, RMSE handles non-binary data, and can actually compare a numerical rating. This could be helpful when it is important for the system to accurately understand strength of the preference of the user. 

- Precision@K: Precision@K measures how many recommendations shown to the user were actually liked by the user. This metric is important to measure customer satisfaction. Bad recommendations make the system seem unreliable and unhelpful, and could push the user to other platforms. 

- Recall@K: Recall@K measures how many of the total relevant items we are showing to the user. I think this would be particularly helpful if we are lookign for breadth and more items shown. I'm thinking of spotify recommendations or book recommendations where there is variety in taste and there is breadth in what is shown. The exact rank may not be as important, but the item should be shown.

- nDCG: nDCG rewards models that rank the best recommendations higher up the list by discounting lower ranked items. I think this is a really strong metric because we want to not only show the user good movies but also rank the best ones at the top. We would definitely want to use nDCG if the ranking order is essential in maximizing user satisfaction. 

- MAP: Mean Average Precision"measure how good the rank is by running the precision from 1 to m, where m is the number of items that are recommended (usually denoted as k)" (Falk 2019, ch. 9). We would want to use this to understand overall ranking quality across the recommender system

- AUC: auc reflects the probability that the model ranks a randomly chosen liked item higher than not a liked one. It only handles binary classification. 0.5 is a guess and the metric ranges from 0 to 1. We would use this metric to measure binary data. It is a common metric in scientific research. 



#### Expand on why Precision@K and Recall@K must be analyzed together for a balanced view and their relationship to each other in a recommender systems model.

Precision@K measures, of the top K recommendations we show, how many the user actually liked, while Recall@K measures how well we capture all of the relevant items for the user. They complement each other because Precision@K focuses on the quality of the top recommendations, while Recall@K reflects how many of the total relevant items we are surfacing. The tradeoff between the two reflects the balance of user satisfaction and coverage. 


## References

Falk, K. (2019). Practical recommender systems. Manning Publications. Chapter 9

Surprise. 2025. General Documentation. https://surpriselib.com/

Surprise. 2025. "FAQ." https://surprise.readthedocs.io/en/stable/FAQ.html#how-to-compute-precision-k-and-recall-k. Accessed April 26th, 2025.

OpenAI. 2025. ChatGPT (April 20 version). https://chat.openai.com/. Comparing RMSE to other error metrics, syntax for barplots, Suprise library syntax.

scikit learn. "ndcg_score". https://scikit-learn.org/stable/modules/generated/sklearn.metrics.ndcg_score.html Accessed April 27th, 2025. 

scikit learn. "ConfusionMatrixDisplay". https://scikit-learn.org/stable/modules/generated/sklearn.metrics.ConfusionMatrixDisplay.html. Accessed April 27th, 2025.

scikit learn. "AveragePrecisionScore". https://scikit-learn.org/stable/modules/generated/sklearn.metrics.average_precision_score.html. Accessed April 27th, 2025.



