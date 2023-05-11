# Semantic Segmentation of 3D Point clouds using Transformer 

This project explores the application of self-attention networks,  which have shown impressive results in natural language processing and image analysis, to 3D point cloud processing with the focus on semantic segmentation task.

## Table of Contents

- [Description](#description)
- [Dependencies](#dependencies)
- [Datase](#dataset)
  - [Preparation](#dataset_preparation)
  - [Specification](#dataset_description)
- [Results](#results)
- [References](#references)



## Description <a name="description"></a>
In this project, We have applied a modification of the Point Transformer model to the SemanticKitti dataset, a large-scale outdoor urban environments. By adjusting the model architecture and training on a different dataset, this project aims to improve the performance of semantic segmentation task on any large-scale outdoor urban lidar point clouds.

To provide some context, The Point Transformer paper proposed a design for self-attention layers for point clouds, and achieved state-of-the-art results across different tasks such as semantic scene segmentation, object part segmentation,and object classification.This model attained an mIoU of 70.4% on the challenging S3DIS dataset for large-scale indoor semantic scene segmentation, outperforming the strongest prior model by 3.3 absolute percentage points and crossing the 70% mIoU threshold for the first time. 

## Dependencies <a name="dependencies"></a>
- PyTorch: 1.9.0
- CUDA: 11.1
- Hardware: at least 4GPUs are required to run this model.
- To set up a Conda environment, run the following command:

  ```
  bash env_setup.sh pt
  ```

## Folder structure <a name="folder_structure"></a>

- Dataloading and preprocessed datasets are available in `data_loader` and `dataset`. 
- The model is available in `models/../pointtransformer_seg.py`. 
- Training functions are provided in `tool/train.py`.
```
├── config
│   └── semantickitti
│       └── semantickitti_pointtransformer_repro.yaml
├── data
│   └── semantickitti
│       └── semantickitti_names.txt
├── lib
│   └── semantickitti
│       └── semantickitti_pointtransformer_repro.yaml
│   └── __init__.py
├── model
│   └── pointtransformer
│       └── pointtransformer_seg.py
│   └── __init__.py
├── tool
│   ├── test.py
│   ├── test.sh
│   ├── train.py
|   └── train.sh
├── util
│   ├── __init__.py
│   ├── common_util.py
│   ├── config.py
│   ├── data_util.py
│   ├── semantickitti.py
│   ├── transform.py
|   └── voxelize.py
├── env_setup.sh
└── README.md
```

## Dataset <a name="dataset"></a>

The SemanticKitti dataset is a large-scale outdoor LiDAR point cloud dataset of urban environments, including city streets, sidewalks, and residential areas. Each point in the LiDAR scan is labeled with semantic segmentation information indicating the object type and ground plane, enabling the training and evaluation of deep learning models for tasks such as object detection and scene segmentation in autonomous driving applications. The dataset has become a benchmark for evaluating the performance of deep learning models on 3D point cloud data.

### Preparation <a name="dataset_preparation"></a>


- Download Semantic-KITTI [dataset](http://semantic-kitti.org/dataset.html) and symlink the paths to them as follows:

  ```sh
   mkdir -p dataset
   ln -s /path_to_semantickitti_dataset dataset/semantickitti
   ```

### Specification <a name="dataset_description"></a>

## Results <a name="results"></a>

Semanctic Segmentation on S3DIS Dataset

  |Model | mAcc | OA | mIoU |
  |-------| ------| ----| -------|
  |[Point Transformer paper](https://arxiv.org/pdf/2012.09164.pdf)  | 76.5 | 90.8 | 70.4 |
  |[Hengshuang's code ](https://github.com/POSTECH-CVLab/point-transformer)| 76.8 | 90.4 | 70.0 |
  |PointNet | 66.2 | 78.5 | 47.6 |
  |SPGraph | 73.0 | 85.5 | 62.1 |




Semanctic Segmentation on SemanticKitti Dataset

  |Model | mAcc | OA | mIoU |
  |-------| ------| ----| -------|
  |[POSTECH-CVLab Point Transformer ](https://github.com/POSTECH-CVLab/point-transformer)| 76.8 | 90.4 | 70.0 |
  |PointNet | - | - | 14.6 |
  |SPGraph | - | - | 17.4 |
  |SPLATNet | - | - | 18.4 |
  |PointNet++ | - | - |  20.1 |
  |SqueezeSeg | - | - | 29.5 |
  |SqueezeSegV2 | - | - |  39.7 |
  |TangentConv | - | - | 40.9 |
  |DarkNet21Seg | - | - | 47.4 |
  |DarkNet53Seg | - | - | 49.9 |

- The results of the PointNet and SPGraph models are added for both datasets to demonstrate that the SemanticKitti dataset is a more challenging dataset than the S3DIS dataset.

- Likewise,I a comparative analysis is conducted on the performance of our Point Transformer model against other state-of-the-art models in point cloud processing to illustrate the challenging nature of the SemanticKitti dataset. 


## References <a name="references"></a>
This project is based on the following sources:

* [POSTECH-CVLab Point Transformer codebase](https://github.com/POSTECH-CVLab/point-transformer) provided by Hengshuang Zhao
* [Point Transformer paper](https://arxiv.org/pdf/2012.09164.pdf)
* [SemanticKitti dataset](http://semantic-kitti.org/dataset.html)
* [SemanticKitti Paper](https://arxiv.org/pdf/1904.01416.pdf)



