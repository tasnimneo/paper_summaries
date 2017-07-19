## [A Latent Semantic Model with Convolutional Pooling Structure for Information Retrieval](http://www.iro.umontreal.ca/~lisa/pointeurs/ir0895-he-2.pdf)

<p align="justify">
In this paper, a latent semantic model based on the convolutional neural network with convolution-pooling structure, called the convolutional latent semantic model (CLSM), is developed to learn low-dimensional, semantic vector representations for search queries and web documents.
<p align="justify">


#### Key Idea

<p align="justify">
The model contains (1) a word-n-gram layer obtained by running a contextual sliding window over the input word sequence (i.e., a query or a document), (2) a letter-trigram layer that transforms each word-trigram into a letter-trigram representation vector, (3) a convolutional layer that extracts contextual features for each word with its neighboring words defined by a window, e.g., a word-n-gram, (4) a max-pooling layer that discovers and combines salient word-n-gram features to form a fixed-length sentence-level feature vector, and (5) a semantic layer that extracts a high-level semantic feature vector for the input word sequence.
<p align="justify">

#### Key Notes

<p align="justify">
The CLSM model directly represents local contextual features at the word n-gram level; i.e., it projects each raw word n-gram to a low-dimensional feature vector where semantically similar word ngrams are projected to vectors that are close to each other in this feature space. Moreover, instead of simply summing all local word-n-gram features evenly, the CLSM performs a max pooling operation to select the highest neuron activation value across all word n-gram features at each dimension, so as to extract the sentence-level salient semantic concepts. 

In this work, letter-trigram based word-n-gram is used to represent query and document. The convolutional layer and max-pooling layer each has 300 neurons, and the final output layer has 128 neurons. They considered window size from one to three because the average lengths of the queries and the document titles are only three and eight words respectively, window sizes larger than three do not provide much extra contextual information.

The weights of the neural network are randomly initialized. The model is trained using mini-batch based stochastic gradient descent. Each mini-batch consists of 1024 training samples.
<p align="justify">

**Evaluation Data and Method**: 

<p align="justify">
The evaluation data set contains 12,071 English queries sampled from one-year  query log files of a commercial search engine and labeled by human judgers. On average, each query is associated with 74 Web documents (URLs). Each query-document pair has a relevance label manually annotated on a 5-level relevance scale: bad, fair, good, excellent, and perfect, corresponding to 0 to 4, where level 0 (bad) means document is not relevant to query and level 4 (perfect) means that the document is the most relevant to query. All the queries and documents are preprocessed such that the text is white-space tokenized and lowercased, numbers are retained, and no stemming/inflection is performed. The average lengths of the queries and the document titles are 3.01 and 7.78 words, respectively. In their experiment, they found 30K unique letter-trigrams  in the training set after the data are lower-cased and punctuation removed. 

The performance of all ranking models we have evaluated has been measured by mean Normalized Discounted Cumulative Gain (NDCG), and we will report NDCG scores at truncation levels 1, 3, and 10 in this section.
<p align="justify">

**More details on this work**: [Unofficial implementation in keras](https://github.com/airalcorn2/Deep-Semantic-Similarity-Model)

**Bibliography**
```
@inproceedings{shen2014latent,
  title={A latent semantic model with convolutional-pooling structure for information retrieval},
  author={Shen, Yelong and He, Xiaodong and Gao, Jianfeng and Deng, Li and Mesnil, Gr{\'e}goire},
  booktitle={Proceedings of the 23rd ACM International Conference on Conference on Information and Knowledge Management},
  pages={101--110},
  year={2014},
  organization={ACM}
}
```
