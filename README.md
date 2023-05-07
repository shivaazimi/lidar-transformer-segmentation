# Semantic Segmentation of 3D Point clouds using Transformer 

This project explores the application of self-attention networks to 3D point cloud processing with the focus on semantic segmentation task.The model is evaluated on the SemanticKitti dataset, a large-scale outdoor urban environments .


## Table of Contents

- [Description](#description)
  - [Sub Header](#subheader-name)
- [Prerequisites](#requirements)
- [Datase](#dataset)
  - [Preparation](#dataset_preparation)
  - [Description](#dataset_description)
- [Result](#results)





## Description <a name="description"></a>

## Dataset <a name="dataset"></a>

### Preparation <a name="dataset_preparation"></a>


- Download Semantic-KITTI [dataset](http://semantic-kitti.org/dataset.html) and symlink the paths to them as follows:

  ```sh
   mkdir -p dataset
   ln -s /path_to_semantickitti_dataset dataset/semantickitti
   ```

### Description <a name="dataset_description"></a>


## Prerequisites < a name="requirements"></a>
- PyTorch: 1.9.0
- CUDA: 11.1
- Hardware: at least 4GPUs are required to run this model.
- To set up a Conda environment, run the following command:

  ```
  bash env_setup.sh pt
  ```
## Result <a name="results"></a>

- Semanctic Segmentation on SemanticKitti

  |Model | mAcc | OA | mIoU |
  |-------| ------| ----| -------|
  |Paper| 76.5 | 90.8 | 70.4 |
  |Hengshuang's code | 76.8 | 90.4 | 70.0 |

