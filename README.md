# The Urban Tree Canopy Cover in South America


##
To better service South America’s urban ecosystem, we developed a semi-supervised deep learning method, which is able to learn semantic segmentation knowledge from both labeled and unlabeled images, to segment urban trees from high spatial resolution remote sensing images. The approach attains significant improvement over existing methods, especially when trained with limited labeled samples. 
Using this approach, we created 0.5 m fine-scale tree canopy products for  cities in South America. The created UTC map products of cities in South America were freely accessible at ([UTCSA](https://drive.google.com/drive/folders/1dlAOe4zDY9mYkxniSrUh8pZfQlzl12Gd?usp=drive_linkk)).

## Study area
South America is a continent located in the Western Hemisphere of the Earth, primarily in the Southern Hemisphere. It is the fourth-largest continent by area, covering approximately 17.8 million square kilometers (6.9 million square miles) and is home to a diverse range of cultures, languages, and landscapes. 
![](/figure/SouthAmerica.png)

## Methods

![](/figure/TreeSeg_Network.png)

In this study, we used the same semi-supervised learning framework to train two CNN models for urban tree and mask segmentation, respectively. 
We use [Deeplabv3+](https://github.com/VainF/DeepLabV3Plus-Pytorch) (Chen et al., 2018) as our segmentation network (b). 
A standard binary classification network was designed as the discriminator (c) in this semi-supervised adversarial learning framework.


## Results

### Urban mask segmentation results
![](/figure/urbanmask.png)

### Tree segmentation results
![](/figure/tree.png)


### Comparison with state-of-the-art databases
![](/figure/datasets.png)


## Package pre-requisites
The code runs on Python 3 and Pytorch 0.4 The following packages are required. 

```
pip install scipy tqdm matplotlib numpy opencv-python

```

## Training preparation

Download ImageNet pretrained Resnet-101([Link](https://download.pytorch.org/models/resnet101-5d3b4d8f.pth)) and place it ```./pretrained_models/```

### Training semi-supervised Learing Framework(SSL)
```
python train.py   
```
or
```
nohup python -u train.py > ./log/out_list.log 2>&1 &
``` 
### Validation 
```
python evaluate.py
```

## Acknowledgement

Parts of the code have been adapted from: 
[DeepLab-Resnet-Pytorch](https://github.com/speedinghzl/Pytorch-Deeplab), [AdvSemiSeg](https://github.com/hfslyc/AdvSemiSeg), [PyTorch-Encoding](https://github.com/zhanghang1989/PyTorch-Encoding)


## Citation


Guo, Jianhua, et al. "Semi-supervised cloud detection in satellite images by considering the domain shift problem." Remote Sensing 14.11 (2022): 2641.

Guo, Jianhua, et al. "Nationwide urban tree canopy mapping and coverage assessment in Brazil from high-resolution remote sensing images using deep learning." ISPRS Journal of Photogrammetry and Remote Sensing 198 (2023): 1-15.

Guo, Jianhua, Zhiheng Liu, and Xiao Xiang Zhu. "Assessing the macro-scale patterns of urban tree canopy cover in Brazil using high-resolution remote sensing images." Sustainable Cities and Society 100 (2024): 105003.

Guo, Jianhua, Danfeng Hong, and Xiao Xiang Zhu. "High-resolution satellite images reveal the prevalent positive indirect impact of urbanization on urban tree canopy coverage in South America." Landscape and Urban Planning 247 (2024): 105076.

Guo, Jianhua, Danfeng Hong, and Xiao Xiang Zhu. "Continent-wide urban tree canopy fine-scale mapping and coverage assessment in South America with high-resolution satellite images." ISPRS Journal of Photogrammetry and Remote Sensing 212 (2024):251-273.



