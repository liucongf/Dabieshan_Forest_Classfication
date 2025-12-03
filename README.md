# Dabieshan Forest Classification using Swin Transformer_UPerNet (with U-Net Baseline)
# 基于 Swin Transformer_UPerNet 的大别山森林分类（附 U-Net 基准对比）

This repository hosts the source dataset used in our study for forest type classification in the Dabie Mountains area, supporting the manuscript titled "Integrating Swin Transformer and UPerNet for High-Resolution Forest Mapping in Support of Monitoring Ecosystem".
本仓库存放了我们研究中用于大别山地区森林类型分类的源数据集，支持题为 《集成 Swin Transformer 与 UPerNet 的高分辨率森林制图及其在生态系统监测中的应用》 的论文。

# Dabieshan Forest Classification Dataset

## 许可 (License)

- **软件/代码**：本仓库中的源代码部分，依据 [Apache License 2.0](LICENSE) 许可。
- **数据集**：本仓库中的GF-1遥感影像数据文件（`.tif` 文件）及标注数据文件（`lab_data.rar`）等**数据集内容**，依据 [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) 许可协议发布。

**Core Method / 核心方法**:
- **Primary Model (Swin Transformer_UPerNet)**: This is the main framework proposed and analyzed in our study for high-resolution forest semantic segmentation.
  **主要模型 (Swin Transformer_UPerNet)**：这是本研究中提出和分析的用于高分辨率森林语义分割的核心框架。
- **Baseline Model (U-Net)**: A U-Net model was implemented as a baseline for comparative performance evaluation.
  **基准模型 (U-Net)**：实现的 U-Net 模型作为性能对比的基准。


## Dataset / 数据集
This dataset comprises a set of paired training samples for forest type classification. It includes preprocessed Gaofen-1 (GF-1) satellite image patches (.tif files) and their corresponding manual annotation labels (in lab_data.rar), which cover four forest classes: coniferous forest, broadleaf forest, mixed forest, and shrubland.
本数据集包含一套用于森林类型分类的配对训练样本。其中包括预处理后的高分一号（GF-1）卫星影像块（.tif 文件）及其对应的人工标注标签（位于 lab_data.rar 中），涵盖四个森林类别：针叶林、阔叶林、混交林和灌丛。

###Data Content / 数据内容
Gaofen-1 (GF-1) Satellite Imagery (.tif files): High-resolution optical remote sensing image patches. These patches were cropped from the preprocessed Gaofen-1 (GF-1) satellite image and served as the primary input for model training and validation.
高分一号卫星影像 (.tif 文件)：高分辨率光学遥感影像块。这些影像块由预处理后的高分一影像裁剪而成，作为模型训练和验证的主要输入。

Labeled Dataset (lab_data.rar): The corresponding annotated data for the above image patches, used for supervised training of the deep learning models.
标注数据集 (lab_data.rar)：与上述影像块对应的标注数据，用于深度学习模型的监督训练。

###Note on Methodology and Code / 方法与代码说明
The complete methodological workflow from this source data to the final forest classification map involved several steps, including model training (utilizing Swin Transformer_UPerNet and a U-Net baseline) and post-processing. The implementation code for the complete methodology is described in the accompanying manuscript. This initial release (v1.1) focuses on providing the core dataset (preprocessed GF-1 image patches and their corresponding annotation labels) to ensure reproducibility.
完整方法的实现代码在论文中详述。本次初始发布 (v1.1) 侧重于提供核心数据集（GF-1影像与标注）以确保可重复性。
