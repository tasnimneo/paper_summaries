## [DenseCap: Fully Convolutional Localization Networks for Dense Captioning](http://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Johnson_DenseCap_Fully_Convolutional_CVPR_2016_paper.pdf)

<p align="justify">
Dense captioning means detecting image regions and describe them in natural language. In this paper, a network architecture is proposed for the task of dense captioning that processes an image and produce region descriptions in a single pass and can be trained end-to-end. This work combines object detection and image captioning. The proposed model is fully differentiable and can be trained jointly with the rest of the network.
<p align="justify">

#### Key Points

- Convolutional network is used to extract features from images. The localization layer internally proposes a set of candidate regions (with confidence) and produces a set of features for each regions. The region proposals which matched the ground truth are considered as postives and rests are negatives. Positive proposals have their confidence increased during training and the negative proposals have their scores pushed down.
- Then the localization layer crops out sections from the CNN feature maps corresponding to each region proposals. Instead of using RoI pooling mechanism as in case of faster R-CNN, they used bilinear interpolation (suggested in spatial transformation network) to make the proposed model fully differentiable.
- The computed feature map is passed through an MLP to compute representations corresponding to each region. These are passes (in a batch) as the first word to an LSTM (caption generator) which is trained to predict each word of the caption.
- The final architecture for dense captioning consists of a convolutional network, a localization layer, a fully connected recognition network and a recurrent neural network. The entire model trained joinly end-to-end by minimizing five loss functions. The localization layer and the recognition network has a regression loss for box position and classification loss for confidence and the recurrnet network has a captioning loss. 

#### Notes

<p align="justify">
They initialized the CNN with weights pretrained on ImageNet. Stochastic gradient descent with momentum 0.9 to train the weights of CNN and Adam to train the other components of the model. The proposed model runs in approximately 300ms on a Titan X GPU for one mini-batch and takes about 3 days of training for the model to converge. Before training, they did pre-process the dataset to improve efficiency. They used mean average precision across a range of thresholds for both localization and language accuracy.
<p align="justify">

**Expermental Dataset**: [Visual Genome (VG) region captions dataset](http://visualgenome.org/)

**More details on this work**: [Webpage](http://cs.stanford.edu/people/karpathy/densecap/), [Official Implementation in Torch](https://github.com/jcjohnson/densecap), [Authors Presentation](https://www.youtube.com/watch?v=2wRnmRSrgCo&t=7s)

**Bibliography**
```
@inproceedings{johnson2016densecap,
  title={Densecap: Fully convolutional localization networks for dense captioning},
  author={Johnson, Justin and Karpathy, Andrej and Fei-Fei, Li},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={4565--4574},
  year={2016}
}
```
