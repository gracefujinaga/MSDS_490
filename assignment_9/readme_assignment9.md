
# Assignment 9 README

## Questions

#### Briefly explain the performance between the DLRM and GR models. Would it make sense to only use GR models going forward or do traditional recommender models have justifiable use case? Explain and provide examples of such use cases.

The DLRM performed way better than the GR. With that said, I ran out of time to really implement the GR and relied heavily on chatgpt and a very simple architecture. I think if I had been able to use the facebook created version, this would not be the case. In this specific case, it clearly doesn't make sense to only use GR models. Traditional models like the NCF model used here perfomred pretty well. I think it always makes sense to test multiple models. 

Additionally, it seems like the different models might fit different user behavior better. For example, a traditional model that can capture user-item interactions might be better when rating is involved because they can capture a rating. With that said, a GR model might be better when a user is interacting with other items. An example of this could be listening to a song, clicking on a dress on an online website, or interactions along those lines. They also can capture changes in user preferences. This seems particularly useful in something like TikTok or instagram where user preferences change often and likes/interactions/comments are tracked.

At the end of the day, I think the DLRM can capture more about a user preference while the GR model can capture more user interactions. Here the GR performed poorly, but obviously that was not the case in the published paper. At the end of the day, I think there is almost always a case to be made in being open minded about choosing models and representations. 

#### Explain and interpret the performance metrics between the DLRM and GR models that you created.

GR:
NDCG@10: 0.0428
precision@10: 0.0925
recall@10: 0.0925
NDCG@100: 0.2101
precision@100: 1.0000
recall@100: 1.0000

DLRM:
precision at 10: 0.9250123556102413
precision at 100: 0.9007493223137176
recall at 10: 0.5557129296813126
recall at 100: 0.8849393563410966
NDCG@10: 0.9051660993065578
NDCG@100: 0.9296560788888077

Overall, the DLRM outperforms the GR model across all metrics. While the GR model ran much faster, it is much simpler than the one that facebook created. The GR model shows low precision, recall, and NDCG @10. This shows bad ranking and relevance but recall improves @100. This points to the idea that it can actually get the relevant items but is bad at ranking them. The DLRM ultimately achieves high metrics @10. Precision decreases @100, while reclal and NDCG both increase. This shows that the model both identifies and ranks relevant movies well. Overall, the DLRM outperformed the GR in this case.


## References

Zhai, J., Liao, L., etal. (2024). *Actions Speak Louder than Words: Trillion-Parameter Sequential Transducers for Generative Recommendations*  (arXiv:2402.17152v3). arXiv. https://doi.org/10.48550/arXiv.2402.17152

OpenAI. 2025. ChatGPT (June 1 version). https://chat.openai.com/. Understanding the facebook research, adjusting the pytorch model from assignment 8, syntax, error messages, fixing the DataLoader, interactive documentaiton help.



