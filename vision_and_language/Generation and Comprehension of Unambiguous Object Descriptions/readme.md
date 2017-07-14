## [Generation and Comprehension of Unambiguous Object Descriptions](http://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Mao_Generation_and_Comprehension_CVPR_2016_paper.pdf)

<p align="justify">
In this paper, a method is proposed that can generate an unambiguous description (referring expression) of a specific object or region in an image. The proposed model can also comprehend or interpret the generated expression to infer which object is being described. In this work, a new large-scale dataset for referring expressions, based on MS-COCO is presented. The dataset is denoted as Google Refexp dataset.
<p align="justify">

#### Key Points

- Generation task - In the description generationt task, the proposed model generates a referring expression for the target object given the full image. They used RNNs to generate one word of the description at a time untill the end of sentence symbol.
- Comprehension task - In the description comprehension task, the proposed model localizes the object being referred to within the image by returning a bounding box. Particularly, they generate a set of region proposals first, and then ask the model to rank those by probability. They used the multibox method of [scalable object detection using deep neural networks] to generate object proposals.
- They used VGGNet to extract image features. They only fine-tuned the weights for the last layer of the CNN. All extracted region, image, and location/size features are fed as input into an LSTM model, which parameterizes the form of the distribution P(S|R,I) where S is a sentence, R is a region and I is an image.
- As an alternative to negative log-likelihood as objective function, they proposed an approach called Maximum Mutual Information (MMI) for training.

#### Notes

<p align="justify">
They trained their model using negative log-likelihood of the referring expressions given their respective region and image. They used stochastic gradient descent with a batch size of 16 and used an initial learning rate of 0.01 which is halved every 50,000 iterations. Gradient norms are clipped to a maximum value of 10. Regularization used to avoid overfitting through using dropout with a ratio of 0.5.
<p align="justify">

**Expermental Dataset**: [Google Refexp dataset](https://github.com/mjhucla/Google_Refexp_toolbox#manual-downloading-and-setup), [UNC-Ref-COCO dataset](https://github.com/lichengunc/refer)

**More details on this work**: [Official Implementation](https://github.com/mjhucla/Google_Refexp_toolbox)

**Bibliography**
```
@inproceedings{mao2016generation,
  title={Generation and comprehension of unambiguous object descriptions},
  author={Mao, Junhua and Huang, Jonathan and Toshev, Alexander and Camburu, Oana and Yuille, Alan L and Murphy, Kevin},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={11--20},
  year={2016}
}
```
