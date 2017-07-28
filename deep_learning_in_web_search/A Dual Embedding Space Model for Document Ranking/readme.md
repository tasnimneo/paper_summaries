## [A Dual Embedding Space Model for Document Ranking](https://arxiv.org/pdf/1602.01137.pdf)

<p align="justify">
In this work, authors proposed Dual Embedding Space Model (DESM) to use both the input and the output embeddings learned using word2vec approach to leverage both the embedding spaces to derive richer distributional relationships. They map the query words into the input space and the document words into the output space, and compute a relevance score by aggregating the cosine similarities across all the query-document word pairs.
<p align="justify">

#### Key Idea

<p align="justify">
Continuous Bag-of-Words (CBOW) and Skip-Gram (SG) model contains two separate embedding spaces (IN and OUT) whose interactions capture additional distributional semantics of words that are not observable by considering any of the two embeddings spaces in isolation. These two model "pushes" the IN vectors of words closer to the OUT vectors of other words that they commonly co-occur with. In doing so, words that appear in similar contexts get pushed closer to each other within the IN embedding space (and also within the OUT embedding space). Therefore the IN-IN (or the OUT-OUT) cosine similarities are higher for words that are typically (by type or by function) similar, whereas the IN-OUT cosine similarities are higher for words that co-occur often in the training corpus (topically similar).
<p align="justify">

#### Key Notes

<p align="justify">
They have two variants of their proposed model where they considered IN-OUT and IN-IN embedding space. On both the evaluation dataset, IN-OUT variant (trained on queries) performed better than all baseline models (BM25 and LSA baselines) and IN-IN model. From their experiment, they concluded that the DESM is primarily suited for ranking at top positions or in conjunction with other document ranking features as all DESM variants perform poorly in non-telescoping settings.
<p align="justify">
  
**Evaluation Data and Method**

<p align="justify">
All the datasets that are used for this study are sampled from Bing’s large scale query logs. They generated 3 version of evaluation datasets. (1) Explicitly judged test set (7,741 queries) which are judged by human evaluators, (2) Implicit feedback based test set (7,477 queries) which contains binary relevance judgement based on whether the document was clicked by the user and (3) Implicit feedback based training set (7,429 queries) which is only used for tuning the parameters for the BM25 baseline and the mixture model.
<p align="justify">
  
<p align="justify">
They have two different experiment settings, telescoped and non-telescoped. In telescoped setting, they considered all documents retrieved by Bing as the candidate set of documents to be re-ranked for each query. In the non-telescoped setting, they considered every distinct document in the test set as a candidate for every query in the same dataset. The performance of all ranking models evaluated has been measured by mean Normalized Discounted Cumulative Gain (NDCG), and we will report NDCG scores at truncation levels 1, 3, and 10 in this section.
<p align="justify">

**More details on this work**: [Project Page](https://www.microsoft.com/en-us/research/project/dual-embedding-space-model-desm/). 

A shorter version of this work ([Improving Document Ranking with Dual Word Embeddings](http://dl.acm.org/citation.cfm?id=2889361)) was published in WWW'16.



**Bibliography**
```
@article{mitra2016dual,
  title={A dual embedding space model for document ranking},
  author={Mitra, Bhaskar and Nalisnick, Eric and Craswell, Nick and Caruana, Rich},
  journal={arXiv preprint arXiv:1602.01137},
  year={2016}
}
```
