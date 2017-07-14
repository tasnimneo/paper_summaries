## [Ask Your Neurons: A Neural-based Approach to Answering Questions about Images](http://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Malinowski_Ask_Your_Neurons_ICCV_2015_paper.pdf)

<p align="justify">
In this work, an approach based on recurrent neural networks for the challenging task of answering questions about images is proposed. The proposed model combines a CNN with a LSTM into end-to-end architecture that predict answers conditioning on a question and an image. They collected additional data to study human consensus on this task and proposed two new metrics. The also provided a variant of their proposed model that also answers question without considering any visual information.
<p align="justify">

#### Key Points

- They have treated question answering task as predicting a sequence of words from a finite vocabulary which ends with a special symbol ($) that represents the question has been fully answered. They also claimed that their algorithm learns to not predict any previously predicted words.
- Their proposed approach, namely, Neural-Image-QA is a deep network built of Convoluational Neural Network (CNN) and Long Short Term Memory (LSTM) which has been shown effective in learning a variable-length sequence-to-sequence mapping. They encode the image using a CNN model and provided it at every time step as input to the LSTM. So, the input of LSTM is a concatenation of question words' vectors and image features.
- They trained CNN models on the ImageNet dataset and in a pilot study, they found that *GoogleNet* architecture outperforms the *AlexNet* architecture as a CNN model for their task and model.
- They explored the use of a 2 layered LSTM model, but have consistently obtained worse performance.
- In order to study how much information is already contained in questions, they trained a version of their model that ignores the visual input. They named it, *"Language only"* model.
- Their experiments and consensus metrics are based on WUPS scores. They proposed two new metrics, namely, **Average Consensus** and **Min Consensus**.

#### Notes

<p align="justify">
Their model doubles the performance of the previous best approach on this problem. Their <em>"Language only"</em> models achieved 17.15% and 32.32% accuracy while the best model including vision achieved 19.43% and 34.68% accuracy on the full and reduced dataset respectively. In order to study the effects of consensus in the question answering task, they have extended the original data to an average of 5 test answers per image and question. They named this dataset as DAQUAR-Consensus. Using the DAQUAR-Consensus dataset, their model achieved 36.78% and 60.50% accuracy according average and min consensus metric.
<p align="justify">

**Expermental Dataset**: [Full DAQUAR and Reduced DAQUAR dataset](https://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/)

**More details on this work**: [Project Webpage](https://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/), [Supplementary Materials](https://www.d2.mpi-inf.mpg.de/sites/default/files/iccv15-neural_qa-supp.pdf), [Spotlight](https://www.youtube.com/watch?v=QZEwDcN8ehs), [Experiment by Huihuang Zheng](http://vision.cs.utexas.edu/381V-spring2016/slides/zheng-expt.pdf)

**Bibliography**
```
@inproceedings{malinowski2015ask,
  title={Ask your neurons: A neural-based approach to answering questions about images},
  author={Malinowski, Mateusz and Rohrbach, Marcus and Fritz, Mario},
  booktitle={Proceedings of the IEEE International Conference on Computer Vision},
  pages={1--9},
  year={2015}
}
```
