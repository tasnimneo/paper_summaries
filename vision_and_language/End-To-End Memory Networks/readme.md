## [End-To-End Memory Networks](https://arxiv.org/pdf/1503.08895.pdf)

<p align="justify">
In this work, authors introduced a neural network with a recurrent attention model and an external memory which can be trained end-to-end via backpropagation on diverse tasks from question answering to language modeling. Their model requires very less supervision of supporting facts which increases its applicability but this model cannot match the performance the memory networks trained with strong supervision. Important characteristics of the proposed model are, (1) reads from memory with soft attention, (2) performs multiple lookups (hops) on memory and (3) end-to-end training with backpropagation. The proposed model is called End-to-end Memory Network (MemN2N).
<p align="justify">

#### Key Points

- The proposed model takes a set of inputs which are stored in the memory and a query. Both the inputs and query is transformed into a continuous representation via multiple steps (hops) to provide an output.
- Each input has a corresponding output vector which is simply computed using an embedding matrix. The response vector from the memory is the a sum over the transformed inputs (output vectors), weighted by the probability vector from the input.
- To produce the predicted label, sum of the output vector and the input embedding is then passed through a final weight matrix and a softmax function.
- Unlike previous work [[Weston et. al, 2015]](https://arxiv.org/pdf/1410.3916.pdf), proposed MemN2N model doesn't require explicit supervision of attention during training rather it only requires supervision on the final output.

#### Notes

<p align="justify">
They used two different representations for sentences, 1. bag-of-words (BoW) representation and 2. position encoding (PE) which takes the order of the words into consideration. In their training, they set learning rate to 0.01 with anneals every 25 epochs by half of the current rate untill 100 epochs eached. They didn't use any momentum or weight decay. All the weight parameters are initialized randomly from a Gaussian distribution. All training used a batch size of 32. The capacity of memory was restricted to the most recent 50 sentences.
<p align="justify">

**Expermental Dataset**: [bAbI dataset](https://research.fb.com/downloads/babi/), [Text8 dataset](http://mattmahoney.net/dc/textdata.html), [Penn TreeBank dataset](https://catalog.ldc.upenn.edu/ldc99t42)

**More details on this work**: [Official Implementation](https://github.com/facebook/MemNN), [Slides from Authors](https://pdfs.semanticscholar.org/10eb/d5c40277ecba4ed45d3dc12f9f1226720523.pdf)

**Bibliography**
```
@inproceedings{sukhbaatar2015end,
  title={End-to-end memory networks},
  author={Sukhbaatar, Sainbayar and Weston, Jason and Fergus, Rob and others},
  booktitle={Advances in neural information processing systems},
  pages={2440--2448},
  year={2015}
}
```
