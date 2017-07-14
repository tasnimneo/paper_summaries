## [Webly Supervised Learning of Convolutional Networks](http://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Chen_Webly_Supervised_Learning_ICCV_2015_paper.pdf)

<p align="justify">
In this paper, a model is proposed to utilize large amounts of web data to train convolutional neural networks. Main idea is based on two levels of training. At first level, easy images are used to learn an initial visual representation and at second level, initial CNN is further trained using harder, more realistic images by leveraging the structure of data and categories. Experiments are done on three different tasks, namely, <a href="http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html">Object Detection</a>, Object Localization, <a href="http://web.mit.edu/torralba/www/indoor.html">Scene Classification</a>. 
<p align="justify">

#### Key Points

- Main idea is based on curriculum learning. In curriculum learning, model is designed to learn from easy examples first and then gradually adapt itself to harder examples.
- Model learns relationship graph and initial visual representation from easy examples first and then improves via fine-tuning by backpropagating through the graph and proper regularization.
- Main model includes the learned relationship graph and the convolutional layers with a soft-max loss function.
- To clean web data and localize objects, they used four different techniques. 1. Nearest Neighbor Propagation, 2. Clustering into Subcategories, 3. EdgeBox Augmentation and 4. Category Expansion.
- Training parameters - batch size 256, learning rate 0.01 with a decay factor of 10 after every 150K iterations, training stopped after 450K iterations.
- Two networks are trained on Google: 1) The object-attribute network (GoogleO) and 2) All included network (GoogleA). For the first network, ~1.5 million images are downloaded from Google image search. Combining scene images, ~2.1 million images are used in the second network.

#### Notes

<p align="justify">
Why Webly Supervison? Training deeper neural network requires large amount of labeled data and such requirement asks for more human efforts. Therefore, if we can exploit web data for training CNNs, it would help us move from million to billion image datasets in the future. In this paper, authors showed CNNs can be trained effectively by just exploiting web data at much larger scales. Also, they demonstrated that competitive performance can be achieved in object detection without using a single label from humans. 
<p align="justify">

**Expermental Dataset**: [PASCAL VOC 2012](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html), [Indoor Scene Recognition](http://web.mit.edu/torralba/www/indoor.html)

**Bibliography**
```
@inproceedings{chen2015webly,
  title={Webly supervised learning of convolutional networks},
  author={Chen, Xinlei and Gupta, Abhinav},
  booktitle={Proceedings of the IEEE International Conference on Computer Vision},
  pages={1431--1439},
  year={2015}
}
```
