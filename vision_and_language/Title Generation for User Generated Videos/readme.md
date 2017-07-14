## [Title Generation for User Generated Videos](https://arxiv.org/pdf/1608.07068.pdf)

<p align="justify">
In this paper, the proposed model combines two methods that extend state-of-the-art video captioners for automatic video title generation. First, they make video captioners highlight sensitive by priming them with a highlight detector. The proposed framework allows for jointly training a model for title generation and video highlight localization. Second, they induce high sentence diversity in video captioners, so that the generated titles are also diverse and catchy. This means that a large number of sentences might be required to learn the sentence structure of titles. Hence, They proposed a novel sentence augmentation method to train a captioner with additional sentence-only examples that come without corresponding videos.
<p align="justify">

#### Key Points

-  For video captioning, they used two state-of-the-art methods as examples, [Sequence to Sequence - Video to Text (S2VT)](http://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Venugopalan_Sequence_to_Sequence_ICCV_2015_paper.pdf) and [Describing Videos by Exploiting Temporal Structure](http://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Yao_Describing_Videos_by_ICCV_2015_paper.pdf).
- In S2VT, all video observations are sequentially encoded by RNN.
- The second state-of-the-art method proposed to use RNN to encode the partial sentences into a learned hidden representation and apply per-word soft-attention mechanism to obtain weighted average of all video observation.
- They proposed to train a highlight sensitive captioner by solving an optimization problem that involves the predicted sentence given a video.
- For sentence augmentation, they retrieve additional sentences from a large corpus. They use each training sentence
as a query and retrieve similar sentences in the corpus. They use the mean of word2vec feature of non-stop words in each sentence as the sentence-based feature. Cosine similarity is used to measure sentence-wise similarity. Among sentences with similarity above 0.75, they sample a target number of sentences.

#### Notes

<p align="justify">
They trained a bidirectional RNN highlight detector (see details) on 2000 training videos to predict the highlightness of each clip of 100 frames, since the median ground truth highlight duration is about 100 frames. This initial highlight detector achieves a 54.2% mean Average Precision (mAP) on testing videos. They compared the model's performance with other variants of their model.
<p align="justify">

**Expermental Dataset**: [Video Titles in the Wild (VTW) dataset](http://140.128.137.13:5433/UGVideo/index.html)

**More details on this work**: [Project Page](http://aliensunmin.github.io/project/video-language/index.html#VideoTitle), 
[Short Video Demonstrating the Work](https://www.youtube.com/watch?v=KCTQ0vMsyDc), [Supplementary Material](http://aliensunmin.github.io/project/video-language/VTW2016supp.pdf), [Poster](http://www.eccv2016.org/files/posters/P-1B-42.pdf)

**Relevant Work**: [Leveraging Video Descriptions to Learn Video Question Answering](http://aliensunmin.github.io/project/video-language/index.html#VideoQA)

**Bibliography**
```
@article{DBLP:journals/corr/ZengCNS16,
  author    = {Kuo{-}Hao Zeng and Tseng{-}Hung Chen and Juan Carlos Niebles and Min Sun},
  title     = {Title Generation for User Generated Videos},
  journal   = {CoRR},
  volume    = {abs/1608.07068},
  year      = {2016}
}
```
