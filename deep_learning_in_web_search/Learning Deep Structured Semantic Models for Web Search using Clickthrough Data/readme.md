## [Learning Deep Structured Semantic Models for Web Search using Clickthrough Data](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/cikm2013_DSSM_fullversion.pdf)

<p align="justify">
In this work, a latent semantic model with a deep structure is proposed that project queries and documents into a common low-dimensional space where the relevance of a document given a query is readily computed as the distance between them. The proposed deep structured semantic models are discriminatively trained by maximizing the conditional likelihood of the clicked documents given a query using the clickthrough data. The proposed deep structured semantic model is shown below.
<p align="justify">

<p align="center">
<img src="http://cdn-ak.f.st-hatena.com/images/fotolife/l/levelfour/20160531/20160531082504.png" width="90%">
<p align="center">

#### Key Idea

<p align="justify">
The input (raw text features) to the DNN is a highdimensional term vector and the output of the DNN is a concept vector in a low-dimensional semantic feature space. It works for web document ranking as follows. (1) Map term vectors to their corresponding semantic concept vectors and (2) compute the relevance score between a document and a query using cosine similarity of their corresponding semantic concept vectors.

They used word hashing to reduce the dimensionality of the bag-of-words term vectors. Given a word (e.g. good), they first add word starting and ending marks to the word (e.g. #good#). Then, they break the word into letter n-grams (e.g. letter trigrams: #go, goo, ood, od#). Finally, the word is represented using a vector of letter n-grams.
<p align="justify">

#### Key Notes

<p align="justify">
For the DNN experiments, they used the architecture with three hidden layers as shown in the above figure. The first hidden layer is the word hashing layer containing about 30k nodes (e.g., the size of the letter-trigrams). Word hashing is done based on a fixed projection matrix. The next two hidden layers have 300 hidden nodes each, and the output layer has 128 nodes. The similarity measure is based on the output layer with the dimensionality of 128.

In the training stage, they optimized the model using mini-batch based stochastic gradient descent (SGD). Each mini-batch consists of 1024 training samples. They observed that the DNN training usually converges within 20 epochs (passes) over the entire training data.
<p align="justify">

**Evaluation Data and Method**

<p align="justify">
The evaluation data set contains 16,510 English queries sampled from one-year query log files of a commercial search engine. On average, each query is associated with 15 Web documents (URLs). Each query-title pair has a relevance label. The label is human generated and is on a 5-level relevance scale, 0 to 4, where level 4 means that the document is the most relevant to query and 0 means document is not relevant to query. All the queries and documents are preprocessed such that the text is white-space tokenized and lowercased, numbers are retained, and no stemming/inflection is performed.
<p align="justify">

<p align="justify">
The performance of all ranking models we have evaluated has been measured by mean Normalized Discounted Cumulative Gain (NDCG), and we will report NDCG scores at truncation levels 1, 3, and 10 in this section.
<p align="justify">


**More details on this work**: [Conference Presentation](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/DSSM_cikm13_talk_v4.pdf)

**Bibliography**
```
@inproceedings{huang2013learning,
  title={Learning deep structured semantic models for web search using clickthrough data},
  author={Huang, Po-Sen and He, Xiaodong and Gao, Jianfeng and Deng, Li and Acero, Alex and Heck, Larry},
  booktitle={Proceedings of the 22nd ACM international conference on Conference on information \& knowledge management},
  pages={2333--2338},
  year={2013},
  organization={ACM}
}
```
