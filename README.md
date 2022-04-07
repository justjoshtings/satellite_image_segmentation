# Satellite Imagery Semantic Segmentation with CNN
## Project Description
Predicting land cover types on remote sensing data using Convolutional Neural Networks. Experimented with [U-Net](#unet) and [and U-Net with RestNet50 Encoder backbone](#resnet_unet) architectures to segment satellite imagery.

#### Sample Predictions
![Sample Prediction Masks](https://github.com/justjoshtings/satellite_image_segmentation/blob/main/results/sample_images/ResNet50_Val/Sample_1.png?raw=true)
## Table of Contents
1. [How to Run](#instructions)
2. [Folder Structure](#structure)
3. [Datasets](#datasets)
4. [Neural Network Architectures](#architectures)
5. [Presentation](#presentation)
6. [Report](#report)
7. [References](#references)
8. [Licensing](#license)

# <a name="instructions"></a>
## How to Run

1. Clone this repository. Navigate to desired directory and use:
```
git clone git@github.com:justjoshtings/satellite_image_segmentation.git
```
2. The Python notebook is optimized and set up for proper execution in [Google Colab](https://colab.research.google.com/). I'd recommend to upload **Land_Cover_Segmentation.ipynb** and execute from there. Please see **Folder Structure** section for how to set up the initial folder structure. The Python notebook will move and create new directories to accomodate for certain preprocessing procedures but the initial setup is shown below.
3. Download the data from the [competition](https://competitions.codalab.org/competitions/18468#learn_the_details-overview)<sup>3</sup> and upload all data into Google Drive workspace based on the prior mentioned folder structure.
4. Execute the Python notebook. Note that for training, it is recommended to connect to a GPU enabled runtime for faster training speeds.

# <a name="structure"></a>
## Folder Structure

#### Initial Google Drive Folder Setup for Google Colab:
```
satellite_image_segmentation
│    Land_Cover_Segmentation.ipynb
│
└───data
│    │   class_dict.csv
│    │   metadata.csv
│    │
│    └───test
│    │    │ 1499_sat.jpg
│    │    │ 1500_sat.jpg
│    │    │ ...
│    │
│    └───train
│    │    │ 199_sat.jpg
│    │    │ 199_mask.png
│    │    │ ...
│    │
│    └───valid
│    │    │ 1074_sat.jpg
│    │    │ 1074_sat.jpg
│    │    │ ...
```

# <a name="datasets"></a>
## Datasets

DeepGlobe Land Cover Classification Dataset from the [Competition](https://competitions.codalab.org/competitions/18468#learn_the_details-overview)<sup>3</sup>

or [Kaggle](https://www.kaggle.com/datasets/balraj98/deepglobe-land-cover-classification-dataset).


# <a name="architectures"></a>
## Neural Network Architectures

2 types of Fully Convolutional Networks<sup>4</sup> were explored with similar final results on validation and testing data.

# <a name="unet"></a>
#### U-Net Architecture

![U-Net](https://github.com/justjoshtings/satellite_image_segmentation/blob/main/results/sample_images/u_net.png?raw=true)

[Ronneberger et al. (2015)'s U-Net](https://arxiv.org/abs/1505.04597)<sup>1</sup>

# <a name="resnet_unet"></a>
#### RestNet Encoder Backbone, U-Net Decoder Architecture

![ResNet Backbone U-Net](https://github.com/justjoshtings/satellite_image_segmentation/blob/main/results/sample_images/resnet_unet.png?raw=true)
[Neven, Robby & Goedemé, Toon. (2021). A Multi-Branch U-Net for Steel Surface Defect Type and Severity Segmentation. Metals. 11. 870. 10.3390/met11060870.](https://www.researchgate.net/figure/U-Net-model-18-with-ResNet-19-backbone_fig4_351911884)<sup>2</sup>

# <a name="report"></a>
## Report
* [Medium Post](https://medium.com/@joshting/satellite-imagery-segmentation-with-convolutional-neural-networks-f9254de3b907)
* [Google Slides Presentation](https://docs.google.com/presentation/d/1do4srMWjMOXvlc0xSFbd8XvPiHDAHshhWZRLiDItgmQ/edit?usp=sharing)

# <a name="references"></a>
## References
1. [Ronneberger et al. (2015)'s U-Net](https://arxiv.org/abs/1505.04597)
2. [Neven, Robby & Goedemé, Toon. (2021). A Multi-Branch U-Net for Steel Surface Defect Type and Severity Segmentation. Metals. 11. 870. 10.3390/met11060870.](https://www.researchgate.net/figure/U-Net-model-18-with-ResNet-19-backbone_fig4_351911884)
3. [DeepGlobe Land Cover Classification Dataset from the Competiton](https://competitions.codalab.org/competitions/18468#learn_the_details-overview)
```
@InProceedings{DeepGlobe18,
 author = {Demir, Ilke and Koperski, Krzysztof and Lindenbaum, David and Pang, Guan and Huang, Jing and Basu, Saikat and Hughes, Forest and Tuia, Devis and Raskar, Ramesh},
 title = {DeepGlobe 2018: A Challenge to Parse the Earth Through Satellite Images},
 booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR) Workshops},
 month = {June},
 year = {2018}
}
```
4. [Long et al. (2015)'s Fully Convolutional Network (FCN)](https://arxiv.org/abs/1411.4038)

# <a name="license"></a>
## Licensing
* The [DeepGlobe Land Cover Classification Challenge](https://competitions.codalab.org/competitions/18468) and hence, the dataset are governed by [DeepGlobe Rules](http://deepglobe.org/docs/DeepGlobe_Rules_3_2.pdf), [The DigitalGlobe's Internal Use License Agreement](http://deepglobe.org/docs/CVPR_InternalUseLicenseAgreement_07-11-18.pdf), and [Annotation License Agreement](http://deepglobe.org/docs/Annotation%20License%20Agreement.pdf).
* MIT License

