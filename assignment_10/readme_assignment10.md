
# Assignment 10 README

Note: I ended up implementing a model that just embedded the userid and movieid. Then, I realized I should probably take advantage of the additional user data (age, job, gender) and movie data (genres). I ultimately ended up with two different models. I know that even small differences in performance can result in millions of dollars, but I was surprised with how similar the metrics were for both models.

## Questions

#### How is retrieval latency impacted by two-tower models vs. interaction-based (single-tower) models?

The two-tower model architecture supports low-latency retrieval. Because of the two separate towers, the embeddings for all items can be precomputed and stored. This allows for a quick similarity search using a dot product when actually makeing a prediction. User embeddings can be computed as the recommender system runs. This precomputation of the item embeddings helps support low latency retrieval. Interaction-based models compute user-item features and doesn't allow for precomputation of item vectors. The models must compute similarity scores for every user-item pair which is expensive computationally and also very slow. The two tower model was one of the fastest models (if not the fastest) we have built in class. 


#### What types of features (dense, sparse) are ideal for sharding, and why?

Sparse features are ideal for sharding. Sparse features are categorical or discrete variables with high cardinality. For example, in this dataset that would be userIDs, item Ids, genre, occupation, and zip code. They map to embeddings and can be stored in large tables. These embedding tables grow to be very large when a large set of items and users exist. Because sparse features are discrete variables, the data can be sharded across multiple machines ore devices to prevent a single, HUGE, embedding table. Looking up the embeddings is fairly lightweight using hashing or other partitioning techniques, so sharding allows for increased efficiency as the model grows.

On the other hand, dense features, like continuous numeric vectors, don't benefit as much from sharding. Due to the more compact nature of the data, the trade off of increased complexity does not yield substantial performance gains. 



## References

PyTorch. “Northwestern University: PyTorch Hands-On Demo .” Published: 21 May 2025. Youtube VideoLinks to an external site.. Video Time: 58:22.

OpenAI. 2025. ChatGPT (May 27 version). https://chat.openai.com/. PyTorch help, Python syntax, fixing recommender code errors, syntax questions, understanding PyTorch code, understanding two tower model 


