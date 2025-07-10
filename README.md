# A Comparative Analysis of Self-Supervised Learning: BYOL vs. Barlow Twins for Earth Observation
A comparative study of BYOL and Barlow Twins for self-supervised representation learning on the SSL4EO-S12 satellite imagery dataset.

![Header Image](results/ssl.png) 

This repository contains the official PyTorch implementation for the paper: **"A Comparative Analysis of Self-Supervised Learning Models: BYOL and Barlow Twins for Earth Observation with Sentinel Imagery"**.

This project investigates and compares the performance of two leading non-contrastive self-supervised learning (SSL) models, **Bootstrap Your Own Latent (BYOL)** and **Barlow Twins**, for pre-training on satellite imagery. We explore their data efficiency and effectiveness by pre-training on subsets of the **SSL4EO-S12 S2RGB** dataset and evaluating the learned representations on the downstream **EuroSAT** land cover classification task.

---

## Key Findings

Our key finding is a clear, data-dependent trade-off between the two models:

-   🚀 **BYOL** proves to be highly **data-efficient**, achieving strong results even with limited pre-training data.
-   🤔 **Barlow Twins** is **"data-hungry,"** failing with limited data but showing remarkable improvement and achieving state-of-the-art performance when a larger dataset is available.

| Pre-training Data | SSL Method | EuroSAT Accuracy (%) |
| :---------------- | :----------- | :------------------- |
| N/A | Scratch (ResNet18) | 72.96% |
| 12,288 images | BYOL | 79.78% |
| | Barlow Twins | 53.85% |
| 30,720 images | BYOL | 84.39 |
| | Barlow Twins | 77.46% |
| 65,024 images | BYOL | 84.44 |
| |**Barlow Twins** | **88.78%** |

![t-SNE Visualization](results/tSNE_barlow_twins_65024_images.png) 
*t-SNE visualization showing the feature separability of the models for Barlow Twins model with 65k images.*

---

## Repository Structure
The project workflow is structured across several key directories. The **Data preparation folder** includes scripts for data retrieval and notebooks containing visualizations of the raw satellite imagery. In the **Pre-trained folder**, you will find the notebooks for the self-supervised training phase, where both BYOL and Barlow Twins models were independently trained on three different data subsets (12,288 images, 30,720 images, and 61,696 images) to assess data efficiency. The **evaluation folder** holds the final stage of our experiment; here, the pre-trained models were trained and evaluated on the EuroSAT dataset (a benchmark with 27,000 images across 10 classes) using the linear probing method. Finally, the **results section** contains all generated plots, confusion matrices, and summary tables from this evaluation.
