## [Ask, Attend and Answer: Exploring Question-Guided Spatial Attention for Visual Question Answering](https://arxiv.org/pdf/1511.05234.pdf)

<p align="justify">
In this work, authors proposed a multi-hop memory network model with spatial attention for the VQA task. Their spatial memory network stores 
neuron activations from different spatial regions of the image in its memory and uses attention to choose regions relevant for computing 
the answer. They created a series of synthetic questions that explicitly require spatial inference to analyze the working principle of the 
proposed model.
<p align="justify">

#### Key Points

- Memory networks combine learned text embeddings with an attention mechanism and multi-step inference. In this work, they adapted an 
end-to-end memory network to solve VQA by storing the convolutional network outputs obtained from different receptive fields into the
memory, which explicitly allows spatial attention over the image.
- The question representation is used to compute attention over the visual memory, which contains extracted image features. The image 
features are embedded into the same number of dimensions as the word vectors using two different embeddings: the "attention" embedding
and the "evidence" embedding. The attention embedding generates the attention weights, while the evidence embedding maps the features
to semantic concepts.
- The embedded features are multiplied with the attention weights and summed over all image locations to generate a visual evidence 
vector which is combined with a representation of the question to predict the answer.
- As a update of their proposed model, they proposed a multi-hop process which repeats the process of gathering evidence from attended 
regions, enabling the model to update the answer based on several attention steps, or "hops" and they found that two-hop model collects 
supplementary evidence for inferring the answer.

#### Notes

<p align="justify">
They used last convolutional layer of GoogLeNet (inception_5b/output) to represent spatial CNN features. Their entire network is differentiable
and is trained using stochastic gradient descent via standard backpropagation, allowing image feature extraction, image embedding, word 
embedding and answer prediction to be jointly optimized on the training image/question/answer triples.
<p align="justify">

**Expermental Dataset**: [Reduced DAQUAR dataset](https://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/vision-and-language/visual-turing-challenge/),
[MSCOCO VQA dataset](http://visualqa.org/data/mscoco/vqa/)

**More details on this work**: [Official Implementation in Caffe](https://github.com/visionlearninggroup/ask_attend_and_answer), 
[Spotlight](https://www.youtube.com/watch?v=FjpRwVKYJQ8), [Abstract from CVPR'16 VQA Workshop](http://cs-people.bu.edu/hxu/CVPR2016_VQA_workshop.pdf)

**Bibliography**
```
@inproceedings{xu2016ask,
  title={Ask, attend and answer: Exploring question-guided spatial attention for visual question answering},
  author={Xu, Huijuan and Saenko, Kate},
  booktitle={European Conference on Computer Vision},
  pages={451--466},
  year={2016},
  organization={Springer}
}
```
