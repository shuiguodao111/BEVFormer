# BEVFormer Cloud Deployment & Environment Isolation

This repository demonstrates the reproduction, environment isolation, and containerized deployment of the **BEVFormer** pure-vision 3D object detection model. 

## 🎯 Core Challenge Resolved
Deploying BEVFormer typically involves severe dependency hell, specifically the compilation conflicts between `MMDet3D`, `CUDA`, and low-level C++ operators. 
This project successfully locked down the exact dependency matrix (e.g., NumPy 1.19.5, MMDet3D 0.17.1) and encapsulated the entire highly-available runtime into a **12.4GB persistent Docker Image**.

## 📦 Containerized Delivery
To achieve "100% Zero-Configuration Reproduction" for the team, the environment is hosted on the AutoDL platform. 
**AutoDL Image ID for Instant Boot:** `[image-ace11b93b5]`

## 🚀 Quick Start (Inference Pipeline)

**1. Initialize Environment:**
Mount data and inject environment variables:
```bash
source init_env.sh

2. 运行单 GPU 推断评估：
Utilizing the pre-trained weights (bevformer_tiny_epoch_24.pth) on the nuScenes-mini dataset:
code
Bash
bash ./tools/dist_test.sh ./projects/configs/bevformer/bevformer_tiny.py ./checkpoints/bevformer_tiny_epoch_24.pth 1

(Note: The /data directory containing the nuScenes dataset is excluded from this repo due to size limits. Please mount it externally prior to execution.)
