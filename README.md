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
- The model is available in `models/st_gat.py`. 
- Training functions are provided in `models/trainer.py`.
```
├── data_loader
│   ├── dataloader.py
│   └── __init__.py
├── dataset
│   ├── PeMSD7_V_228.csv
│   └── PeMSD7_W_228.csv
├── models
│   ├── __init__.py
│   ├── st_gat.py
│   └── trainer.py
├── runs
│   ├── model_final_200epochs.pt
│   └── model_final_60epochs.pt
├── utils
│   ├── __init__.py
|   └── math_utils.py
├── main.py
├── requirements.txt
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

- Semanctic Segmentation on SemanticKitti

  |Model | mAcc | OA | mIoU |
  |-------| ------| ----| -------|
  |Paper| 76.5 | 90.8 | 70.4 |
  |Hengshuang's code | 76.8 | 90.4 | 70.0 |


## References <a name="references"></a>
This project is based on the following sources:

* [POSTECH-CVLab Point Transformer codebase](https://github.com/POSTECH-CVLab/point-transformer) provided by Hengshuang Zhao
* [Point Transformer paper](http://semantic-kitti.org/dataset.html)
* [SemanticKitti dataset](http://semantic-kitti.org/dataset.html)


