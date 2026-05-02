# BEVFormer Reproduction Project - Submission Guide

Dear Professor/Reviewer,

This archive contains the core codebase, configuration files, and custom scripts for our reproduction of the BEVFormer model.

### 1. Missing Folders (Data & Weights)
To keep the submission size manageable, the `/data` directory (containing the massive nuScenes dataset) has been excluded from this archive. 
The pre-trained weights (`bevformer_tiny_epoch_24.pth`) are expected to be placed in the `/checkpoints` directory.

### 2. Environment Verification (AutoDL Image)
We have encapsulated our perfectly aligned environment (MMDet3D 0.17.1 + NumPy 1.19.5 + custom CUDA operators) into an AutoDL system image. 
If you wish to verify our code on the cloud, you can directly boot our environment using the following AutoDL Image ID: 
**[image-ace11b93b5]**

### 3. Quick Start Guide
Once the data and weights are in place, you can run our project using the following commands:
```bash
# 1. Initialize environment variables
source init_env.sh

# 2. Run single-GPU inference evaluation
bash ./tools/dist_test.sh ./projects/configs/bevformer/bevformer_tiny.py ./checkpoints/bevformer_tiny_epoch_24.pth 1