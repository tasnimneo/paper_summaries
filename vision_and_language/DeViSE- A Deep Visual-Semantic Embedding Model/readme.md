## [DeViSE: A Deep Visual-Semantic Embedding Model](http://papers.nips.cc/paper/5204-devise-a-deep-visual-semantic-embedding-model.pdf)

<p align="justify">
In this paper, they presented a <b>De</b>ep <b>Vi</b>sual <b>S</b>emantic <b>E</b>mbedding (DeViSE) model to identify visual objects using both labeled image data as well as semantic information gleaned from unannotated text. This model leverages textual data to learn semantic relationships between image labels and explicitly maps images into a rich semantic embedding space.
<p align="justify">

#### Key Points

- Main objective - levaraing the semantic knowledge learned in the text domain, and transfer it to a model trained for visual object recognition.
- Language Model Training - Skip-gram model with hierarchical softmax layer is used for predicting adjacent terms and was trained using a 20-word window with a single pass through the corpus of 5.7 million documents (5.4 billion words) extracted from Wikipedia.
- Visual Model Training - [AlexNet](http://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf) with a softmax layer was used to train visual model using the [ILSVRC 2012 1K dataset](http://www.image-net.org/papers/imagenet_cvpr09.pdf).
- Language model and visual model are combined to generate Deep Visual-Semantic Embedding Model (DeViSE) with a loss function by considering dot-product similarity and hinge rank loss such that model produce higher similarity between visual model output and the vector representation of the correct label than visual output and other randomly chosen text terms.
- DeViSE model was trained by asynchronous stochastic gradient descent and adagrad per-parameter dynamic learning rates were utilized to keep gradients well scaled at different layers of the network.
- DeViSE matches state-of-the-art performance on the 1000-class ImageNet object recognition challenge and performed well in predicting zero-shot classes.

#### Notes

<p align="justify">
Advantage of the proposed model is in exploiting the semantic information learned by the model to make predictions about image labels which are not observed during training. The semantic knowledge learned from large and independent dataset improves zero-shot predictions achieving hit rates of up to 18% accorss of thousands of novel labels never seen by the trained visual model.
<p align="justify">

**Expermental Dataset**: [ImageNet (ILSVRC) 2012 1K](http://image-net.org/challenges/LSVRC/2012/index#data)

**Bibliography**
```
@article{parikh2016decomposable,
  title={A decomposable attention model for natural language inference},
  author={Parikh, Ankur P and T{\"a}ckstr{\"o}m, Oscar and Das, Dipanjan and Uszkoreit, Jakob},
  journal={arXiv preprint arXiv:1606.01933},
  year={2016}
}
```
