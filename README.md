# SSL4EO-JEPA

This project implements the Image Joint Embedding Predictive Architecture (I-JEPA) on the SSL4EO (Self-Supervised Learning for Earth Observation) dataset.

## Project Overview

SSL4EO-JEPA applies self-supervised learning techniques to Earth Observation satellite imagery using the I-JEPA architecture. This approach allows for effective feature learning without requiring labeled data, which is particularly valuable for remote sensing applications where labeled data is often scarce.

## Repository Structure

```
├── data/                         # Data folder for SSL4EO dataset
├── EDA/                          # Exploratory Data Analysis
│   ├── data_exploration.ipynb    # Notebook for data exploration
│   └── output.png                # Visualization 
├── Linear Probing/               # Linear evaluation of learned features
│   └── linear_probing.ipynb      # Linear probing 
├── SSL_training/                 # Self-supervised training code
│   └── ijepa_training.ipynb      # I-JEPA training notebook
├── visualizations/               # Training logs and visualizations
│   └── visualizations.ipynb
├── .gitignore                    # Git ignore file
└── README.md                     # This file
```

## Getting Started

### Prerequisites

- Python 3.8+
- PyTorch
- zarr
- numpy
- matplotlib
- pyyaml
- rasterio
- pandas

### Training

The self-supervised training is implemented in [SSL_training/ijepa_training.ipynb](SSL_training/ijepa_training.ipynb). This notebook contains the full training pipeline for the I-JEPA model on the SSL4EO dataset. Large parts of this pipeline are based on the original implementation of I-JEPA available as a GitHub repo at https://github.com/facebookresearch/ijepa. Since the repo has multiple folders with various files, a significant amount of work has been conducted to identify and isolate the important train pipeline parts from this codebase and restructuring them within a single notebook (necessary since kaggle only support running a jupyter notebook without having an auxiliary file system).


### Evaluation

Model evaluation through linear probing is implemented in [Linear Probing/linear_probing.ipynb](Linear%20Probing/linear_probing.ipynb). This notebook demonstrates how to evaluate the quality of the learned representations by training a linear classifier on top of the frozen features.

## Model Checkpoints

Trained model checkpoints are stored on kaggle.

JEPA trained on multi-band data: https://www.kaggle.com/models/wmarcus/jepa_small/

JEPA trained on RGB data: https://www.kaggle.com/models/wmarcus/jepa_rgb/settings 

## Data Exploration

Exploratory data analysis can be found in [EDA/data_exploration.ipynb](EDA/data_exploration.ipynb), which provides insights into the SSL4EO dataset structure and characteristics.

## License
CC BY-NC-SA 4.0


## Acknowledgments

- I-JEPA codebase https://github.com/facebookresearch/ijepa (the official repo formed the basis for this project)