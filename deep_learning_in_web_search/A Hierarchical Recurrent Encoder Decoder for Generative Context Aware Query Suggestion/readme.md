## [A Hierarchical Recurrent Encoder Decoder for Generative Context Aware Query Suggestion](https://arxiv.org/pdf/1507.02221.pdf)

<p align="justify">
In this work, authors presented a generative probabilistic model capable of producing synthetic, context-aware suggestions not only for
popular queries, but also for long tail queries. Given a sequence of queries as prefix, the proposed hierarchical recurrent encoder-decoder based model predicts the most likely sequence of words that follow the prefix. More specifically, given a query in the session, the proposed model encodes the information seen up to that position and tries to predict the following query. The process is iterated throughout all the queries in the session. The proposed architecture is shown below.
<p align="justify">

<p align="center">
<img src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/00f31994c123fbceba5d5a0e06bb78aff651aae7/3-Figure3-1.png" width="90%">
<p align="center">

#### Key Idea

<p align="justify">
Recurrent Neural Network can be trained to obtain an order sensitive representation of a query or to decode a sentence out of a given query encoding. These two use cases of RNNs are pipelined to a single recurrent encoder-decoder to predict the next query in a session given the previous one. They used an additional, session-level RNN on top of the query-level RNN ecndoer to form a hierarchical recurrent neural network. The query-level RNN is responsible to encode a query and the session-level RNN takes as input the query encoding and updates its own recurrent state. At a given position in the session, the session-level recurrent state is a learnt summary of the past queries, keeping the information that is relevant to predict the next one. At this point, the decoder RNN takes as input the session-level recurrent state, thus making the next query prediction contextual.
<p align="justify">

#### Key Notes

<p align="justify">
They used gated recurrent unit (GRU) as the recurrent neural network architecture to form the encoder and decoder. The model parameters are learned by maximizing the log-likelihood of a session. The gradients were computed using the back-propagation through time (BPTT) algorithm. Their proposed model is used both for generating queries and scoring a given suggestion conditioned on the history of previous queries. They have also used beam-search while decoding a query. With a beam size of 50, the training time was approximately 44 hours for 135,350 batches.
<p align="justify">

**Evaluation Data and Method**

<p align="justify">
They executed their experiments on the AOL search log. They removed all nonalphanumeric characters from the queries, applied a spelling corrector and lowercasing. They defined the end of a session by a 30 minute window of idle time. They used the last one month of the AOL search log for training, validation and testing. First two weeks of data are used as a training set and the remaining two weeks are split into the validation and the test set. In total, there were <b>435,705</b> sessions in the training set, <b>166,836</b> in the validation set and <b>230,359</b> in the test set.

Vocabulary size in their experiments was 90K. They used gradient clipping (threshold, c=1) and early stopping during training. The training stops if the likelihood of the validation set does not improve for 5 consecutive iterations. Parameter optimization is done using mini-batch RMSPROP. The dimensionality of the query and session level RNN was set to 1000 and 1500 respectively. Embedding dimension was set to 300.

As a part of their evaluation, they did a user study to test the generative capabilities of their query suggestion system. The assessment was conducted by a group of 5 assessors. 
<p align="justify">

**More details on this work**: [Official implementation in theano](https://github.com/sordonia/hred-qs)

**Bibliography**
```
@inproceedings{sordoni2015hierarchical,
  title={A hierarchical recurrent encoder-decoder for generative context-aware query suggestion},
  author={Sordoni, Alessandro and Bengio, Yoshua and Vahabi, Hossein and Lioma, Christina and Grue Simonsen, Jakob and Nie, Jian-Yun},
  booktitle={Proceedings of the 24th ACM International on Conference on Information and Knowledge Management},
  pages={553--562},
  year={2015},
  organization={ACM}
}
```
