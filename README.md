## recommender_system
Task: Under senarios such as recommendation based on searching words and relevant documents, or recommendation based on personalization and generally rough ranking, an interesting task to do is to learn the rank among the given set (relevant documents / rough ranking).
Application: Web search engine algorithms - searching rank, video recommendation.
* Metric: Discounted Cumulative Gain (DCG) - Assume <img src="https://latex.codecogs.com/svg.image?rel_i" title="rel_i" /> is the graded relevance of the i-th item in the result list. Then <img src="https://latex.codecogs.com/svg.image?DCG_k" title="DCG_k" /> is defined as:
<img src="https://latex.codecogs.com/svg.image?DCG_k&space;=&space;\sum_{i=1}^k&space;\frac{2^{rel_i}-1}{\log_2(i&plus;1)}" title="DCG_k = \sum_{i=1}^k \frac{2^{rel_i}-1}{\log_2(i+1)}" /> 
To evaluate the performance of ranking, one can use Normalized DCG (NDCG), defined as
<img src="https://latex.codecogs.com/svg.image?NDCG_k&space;=&space;\frac{DCG_k}{\max_{s\in\sigma([k])}DCG(s)_k}" title="NDCG_k = \frac{DCG_k}{\max_{s\in\sigma([k])}DCG(s)_k}" />

### RankNet
The idea of RankNet is to decompose the k-ranking problem into pairwise comparison. The input of RankNet is <img src="https://latex.codecogs.com/svg.image?(item_i,item_j)" title="(item_i,item_j)" /> and the output is <img src="https://latex.codecogs.com/svg.image?(s_i,s_j)" title="(s_i,s_j)" />. To minimize cross entropy loss defined as follows:
<img src="https://latex.codecogs.com/svg.image?L&space;=&space;-\hat{P}_{ij}\log&space;P_{ij}&space;-&space;(1-\hat{P}_{ij})\log&space;(1-P_{ij})" title="L = -\hat{P}_{ij}\log P_{ij} - (1-\hat{P}_{ij})\log (1-P_{ij})" />
. Here, we define <img src="https://latex.codecogs.com/svg.image?\hat{P}_{ij}=1" title="\hat{P}_{ij}=1" /> if i-item is more relevant, otherwise <img src="https://latex.codecogs.com/svg.image?\hat{P}_{ij}=0" title="\hat{P}_{ij}=0" />.



* Acceleration

### LambdaRank


### LambdaMart
