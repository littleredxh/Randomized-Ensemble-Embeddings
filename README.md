## New approach for better retrieval performance with single model: Improved Embeddings with Easy Positive Triplet Mining(WACV2020)

Paper link: https://arxiv.org/abs/1904.04370

Git   link: https://github.com/littleredxh/EasyPositiveHardNegative


# Deep Randomized Ensembles for Metric Learning

This repository contains the PyTorch(1.5.0) implementation of Deep Randomized Ensembles for Metric Learning(ECCV2018)

Paper link: https://arxiv.org/abs/1808.04469 or https://www2.seas.gwu.edu/~pless/papers/DREML_ECCV2018.pdf

Prepare the training data and testing data in python dictionary format. 

For example:
```
data_dict = {'tra' : {'class_tra_01':[image path list],
                      'class_tra_02':[image path list],
                      'class_tra_03':[image path list],
                      ....,
                      'class_tra_XX':[image path list]}
                 
             'test': {'class_test_01':[image path list],
                      'class_test_02':[image path list],
                      'class_test_03':[image path list],
                      ....,
                      'class_test_XX':[image path list]}
            }
```
                 

Replace ```Data``` and ```data_dict``` in the file ```main.py```

We have the color nomarlization info for CUB, CAR, SOP, CIFAR100, In-shop cloth and PKU vehicleID data. If you want to use other dataset please add the color nomarlization value in ```_code/color_lib.py```

We also provide efficient recall@K accuracy calculation functions in ```_code/Utils.py```

```
Function for CAR,CUB and SOP dataset：recall(Fvec, imgLab, rank=None) 
Fvec:   Feature vectors, N by D torch.Tensor
imgLab: Image label, python list
rank:   k of recall@k, python list

Function for In-shop Cloth dataset： recall2(Fvec_val, Fvec_gal, imgLab_val, imgLab_gal, rank=None) 
Fvec_val:     Probe feature vectors, N_val by D torch.Tensor
Fvec_gal:     Gallary feature vectors, N_gal by D torch.Tensor
imgLab_val:   Probe image label, python list
imgLab_gal:   Gallary image label, python list
rank:         k of recall@k, python list
```

The example of calling the function is shown in  ```Recall.ipynb```

Please cite our paper, if you use these functions for recall calculation.

### Requirements
Pytorch 1.5.0

Python >3.5

### Updates
06/12/2020/: 
Upgrade to PyTorch 1.5.0 version

05/01/2019/: 

Upgrade to PyTorch 1.0.0 version

Simplified the codes structure

Fix the bug in Recall.ipynb

Add recall functions for CAR, CUB, SOP and In-shop cloth dataset

### Citation
```
@InProceedings{Xuan_2018_ECCV,
author = {Xuan, Hong and Souvenir, Richard and Pless, Robert},
title = {Deep Randomized Ensembles for Metric Learning},
booktitle = {The European Conference on Computer Vision (ECCV)},
month = {September},
year = {2018}
}
```
