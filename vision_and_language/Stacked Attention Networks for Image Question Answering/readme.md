## [Stacked Attention Networks for Image Question Answering](http://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Yang_Stacked_Attention_Networks_CVPR_2016_paper.pdf)

<p align="justify">
In this work, a stacked attention networks (SANs) is presented that learns to answer natural language questions from images through multi-step reasoning. SANs use semantic representation of a question as query to search for the regions in an image that are related to the answer. In SANs, they query an image multiple times through multiple-layer SAN to infer the answer progressively. SAN consists of three major compoenents: (1) the image model, (2) the question model and (3) the stacked attention model.
<p align="justify">

#### Key Points

- The image model uses VGGNet to extract image features. Features are chosen from the last pooling layer (512 X 14 X 14).
- In the questio model, they used CNN or a LSTM to extract a semantic vector of the question. In most cases, they found CNN-based question model performs better.
- In the stacked attention model, the attention distribution over all extracted image regions are computed first and then weighted sum of the image vectors are combined with question vector to form the query vector. Finally the query is used to predict the answer using softmax probabilities. Also, they put multi-step reasoning through stacked attention layers where the model iterates the query-attention process multiple times.

#### Notes

<p align="justify"> 
For DAQUAR and COCO-QA, they set the word embedding dimension and LSTM’s dimension to be 500 in the question model. For the CNN based question model, they set the unigram, bigram and trigram convolution filter size to be 128, 256, 256 respectively. In evaluation, they experiment with SAN with one and two attention layers. They found that using three or more attention layers does not further improve the performance. In their experiments, all the models are trained using stochastic gradient descent with momentum 0.9. The batch size was fixed to be 100. The best learning rate is picked using grid search. Gradient clipping technique and dropout were used too.
<p align="justify">

**Expermental Dataset**: [Full DAQUAR and Reduced DAQUAR dataset](https://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/), [COCO-QA dataset](http://www.cs.toronto.edu/~mren/imageqa/data/cocoqa/), [VQA (v1)](http://visualqa.org/vqa_v1_download.html)

**More details on this work**: [Official Implementation in Theano](https://github.com/zcyang/imageqa-san), [Author's Presentation](https://www.youtube.com/watch?v=nlcvZZWhoL8&t=14s)

**Bibliography**
```
@inproceedings{yang2016stacked,
  title={Stacked attention networks for image question answering},
  author={Yang, Zichao and He, Xiaodong and Gao, Jianfeng and Deng, Li and Smola, Alex},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={21--29},
  year={2016}
}
```
