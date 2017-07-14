## [Segmentation from Natural Language Expressions](https://arxiv.org/pdf/1603.06180.pdf)

<p align="justify">
In this paper, authors addressed the following problem: given an image and a natural language expression that describes a certain part of the image, authors want to segment the corresponding region(s) that covers the visual entities described by the expression. Authors proposed an end-to-end trainable recurrent and convolutional network model that jointly learns to process visual and linguistic information. In the proposed model, the referential expression is encoded into a fixed-length vector representation through a recurrent LSTM network, and a convolutional network is used to extract a spatial feature map from the image. The encoded expression and the feature map are then processed by a multi-layer classifier network in a fully convolutional manner to produce a coarse response map, which is upsampled with deconvolution to obtain a pixel-level segmentation mask of the target image region. The proposed network architecture is shown below.
<p align="justify">

<p align="center">
  <br/>
  <img src="http://ronghanghu.com/wp-content/uploads/text_objseg_method-1024x442.jpg" width="600"/>
  <br/><br/>
  Figure. Proposed model for segmentation from natural language expressions
<p align="center">

#### Key Points

- In the implementation, they adopted the VGG-16 architecture as their fully convolutional network by treating fc6, fc7 and fc8 as convolutional layers, which outputs 1000 dimensional local descriptors. They applied L2-normalization to the local descriptors at that position in order to obtain a more robust feature representation.
- To encode natural language expression that describes an image region, they first embed each word into a vector through a word embedding matrix, and then used a recurrent LSTM network to encode the word sequence.
- A fully convolutional classifier is used to determine if the local image descriptors match the encoded expressions. The proposed end-to-end model is trained using the average over per-pixel weighted logistic regression loss.
- In their experiments, they use a two-stage training strategy: they first train a low resolution version of the model, and then fine-tune from it to obtain the final high resolution model. For evaluation, they used: overall intersection-over-union (overall IoU) metric and the precision metric.

#### Notes

<p align="justify">
The parameters in feature map extraction network are initialized from a VGG-16 network pretrained on the 1000-class ILSVRC classification task, the deconvolution filter for upsampling is initialized from bilinear interpolation. All the parameters in the proposed model, including the word embedding matrix, the LSTM parameters and the classifier parameters, are randomly initialized. The whole network is trained with standard back-propagation using SGD with momentum.
<p align="justify">

**Expermental Dataset**: [ReferIt dataset](http://tamaraberg.com/referitgame/)

**More details on this work**: [Official Implementation in Tensorflow](https://github.com/ronghanghu/text_objseg), [Caffe Implementation](https://github.com/Seth-Park/text_objseg_caffe), 
[Project Page](http://ronghanghu.com/text_objseg/), [Poster](http://www.eccv2016.org/files/posters/S-1A-07.pdf)

**Bibliography**
```
@inproceedings{hu2016segmentation,
  title={Segmentation from natural language expressions},
  author={Hu, Ronghang and Rohrbach, Marcus and Darrell, Trevor},
  booktitle={European Conference on Computer Vision},
  pages={108--124},
  year={2016},
  organization={Springer}
}
```
