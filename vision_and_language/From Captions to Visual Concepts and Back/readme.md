## [From Captions to Visual Concepts and Back](http://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Fang_From_Captions_to_2015_CVPR_paper.pdf)

<p align="justify">
This paper presents an approach for automatically generating image descriptions: visual detectors, language models, and multimodal similarity models learnt directly from a dataset of image captions.
<p align="justify">

#### Key Points

- They used multiple instance learning to train visual detectors for words that commonly occur in captions, including many different parts of speech such as nouns, verbs, and adjectives.
- The word detector outputs serve as conditional inputs to a maximum-entropy language model. The language model learns from a set of over 400,000 image descriptions to capture the statistics of word usage.
- Global semantics is captured by re-ranking caption candidates using sentence-level features and a deep multimodal similarity model.
- The proposed model is state-of-the-art on the official Microsoft COCO benchmark, producing a BLEU-4 score of 29.1%.
- Perplexity, BLEU and METEOR is used as evaluation metrics.

#### Notes

<p align="justify">
The proposed model was state-of-the-art on all 14 official metrics of the COCO image captioning task, and equal to or exceeding human performance on 12 out of the 14 official metrics. The model generated captions were judged by humans to be equal to or better than human-written captions 34% of the time.
<p align="justify">

**Expermental Dataset**: [MSCOCO](http://mscoco.org/), [PASCAL VOC 2008](http://host.robots.ox.ac.uk/pascal/VOC/voc2008/)

**More details on this work**: [Official Implementation in Caffe](https://github.com/s-gupta/visual-concepts)

**Bibliography**
```
@inproceedings{fang2015captions,
  title={From captions to visual concepts and back},
  author={Fang, Hao and Gupta, Saurabh and Iandola, Forrest and Srivastava, Rupesh K and Deng, Li and Doll{\'a}r, 
  Piotr and Gao, Jianfeng and He, Xiaodong and Mitchell, Margaret and Platt, John C and others},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={1473--1482},
  year={2015}
}
```
