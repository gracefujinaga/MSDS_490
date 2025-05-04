# Assignment 4 README

## Questions

#### Share your analysis on the recommendation produced using content-based filtering versus collaborative filtering in the previous module?
The recommendation produced using content-based filtering is much less diverse. Granted, with collaborative filtering, users are compared and then predictions made on potential ratings. Because users rated 20+ movies, there was more diversity because the predicted ratings used to recommend items were based on more than just one piece of content. The content-based filtering yielded less diverse recommendations because it was based on exactly one movie and only used genres. The movies recommended for Toy Story (1995) were movies with the same genre tags (['Adventure', 'Animation', 'Children', 'Comedy', 'Fantasy']). Many movies matched these genres exactly like the second toy story, Monsters, Turbo, etc. A lot of the movies recommended had a cosine similarity of 1 to toy story because they matched all of the genre tags exactly. The model would certainly perform better if tags beyond genre were used. This would not help the lack of diversity but would better narrow down the top 5 results. 

#### How would you address lack of diversity in the recommendations? For example, recommending all versions of Toy Story does not help as we know the user will like and perhaps watch all version of Toy Story if they have seen the original.

There seem to be a few potential ways to introduce diversity. To remove sequels of the original content, a rule could be used to filter those out of the potential recommendations with name matching or tags. Additionally, items with really high similarity rating, for example 1 if we're using cosine similarity, could be filtered out of the recommendations. A hybrid model of both collaborative filtering and content based filtering could be used to both increase diversity but also link the recommendations to a specific item. 

## References

Falk, K. (2019). Practical recommender systems. Manning Publications. Chapter 10

scikit learn. "LatentDirichletAllocation." https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.LatentDirichletAllocation.html. Accessed May 4, 2025.

OpenAI. 2025. ChatGPT (May 4 version). https://chat.openai.com/. Comparing the LDA library in gensim and scikit learn, understanding count vectors.



