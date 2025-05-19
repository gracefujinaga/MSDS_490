
# Assignment 7 README

## Questions

Results
![Figure 1](/Images/results_assign_7.png)
*Table 1. Results from different LTR algorithms on the MovieLens Dataset*

#### Which of the three LTR algorithms had the highest accuracy? Why?
The listwise LTR algorithm had the highest accuracy. All three metrics were higher for the listwise model. It is difficult to compare the pointwise algorithm to the listwise because they don't have overlapping metrics. With that said, the listwise model performing better makes sense because it optimizes the entire ranked list. It does not focus on individual or pairwise item comparisons so the algorithm can capture a wider lens of comparison. It seems like this allows the model to better capture the structure and order of preferences. An RMSE of 1.020 in this case is also pretty bad because we normalized the ratings. Thus, most ratings are centered around 0. The average RMSE could be the difference between a positive rating and a negative rating which indicates a fairly weak model.


#### Why would NDCG@K be a more suitable metric than Precision@K for evaluating ranked lists in certain situations?
NDCG@K is a more suitable metric than Precision@K for evaluating ranked lists because precision@k does not take into account the order of the items in the list, just whether they should be there at all. NDCG@K weights higher ranked items more heavily, which rewards correctly ranking highly relevant items higher up in the list. Precision@k treats all items in the top k items the same. Thus, precision@k can be helpful in understanding a set of results but NDCG@K can evaluate a ranked list better. 


## References

Falk, K. (2019). Practical recommender systems. Manning Publications. Chapter 13

Lyst. "LightFM Documentation." https://making.lyst.com/lightfm/docs/index.html. Accessed May 18, 2025.

Microsoft. "LightGBM Documentation." https://lightgbm.readthedocs.io/en/latest/index.html. Accessed May 18, 2025.

OpenAI. 2025. ChatGPT (May 18 version). https://chat.openai.com/. lightgbm documentation and syntax, lightfm documentation and syntax.



