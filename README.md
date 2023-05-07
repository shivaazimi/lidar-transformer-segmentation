# Semantic Segmentation of 3D Point clouds using Transformer 

This project explores the application of self-attention networks to 3D point cloud processing with the focus on semantic segmentation task.The model is evaluated on the SemanticKitti dataset.


## Table of Contents

- [Description](#description)
  - [Dataset Preparation](#subheader-name)



## Description <a name="description"></a>

### Dataset Preparation <a name="dataset_preparation"></a>

- Download Semantic-KITTI [dataset](http://semantic-kitti.org/dataset.html) and symlink the paths to them as follows:

  ```sh
   mkdir -p dataset
   ln -s /path_to_s3dis_dataset dataset/s3dis
   ```
