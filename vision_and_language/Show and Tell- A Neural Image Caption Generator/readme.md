## [Show and Tell: A Neural Image Caption Generator](http://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Vinyals_Show_and_Tell_2015_CVPR_paper.pdf)

<p align="justify">
In this paper, authors presented a Neural Image Caption (NIC) generation model based on a deep recurrent architecture consisting of convolutional neural network (CNN) followed by a long-short term memory (LSTM) network to generate natural sentences describing an image. CNN is used as an encoder to encode image features and LSTM is used as a decoder to decode image representation to captions.
<p align="justify">

#### Key Points

- Negative log likelihood of the correct word is used as model loss.
- For inference, they used both two different methods. One is simple **Sampling** method and the other one is using **BeamSearch**.
- Training is done through Stochastic Gradient Descent (SGD) with fixed learning rate and no momentum.
- All the weights are randomly initialized for training except the CNN weights. They used 512 dimensions for the embeddings and the size of the LSTM memory.
- BLEU-1, BLEU-4, METEOR, CIDER is used as evaluation metrics.

#### Notes

<p align="justify">
The proposed model yields BLEU-1 score of 59 comparable to human performance around 69 while previously state-of-the-art BLEU-1 score was 25 on the Pascal dataset. They also showed BLEU-1 score improvements on Flickr30k, from 56 to 66, and on SBU, from 19 to 28. They also achieved BLEU-4 score of 27.7 on the MSCOCO dataset.
<p align="justify">

**Expermental Dataset**: [MSCOCO](http://mscoco.org/), [Flickr8k](http://shannon.cs.illinois.edu/DenotationGraph/), [Flickr30k](http://shannon.cs.illinois.edu/DenotationGraph/), [PASCAL VOC 2008](http://host.robots.ox.ac.uk/pascal/VOC/voc2008/), [SBU](http://tlberg.cs.unc.edu/vicente/sbucaptions/)

**More details on this work**: [Blog](https://research.googleblog.com/2016/09/show-and-tell-image-captioning-open.html), [Implementation in Tensorflow](https://github.com/tensorflow/models/tree/master/im2txt), 

**Bibliography**
```
@inproceedings{vinyals2015show,
  title={Show and tell: A neural image caption generator},
  author={Vinyals, Oriol and Toshev, Alexander and Bengio, Samy and Erhan, Dumitru},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={3156--3164},
  year={2015}
}
```
