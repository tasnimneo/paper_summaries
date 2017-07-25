## [A Dual Embedding Space Model for Document Ranking](https://arxiv.org/pdf/1602.01137.pdf)

<p align="justify">
In this work, authors proposed to use both the input and the output embeddings learned using word2vec approach to leverage both the
embedding spaces to derive richer distributional relationships.
<p align="justify">

#### Key Idea

<p align="justify">
The Dual Embedding Space Model (DESM) is an information retrieval model that uses two word embeddings, one for query words and one for 
document words. It takes into account the vector similarity between each query word vector and all document word vectors.
<p align="justify">

#### Key Notes


**Evaluation Data and Method**

<p align="justify">
The performance of all ranking models evaluated has been measured by mean Normalized Discounted Cumulative Gain (NDCG), and we will report 
NDCG scores at truncation levels 1, 3, and 10 in this section.
<p align="justify">

**More details on this work**: [Project Page](https://www.microsoft.com/en-us/research/project/dual-embedding-space-model-desm/)


**Bibliography**
```
@article{mitra2016dual,
  title={A dual embedding space model for document ranking},
  author={Mitra, Bhaskar and Nalisnick, Eric and Craswell, Nick and Caruana, Rich},
  journal={arXiv preprint arXiv:1602.01137},
  year={2016}
}
```
