## [Dynamic Memory Networks for Visual and Textual Question Answering](http://www.jmlr.org/proceedings/papers/v48/xiong16.pdf)

<p align="justify">
In this work, they analyzed Dynamic Memory Network (DMN) [<a href="http://www.jmlr.org/proceedings/papers/v48/kumar16.pdf">Kumar et al., 2015</a>] and proposed several improvements to its memory and input modules. Specifically, they proposed a new input module which uses a two level encoder with a sentence reader and input fusion layer to allow for information flow between sentences. They also introduced a new input module to represent images and they named their model as DMN+.
<p align="justify">

#### Key Points

- Their proposed memory module includes a modified gated recurrent units where they incorporated attention gates which are computed using global knowledge over the facts.
- In DMN+, they proposed replacing the single GRU with two different components. (1) A sentence reader (a positional encoder) that transforms a sentence to an embedding. (2) The input fusion layer comprised of bi-directional GRU that allows interactions between sentences.
- To apply DMN to visual question answering, they updated input module which splits an image into small local regions and considers each region equivalent to a sentence in the input module for text. The input module for VQA is composed of three parts, (1) local region feature extraction, (2) visual feature embedding, and the (3) input fusion layer. They used VGG-19 model as local region feature extractor and a simple linear layer with tanh activation to project the local regional vectors to the textual feature space used by the question vector.
- For the episodic memory module, they have used a new attention based GRU which improved performance. They replaced the update gate in GRU with the output of the attention gate to consider the knowledge from the question or previous episode memory.
- Their proposed framework obtains state of the art results on both the VQA dataset and the bAbI-10k dataset.

#### Notes

<p align="justify">
They trained their model using the Adam optimizer with a learning rate of 0.001 and batch size of 128. They trained for 256 epochs with early stopping if the validation loss had not improved within the last 20 epochs. The model from the epoch with the lowest validation loss was then selected. Xavier initialization was used for all weights except for the word embeddings which used random uniform initialization. They used L2 regularization on all weights except bias and used dropout on the initial sentence encodings and the answer module.
<p align="justify">

**Expermental Dataset**: [bAbI dataset](https://research.fb.com/downloads/babi/), [DAQUAR-ALL dataset](https://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/), [MSCOCO VQA dataset](http://visualqa.org/index.html)

**More details on this work**: [Unofficial Implementation in Tensorflow](https://github.com/therne/dmn-tensorflow), [](), [New York Times](https://www.nytimes.com/2016/03/07/technology/taking-baby-steps-toward-software-that-reasons-like-humans.html?_r=0), [MIT Technology Review](https://www.technologyreview.com/s/600958/the-memory-trick-making-computers-seem-smarter/)

**Bibliography**
```
@article{xiong2016dynamic,
  title={Dynamic memory networks for visual and textual question answering},
  author={Xiong, Caiming and Merity, Stephen and Socher, Richard},
  journal={arXiv},
  volume={1603},
  year={2016}
}
```
