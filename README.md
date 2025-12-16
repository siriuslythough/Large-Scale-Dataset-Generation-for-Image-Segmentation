# Large-Scale Dataset Generation for Image Segmentation

## Overview
This project focuses on **dataset engineering for vision tasks**, covering synthetic data generation, ground-truth construction, model training, and quantitative evaluation.

The objective was to build large-scale, well-structured datasets suitable for **segmentation, localization, and classification**, and to validate them using learning-based models.

## Dataset Construction
Starting from the MNIST dataset, multiple derived datasets were created:

- **Foreground segmentation dataset**
  - Foreground masks generated using Otsu thresholding
  - Original digit class labels discarded to focus on segmentation quality

- **Classification with circlization dataset**
  - Tight enclosing circles generated around digit masks
  - Images labeled by digit class and evaluated using localization-aware metrics

- **Multi-object semantic segmentation dataset**
  - Random composition of four digits into a 2×2 grid
  - Corresponding multi-label ground-truth masks generated
  - Over **250,000 unique images** created with no duplicate samples

## Model Training
- CNN models were trained **from scratch** for:
  - Foreground extraction
  - Classification with circlization
  - Semantic segmentation
- No pretrained weights were used.

## Evaluation
- **Foreground extraction & circlization:** Intersection over Union (IoU)
- **Semantic segmentation:** Dice coefficient
- Evaluation performed on held-out validation and test splits

## Implementation Details
- **Language:** Python  
- **Libraries:** NumPy, OpenCV, PyTorch  

The pipeline emphasizes **reproducibility, scale, and clean supervision**, reflecting real-world dataset preparation workflows used in scientific and medical imaging.

## Motivation
Modern vision systems are often bottlenecked by **data quality rather than model choice**.  
This project was designed to:
- explore large-scale synthetic data generation,
- understand the impact of supervision structure, and
- practice rigorous evaluation for segmentation tasks.

The workflow closely mirrors dataset preparation challenges encountered in **medical, satellite, and hyperspectral imaging domains**.

