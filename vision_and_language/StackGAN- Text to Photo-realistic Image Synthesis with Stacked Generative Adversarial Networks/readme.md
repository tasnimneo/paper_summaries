## [StackGAN: Text to Photo-realistic Image Synthesis with Stacked Generative Adversarial Networks](https://arxiv.org/pdf/1612.03242.pdf)

<p align="justify">
In this paper, a stacked generative adversarial networks (Stack-GAN) to generate photo-realistic images conditioned on text descriptions. The stage-I GAN sketches the primitive shape and basic colors of the object based on the given text description, resulting in low resolution images. Stage-II GAN takes stage-I results and text descriptions as inputs, and generates high resolution images with photo realistic details. The proposed network architecture is shown below.
<p align="justify">

<p align="center">
  <img src="https://raw.githubusercontent.com/hanzhanggit/StackGAN/master/examples/framework.png" width="750"/>
<p align="center">

#### Key Points

- Stage-I GAN: it sketches the primitive shape and basic colors of the object conditioned on the given text description and draws the background layout from a random noise vector, yielding a low resolution image.
- Stage-II GAN: it corrects defects in the low resolution image and completes details of the object by reading the text description again, producing a high resolution photo-realistic image.

#### Notes

<p align="justify">
The up-sampling blocks consist of the nearest-neighbor upsampling followed by a 3 x 3 stride 1 convolution. Batch normalization and ReLU activation are applied after every convolution except the last one. Two residual blocks are used in 128 x 128 StackGAN models while four are used in 256 x 256 models. They trained D and G network of stage-I for 600 epochs by fixing stage-II GAN and then D and G network of stage-II are trained for another 600 epochs by fixing stage-I GAN. They used ADAM optimizer with batch size 64 and initial learning rate was set to 0.0002. The learning rate is decayed to 1/2 of its previous value every 100 epochs. They used inception score as evaluation metric. 
<p align="justify">

**Expermental Dataset**: [Caltech-UCSD Birds 200](http://www.vision.caltech.edu/visipedia/CUB-200.html), 
[Oxford-102 Category Flower Dataset](http://www.robots.ox.ac.uk/~vgg/data/flowers/102/)

**More details on this work**: [Official Implementation](https://github.com/hanzhanggit/StackGAN)

**Bibliography**
```
@article{zhang2016stackgan,
  title={StackGAN: Text to Photo-realistic Image Synthesis with Stacked Generative Adversarial Networks},
  author={Zhang, Han and Xu, Tao and Li, Hongsheng and Zhang, Shaoting and Huang, Xiaolei and Wang, Xiaogang and Metaxas, Dimitris},
  journal={arXiv preprint arXiv:1612.03242},
  year={2016}
}
```
