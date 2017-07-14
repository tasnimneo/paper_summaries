## [Generative Adversarial Text to Image Synthesis](http://www-personal.umich.edu/~reedscot/files/icml2016.pdf)

<p align="justify">
In this work, authors aimed to learn a mapping directly from words and characters to image pixels. They developed a simple GAN architectur
and training strategy that enables compelling text to image synthesis of bird and flower images from human-written descriptions. They 
trained a deep convolutional generative adversarial network (DC-GAN) conditioned on text features encoded by a hybrid character-level
convolutional recurrent neural network. The proposed network architecture is shown below.
<p align="justify">

<p align="center">
  <img src="https://camo.githubusercontent.com/1925e23b5b6e19efa60f45daa3787f1f4a098ef3/687474703a2f2f692e696d6775722e636f6d2f644e6c32486b5a2e6a7067" width="750"/>
<p align="center">

#### Key Points

- In their proposed DC-GAN architecture, both the generator and discriminator network perform feed-forward inference conditioned on the
text feature.
- In the generator G, first text query is encoded using a text encoder and then encoded representation is compressed using a fully-connected 
layer followed by a leaky RELU and then concatenated to the sampled noise vector. A normal deconvolutional network is used to generate 
a synthetic image from the text representation.
- In the discriminator D, they performed several layers of stride-2 convolution with spatial batch normalization followed by leaky RELU.
- They also proposed two variants of the GAN architecture, one is matching-aware discriminator (GAN-CLS) to separate error sources and 
the other one is Learning with manifold interpolation (GAN-INT) to generate large amount of text embeddings by simply interpolating between 
embeddings of training set captions.

#### Notes

<p align="justify">
For text features, they trained a deep convolutional recurrent text encoder on structured joint embedding of text captions with 1,024 
dimensional GoogLeNet image embeddings. Generator noise was sampled from 100-dimensional unit normal distribution. They set learning rate
to 0.0002 and used the Adam optimizer with momentum 0.5. They used a minibatch of size 64 and trained for 600 epochs.
<p align="justify">

**Expermental Dataset**: [Caltech-UCSD Birds 200](http://www.vision.caltech.edu/visipedia/CUB-200.html), 
[Oxford-102 Category Flower Dataset](http://www.robots.ox.ac.uk/~vgg/data/flowers/102/), [MSCOCO](http://mscoco.org/)

**More details on this work**: [Official Implementation](https://github.com/reedscot/icml2016), [Related Tensorflow Implementation](https://github.com/paarthneekhara/text-to-image)

**Bibliography**
```
@inproceedings{reed2016generative,
  title={Generative adversarial text to image synthesis},
  author={Reed, Scott and Akata, Zeynep and Yan, Xinchen and Logeswaran, Lajanugen and Schiele, Bernt and Lee, Honglak},
  booktitle={Proceedings of The 33rd International Conference on Machine Learning},
  volume={3},
  year={2016}
}
```
