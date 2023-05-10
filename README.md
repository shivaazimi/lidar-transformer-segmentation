# Semantic Segmentation of 3D Point clouds using Transformer 

This project explores the application of self-attention networks,  which have shown impressive results in natural language processing and image analysis, to 3D point cloud processing with the focus on semantic segmentation task.The model is evaluated on the SemanticKitti dataset.
## Table of Contents

- [Description](#description)
  - [Sub Header](#subheader-name)
- [Dependencies](#dependencies)
- [Datase](#dataset)
  - [Preparation](#dataset_preparation)
  - [Specification](#dataset_description)
- [Results](#results)



## Description <a name="description"></a>
In this project, We have applied a modification of the Point Transformer model to the SemanticKitti dataset, a large-scale outdoor urban environments. By adjusting the model architecture and training on a different dataset, this project aims to improve the performance of semantic segmentation task on any large-scale outdoor urban lidar point clouds.

To provide some context, The Point Transformer paper proposed a design for self-attention layers for point clouds, and achieved state-of-the-art results across different tasks such as semantic scene segmentation, object part segmentation,and object classification.This model attained an mIoU of 70.4% on the challenging S3DIS dataset for large-scale indoor semantic scene segmentation, outperforming the strongest prior model by 3.3 absolute percentage points and crossing the 70% mIoU threshold for the first time. 
## Dataset <a name="dataset"></a>

### Preparation <a name="dataset_preparation"></a>


- Download Semantic-KITTI [dataset](http://semantic-kitti.org/dataset.html) and symlink the paths to them as follows:

  ```sh
   mkdir -p dataset
   ln -s /path_to_semantickitti_dataset dataset/semantickitti
   ```

### Specification <a name="dataset_description"></a>


## Dependencies < a name="dependencies"></a>
- PyTorch: 1.9.0
- CUDA: 11.1
- Hardware: at least 4GPUs are required to run this model.
- To set up a Conda environment, run the following command:

  ```
  bash env_setup.sh pt
  ```
## Results <a name="results"></a>

- Semanctic Segmentation on SemanticKitti

  |Model | mAcc | OA | mIoU |
  |-------| ------| ----| -------|
  |Paper| 76.5 | 90.8 | 70.4 |
  |Hengshuang's code | 76.8 | 90.4 | 70.0 |

