## [Show, Attend and Tell: Neural Image Caption Generation with Visual Attention](http://jmlr.csail.mit.edu/proceedings/papers/v37/xuc15.pdf)

<p align="justify">
In this paper, authors introduced an attention based model that automatically learns to describe the content of images. Their proposed model learns the lower-level representation by attending different locations in the image. They presented two variants of attention mechanism: a "hard" stochastic attention mechanism and a "soft" deterministic attention mechanism.
<p align="justify">

#### Key Points

- Their model takes a single raw image and generates a caption encoded as a sequence of 1-of-K encoded words where K is the size of the vocabulary. They used a convolutional neural network in order to extract a set of feature vectors which they refered as annotation vectors. All the extracted "L" feature vectors are of dimension D which represents a region of the image.
- They used a long short-term memory (LSTM) network that produces a caption by generating one word at every time step conditioned on a context vector, the previous hidden state and the previously generated words. The context vector provides a dynamic representation of the relevant part of the image input at time *t*.
- For each image location, they used stochastic and deterministic attention mechanism to compute weight which can be interpreterd either as the probability that an image location is the right place to focus for producing the next word (stochastic attention) or the relative importance to give to the location in blending the attention wieghts together (deterministic attention).

#### Notes

<p align="justify">
Both variants of their attention model were trained with stochastic gradient descent using adaptive learning rates. They found RMSProp works better for Flickr8k dataset and Adam works better for Flickr30k for MSCOCO dataset. They used mini-batch size of 64 during training and dropout with early stopping on BLEU score as regularization strategy. For all their experiments, they used a fixed vocabulary size of 10,000. They used BLEU-1,2,3,4 and METEOR to evaluate their models.
<p align="justify">

**Expermental Dataset**: [MSCOCO](http://mscoco.org/), [Flickr8k](http://shannon.cs.illinois.edu/DenotationGraph/), [Flickr30k](http://shannon.cs.illinois.edu/DenotationGraph/)

**More details on this work**: [Official Implementation in Theano](https://github.com/kelvinxu/arctic-captions), [Presentation by Yunchen Pu](http://people.ee.duke.edu/~lcarin/Yunchen9.25.2015.pdf)

**Bibliography**
```
@inproceedings{xu2015show,
  title={Show, Attend and Tell: Neural Image Caption Generation with Visual Attention.},
  author={Xu, Kelvin and Ba, Jimmy and Kiros, Ryan and Cho, Kyunghyun and Courville, Aaron C and Salakhutdinov, Ruslan and Zemel, Richard S and Bengio, Yoshua},
  booktitle={ICML},
  volume={14},
  pages={77--81},
  year={2015}
}
```
