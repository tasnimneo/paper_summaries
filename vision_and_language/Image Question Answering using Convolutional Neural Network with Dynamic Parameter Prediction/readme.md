## [Image Question Answering using Convolutional Neural Network with Dynamic Parameter Prediction](http://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Noh_Image_Question_Answering_CVPR_2016_paper.pdf)

<p align="justify">
In this paper, authors addressed the image question answering problem through a convolutional neural network with a dynamic parameter layer whose weights are determined adaptively based on questions. For the adaptive parameter prediction, they employed a separate parameter prediction network which consists of gated recurrent unit (GRU) taking a question as its input and a fully-connected layer generating a set of candidate weights as its output. The proposed network architecture is shown below.
<p align="justify">

<p align="center">
  <br/>
  <img src="http://cvlab.postech.ac.kr/research/dppnet/images/figure2.png"/>
  <br/><br/>
  Figure. Overall architecture of the proposed Dynamic Parameter Prediction network (DPPnet)
<p align="center">

#### Key Points

- The proposed network composed of two sub-networks: classification network and parameter prediction network. The classification network is constructed based on VGG16-layer net. They removed the last layer in the network and attached three fully-connected layers.
- The second last fully-connected layer in the classification network is the dynamic parameter layer, and the weights in the layer are determined adaptively by the parameter prediction network. The last fully-connected layer is the classification layer whose output dimensionality is equal to the number of possible answers.
- The parameter prediction network has GRU cells and a fully-connected layer. It takes a question as its input, and generates a real valued vector, which corresponds to candidate weights for the dynamic parameter layer in the classification network.
- Given an image and a question, the proposed model estimates the weights in the dynamic parameter layer through hashing (reduces the number of parameters) with the candidate weights obtained from the parameter prediction network. 
- They fine-tuned GRU pre-trained on a large-scale text corpus to improve generalization performance in obtaining representations for questions. They initialized the GRU with the skipthought vector model trained on a book-collection corpus containing more than 74M sentences.
- For hashing, they employed recently proposed random weight sharing technique [<a href="http://www.jmlr.org/proceedings/papers/v37/chenc15.pdf">Compressing neural networks with the hashing trick</a>]. Specifically, a single parameter in the candidate weight vector is shared by multiple elements of the weight matrix which is done by applying a predefined hash function that converts the 2d location in the matrix to the 1d index in the weight vector.

#### Notes

<p align="justify">
The proposed network — joint network with the CNN for ImageQA and the parameter prediction network is trained end-to-end through back-propagation, where its weights are initialized using a pre-trained CNN and GRU. Adam is used for optimization with initial learning rate 0.01. They clipped the gradient to 0.1 and stopped training when there is no progress on validation accuracy for 5 epochs. They used batch-normalization to the output activations of the dynamic parameter layer to avoid the change of distribution in the outputs.
<p align="justify">

**Expermental Dataset**: [DAQUAR-ALL dataset](https://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/),
[COCO QA dataset](http://mscoco.org/), [VQA dataset](http://visualqa.org/index.html)

**More details on this work**: [Project Page](http://cvlab.postech.ac.kr/research/dppnet/), [Official Implementation](https://github.com/HyeonwooNoh/DPPnet)

**Bibliography**
```
@inproceedings{noh2016image,
  title={Image question answering using convolutional neural network with dynamic parameter prediction},
  author={Noh, Hyeonwoo and Hongsuck Seo, Paul and Han, Bohyung},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={30--38},
  year={2016}
}
```
