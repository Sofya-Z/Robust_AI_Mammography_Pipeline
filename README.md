# End-to-End Optimization of AI Pipelines for Mammography

This repository contains the official implementation and code associated with the paper: **"End-to-End Optimization of AI Pipelines for Mammography: A Sequential Assessment from Data Filtering to Vision-Language Models."** ## 📖 Overview

Our study presents a comprehensive, sequential evaluation of automated diagnostic pipelines in medical informatics. Rather than isolating a single algorithmic step, this project provides a modular framework that optimizes the entire mammography analysis workflow. By combining Convolutional Neural Networks (CNNs) for rigorous data harmonization with cutting-edge Vision-Language Models (VLMs) like CLIP, this pipeline bridges the gap between visual anomalies and semantic clinical descriptions.

## ⚙️ Pipeline Stages

The codebase is organized to reflect the sequential steps of our proposed methodology. You can run these stages sequentially or use them as independent modules:

* **Stage 1: Data Harmonization & Filtering (`/src/filtering/`)**
    * Preprocessing scripts designed to standardize heterogeneous medical images (resolution alignment, contrast, and brightness normalization).
    * CNN-based filtering algorithms that automatically detect and remove scans with artifacts, severe noise, or incorrect positioning, ensuring only high-quality data enters the pipeline.
* **Stage 2: Augmentations (`/src/augmentations/`)**
    * Implementation of targeted data augmentation techniques to enhance model robustness and prevent overfitting.
    * Scripts covering both spatial transformations (rotations, reflections, scaling) and medical-specific distortions (sharpness adjustment, synthetic noise, exposure simulation) to handle variations across different mammography machines.
* **Stage 3: EfficientNet Comparison (`/src/efficientnet_compare/`)**
    * Comparative analysis framework for different architectures within the EfficientNet family (e.g., from B0 to larger variants).
    * Evaluation scripts aimed at finding the optimal balance between diagnostic accuracy (sensitivity/specificity in detecting anomalies) and computational efficiency for real-world clinical deployment.
      
## 💾 Data Availability and Setup

**⚠️ Important:** Due to medical data privacy regulations and licensing restrictions, the raw mammography datasets used in this study are **not** included in this repository.

To run this pipeline, you must independently obtain access to the required datasets. 

**Steps to prepare your data:**
1.  Download the necessary mammography databases (e.g., CBIS-DDSM, INbreast, VinDr-Mammo, or state "your institutional datasets").
2.  Create a `data/` directory in the root of this project.
3.  Place the downloaded raw images and clinical metadata into `data/raw/`. 
4.  Follow the formatting guidelines detailed in `data/DATA_STRUCTURE.md` to ensure compatibility with the preprocessing scripts.

## 🚀 Quick Start

### 1. Environment Setup
We recommend using a virtual environment (e.g., Conda or Python `venv`). Clone the repository and install the required dependencies:

```bash
git clone [https://gitlab.com/your-username/mammography-ai-pipeline.git](https://gitlab.com/Sofya-Z/mammography-ai-pipeline.git)
cd mammography-ai-pipeline
pip install -r requirements.txt
```

### 2. Running
Once your environment is set up and the data is placed in the correct directory, you can execute the pipeline sequentially:

```
# Step 1: Run data harmonization and quality filtering
python run_filtering.py --config configs/filtering_config.yaml

# Step 2: Apply medical data augmentations
python run_augmentations.py --config configs/augmentations_config.yaml

# Step 3: Run EfficientNet architecture comparison and evaluation
python compare_efficientnet.py --config configs/efficientnet_config.yaml
```

## 📝 Citation
If you find this code or our research helpful in your work, please consider citing our paper:

```
@article{zimina2026mammography,
  title={End-to-End Optimization of AI Pipelines for Mammography: A Sequential Assessment from Data Filtering to Vision-Language Models},
  author={Zimina, Sofya and [Other Authors]},
  journal={Informatics},
  year={2026},
  publisher={MDPI}
}
```

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
