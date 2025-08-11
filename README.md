# UFEN-SLAM  
**Paper:** *Knowledge Distillation for Feature Extraction in Underwater VSLAM (ICRA 2023)* [[ArXiv]](https://arxiv.org/abs/2303.17981) | [[IEEE]](https://ieeexplore.ieee.org/document/10161047)  

## 1. Introduction  
UFEN is an underwater feature extraction and matching network.  
We use in-air RGB-D data to generate synthetic underwater images and distil knowledge from the teacher model [SuperPoint](https://github.com/magicleap/SuperPointPretrainedNetwork). Following [GCNv2](https://github.com/jiexiong2016/GCNv2_SLAM), UFEN is integrated into the [ORB-SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3) framework to replace ORB features.  

We also introduce the **EASI** dataset, containing underwater images under various turbidities with ground truth measurements. It includes a challenging sequence, **EASI-T**, featuring the highest turbidity and dense flowing particles. [[EASI Dataset]](https://github.com/Jinghe-mel/UFEN-SLAM/tree/main/EASI%20Dataset)  

## 2. Demo  
**Tracking Loss** (ORB-SLAM3 vs UFEN-SLAM)  
![](Others/ORB_1.gif) ![](Others/UFEN_1.gif)  

**Initialization Failure** (ORB-SLAM3 vs UFEN-SLAM)  
![](Others/ORB_2.gif) ![](Others/UFEN_2.gif)  

## 3. UFEN Feature Matching Implementation  
A fast Python implementation of UFEN feature matching is available here: [[UFEN_Demo]](https://github.com/Jinghe-mel/UFEN-SLAM/tree/main/UFEN_Inference)  
- **Original weights:** [SuperPoint](https://github.com/magicleap/SuperPointPretrainedNetwork)  
- **UFEN weights:** [[Download]](https://github.com/Jinghe-mel/UFEN-SLAM/tree/main/UFEN_Demo/weights)  
  - *UFEN_v1*: retrained version from the original paper  
  - *UFEN_v2*: improved version via parameter fine-tuning  

Image pairs are sourced from the [EASI Dataset](https://github.com/Jinghe-mel/UFEN-SLAM/tree/main/EASI%20Dataset) and [real underwater videos](https://ieeexplore.ieee.org/abstract/document/8968049).  

## 4. UFEN-SLAM  
UFEN-SLAM code can be found in [UFEN_SLAM](https://github.com/Jinghe-mel/UFEN-SLAM/tree/main/UFEN_SLAM)

## Citation  
If you use the EASI dataset or UFEN, please cite:  
```
@INPROCEEDINGS{10161047,
  author={Yang, Jinghe and Gong, Mingming and Nair, Girish and Lee, Jung Hoon and Monty, Jason and Pu, Ye},
  booktitle={2023 IEEE International Conference on Robotics and Automation (ICRA)}, 
  title={Knowledge Distillation for Feature Extraction in Underwater VSLAM}, 
  year={2023},
  doi={10.1109/ICRA48891.2023.10161047}}
```
