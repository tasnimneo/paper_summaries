## [A Dual Embedding Space Model for Document Ranking](https://arxiv.org/pdf/1602.01137.pdf)

<p align="justify">
In this work, authors proposed Dual Embedding Space Model (DESM) to use both the input and the output embeddings learned using word2vec approach to leverage both the embedding spaces to derive richer distributional relationships. They map the query words into the input space and the document words into the output space, and compute a relevance score by aggregating the cosine similarities across all the query-document word pairs.
<p align="justify">

#### Key Idea

<p align="justify">
Continuous Bag-of-Words (CBOW) and Skip-Gram (SG) model contains two separate embedding spaces (IN and OUT) whose interactions capture additional distributional semantics of words that are not observable by considering any of the two embeddings spaces in isolation. These two model "pushes" the IN vectors of words closer to the OUT vectors of other words that they commonly co-occur with. In doing so, words that appear in similar contexts get pushed closer to each other within the IN embedding space (and also within the OUT embedding space). Therefore the IN-IN (or the OUT-OUT) cosine similarities are higher for words that are typically (by type or by function) similar, whereas the IN-OUT cosine similarities are higher for words that co-occur often in the training corpus (topically similar).
<p align="justify">

#### Key Notes


**Evaluation Data and Method**

<p align="justify">
All the datasets that are used for this study are sampled from Bing’s large scale query logs. They generated 3 version of evaluation datasets. (1) Explicitly judged test set which are judged by human evaluators, (2) Implicit feedback based test set which contains binary relevance judgement based on whether the document was clicked by the user and (3) Implicit feedback based training set which is only used for tuning the parameters for the BM25 baseline and the mixture model.

The performance of all ranking models evaluated has been measured by mean Normalized Discounted Cumulative Gain (NDCG), and we will report NDCG scores at truncation levels 1, 3, and 10 in this section.
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
