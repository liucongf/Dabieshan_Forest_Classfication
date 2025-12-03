# Dabieshan Forest Classification using Swin Transformer_UPerNet (with U-Net Baseline)
# 基于 Swin Transformer_UPerNet 的大别山森林分类（附 U-Net 基准对比）

This repository contains the **implementation code** and **result dataset** for the forest type classification methodology described in our manuscript titled **"Integrating Swin Transformer and UPerNet for High-Resolution Forest Mapping in Support of Monitoring Ecosystem"**.

本仓库包含我们论文《**集成 Swin Transformer 与 UPerNet 的高分辨率森林制图及其在生态系统监测中的应用**》中描述的森林类型分类方法的**实现代码**与**结果数据集**。

# Dabieshan Forest Classification Dataset

## 许可 (License)

- **软件/代码**：本仓库中的源代码部分，依据 [Apache License 2.0](LICENSE) 许可。
- **数据集**：本仓库中的森林分类地图文件（`.tif` 文件）及标注数据文件（`lab_data.rar`）等**数据集内容**，依据 [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) 许可协议发布。

**Core Method / 核心方法**:
- **Primary Model (Swin Transformer_UPerNet)**: This is the main framework proposed and analyzed in our study for high-resolution forest semantic segmentation.
  **主要模型 (Swin Transformer_UPerNet)**：这是本研究中提出和分析的用于高分辨率森林语义分割的核心框架。
- **Baseline Model (U-Net)**: A U-Net model was implemented as a baseline for comparative performance evaluation.
  **基准模型 (U-Net)**：实现的 U-Net 模型作为性能对比的基准。

**Dataset / 数据集**:
The dataset includes three forest type classification maps of the Dabie Mountains area in China. It features four main classes: coniferous forest, broadleaf forest, mixed forest, and shrubland.
本数据集包含三幅中国大别山地区的森林类型分类图，主要分为四个类别：针叶林、阔叶林、混交林和灌丛。

## 🗺️ Overall Workflow / 整体工作流程
The complete process from raw imagery to the final forest map consists of the following key steps:
从原始影像到最终森林专题图的完整流程包含以下关键步骤：

1.  **Data Preprocessing & VOC Preparation**: Raw images are cropped (with geographic information preserved) and annotated to form a VOC-format dataset.
    **数据预处理与 VOC 准备**：裁剪原始图像（保留地理信息）并标注，生成 VOC 格式数据集。
2.  **Model Training**:
    **模型训练**：
    - **Primary Model (Swin Transformer_UPerNet)**: Trained using `train_swin.py`.
      **主要模型 (Swin Transformer_UPerNet)**：使用 `train_swin.py` 进行训练。
    - **Baseline Model (U-Net)**: Trained using `train_unet.py` for comparative analysis.
      **基准模型 (U-Net)**：使用 `train_unet.py` 进行训练，用于对比分析。
3.  **Model Inference & Map Generation**:
    **模型推理与专题图生成**：
    - **Prediction**: Both models are used to predict on pre-processed tiles using their respective prediction scripts.
      **预测**：使用各自的预测脚本，让两个模型对预处理后的图像块进行预测。
    - **Mosaicking & Coloring (Primary Model)**: The predicted tiles from the Swin Transformer_UPerNet model are stitched back together based on the recorded cropping boundaries (using a Gaussian-based algorithm) and then colorized according to the forest type classes. This process is integrated into `predict_and_merge.py`.
      **拼接与上色 (主要模型)**：Swin Transformer_UPerNet 模型的预测块根据记录的裁剪边界（基于高斯算法）拼接回完整的区域，并根据森林类型类别上色。此过程集成在 `predict_and_merge.py` 中。

## ⚙️ Setup & Installation / 环境设置与安装

### 1. Clone and Setup the Base Framework / 克隆并设置基础框架
**You must first set up the official `Swin-Transformer-Semantic-Segmentation` framework independently.**  
**您必须首先独立安装官方的 `Swin-Transformer-Semantic-Segmentation` 框架。**

```bash
git clone https://github.com/SwinTransformer/Swin-Transformer-Semantic-Segmentation.git
cd Swin-Transformer-Semantic-Segmentation
# Follow the official installation guide (安装依赖、编译 CUDA 算子等)
# 请严格按照其官方 README 的 Installation 部分操作: https://github.com/SwinTransformer/Swin-Transformer-Semantic-Segmentation#installation
