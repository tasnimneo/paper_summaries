## [Exploring Models and Data for Image Question Answering](https://arxiv.org/pdf/1505.02074.pdf)

<p align="justify">
In this paper, authors presented a generic end-to-end QA model using visual semantic embeddings to connect a CNN and a recurrent neural net (RNN) and compared their presented model with a suite of other models. They also proposed an automatic question generation algorithm that converts the descriptive sentences to questions and provided a new QA dataset (COCO-QA) that was generated using the proposed algorithm. Finally the provided a number of baseline results on the new dataset.
<p align="justify">

#### Key Points

- Their proposed model is based on LSTM sentence model and is called the "VIS+LSTM" model. They treated the image as one word of the question. They compared their proposed model with a suite of simpler models.
  - [x] They used the last hidden layer of the VGG19 Conv Net to generate the visual embeddings.
  - [x] They experimented with different word embedding models: randomly initialized embedding, dataset-specific skip-gram embedding and general-purpose skip-gram embedding.
  - [x] To treat the image as the first word of the sentence, they used a linear transformation to map 4096 dimension image feature vectors to a 300 or 500 dimensional vector (dimension of the word embeddings).
  - [x] They also considered the image as the last word of the question and optionally add a reverse LSTM, which gets the same content but operates in a backward sequential fashion.
  - [x] The LSTM(s) outputs are fed into a softmax layer at the last timestep to generate answers.
- They pre-processed the image captions before generating questions and also done post-processing after generating the questions. They considered generating four types of questions, namely, Object questions, Number questions, Color questions and Location questions.

#### Notes

<p align="justify">
They had 4 different models, namely, (1) VIS+LSTM, (2) 2-VIS+BLSTM, (3) IMG+BOW, (4) FULL. A short description of the models are given below.
<p align="justify">

- [x] VIS+LSTM: The first model is the CNN and LSTM with a dimensionality-reduction weight matrix in the middle.
- [x] 2-VIS+BLSTM: The second model has two image feature inputs, at the start and the end of the sentence, with different learned linear transformations, and also has LSTMs going in both the forward and backward directions. Both LSTMs output to the softmax layer at the last timestep.
- [x] IMG+BOW: This simple model performs multinomial logistic regression based on the image features without dimensionality reduction (4096 dimension), and a bag-of-word (BOW) vector obtained by summing all the learned word vectors of the question.
- [x] FULL: Lastly, the “FULL” model is a simple average of the three models above.

<p align="justify">
To evaluate the effectiveness of their model, they designed few baselines, namely, (1) Guess, (2) BOW, (3) LSTM, (4) IMG, (5) IMG+PRIOR, (6) K-NN. They used WUPS score as performance metrics. They found that IMG+BOW model was very strong on both datasets. They conceded that one of the limitation of their VIS+LSTM model is the dimensionality reduction of the image fetures in which case, their model is probably losing some useful information.
<p align="justify">

**Expermental Dataset**: [Toronto COCO-QA Dataset](http://www.cs.toronto.edu/~mren/imageqa/data/cocoqa/)

**More details on this work**: [Project Webpage](http://www.cs.toronto.edu/~mren/imageqa/results/), [Source Code](https://github.com/renmengye/imageqa-public)

**Bibliography**
```
@inproceedings{ren2015exploring,
  title={Exploring models and data for image question answering},
  author={Ren, Mengye and Kiros, Ryan and Zemel, Richard},
  booktitle={Advances in Neural Information Processing Systems},
  pages={2953--2961},
  year={2015}
}
```
