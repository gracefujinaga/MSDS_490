
# Assignment 6 README

## Questions

Note: I had some issues with overlap in the models. For example, there are only 2,068 combined ratings. I know that there should be more because both datasets contain the same sets of asin and user_id but I didn't have time to explore this further. Additionally, I combined the cosine similarity with the predicted rating from the SVD model. This doesn't really make sense to predict a rating since they are not on the same scale. I ran out of time to find a good fix to combine the two more appropriately. I tried linear scaling but that didn't really yield seriously different results. 

#### The rationale is that by combining collaborative filtering and content-based filtering, your model should have performed better than each model separately. Was that the case? Why or why not?

In theory, hybrid filtering should outperform pure collaborative filtering or pure content-based filtering. An alpha of 0.7 did perform better than alpha = 0.5 in the hybrid filtering model, but this seems to be because it weighted the results from the SVD model more heavily while downplaying the results from the TF-IDF-based model. Even at alpha = 0.7, the hybrid model still didn’t outperform collaborative filtering alone across most metrics. This suggests that the content-based component may have actually hurt performance rather than helped. As I mentioned earlier, the disparity in scale between cosine similarity scores and predicted ratings likely contributed to this. While hybrid models are expected to leverage the strengths of both methods, in this case, the content-based filtering didn’t seem to add much value and may have even reduced overall effectiveness. I feel like this really lends itself to user error in the model (ie I should've addressed this issue) rather than the idea of hybrid filtering itself.


#### Given the dataset we experiment using ratings and reviews from the musical instrument category of a large eCommerce retailer, what other features would have helped your model perform better?

Features like instrument family, location, and age group could help with the collaborative filtering. Additionally, the time of some items/reviews would be helpful. For example, if someone bought a tuba recently, they are probably also looking for a tuba case. However, 3 years later, they likely are not looking for another tuba case and the review or purchase of the tuba is less relevant to the recommender system. Some sort of feedback on the filtering would also be helpful. Obviously this is the case with all recommender systems, but using A/B testing to decide on the right model weights or features would be very helpful. 

## References

Falk, K. (2019). Practical recommender systems. Manning Publications. Chapter 12

OpenAI. 2025. ChatGPT (May 12 version). https://chat.openai.com/. Normalization using Surprise SVD library, syntax changes for recall@k and precision@k functions
