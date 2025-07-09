# A Comparative Analysis of Self-Supervised Learning: BYOL vs. Barlow Twins for Earth Observation
A comparative study of BYOL and Barlow Twins for self-supervised representation learning on the SSL4EO-S12 satellite imagery dataset.
![Header Image](link_to_your_header_image.png) <!-- Opsiyonel: Sunumdan güzel bir görsel ekleyebilirsin -->

This repository contains the official PyTorch implementation for the paper: **"A Comparative Analysis of Self-Supervised Learning Models: BYOL and Barlow Twins for Earth Observation with Sentinel Imagery"**.

This project investigates and compares the performance of two leading non-contrastive self-supervised learning (SSL) models, **Bootstrap Your Own Latent (BYOL)** and **Barlow Twins**, for pre-training on satellite imagery. We explore their data efficiency and effectiveness by pre-training on subsets of the **SSL4EO-S12 S2RGB** dataset and evaluating the learned representations on the downstream **EuroSAT** land cover classification task.

---

## Key Findings

Our key finding is a clear, data-dependent trade-off between the two models:

-   🚀 **BYOL** proves to be highly **data-efficient**, achieving strong results even with limited pre-training data.
-   🤔 **Barlow Twins** is **"data-hungry,"** failing with limited data but showing remarkable improvement and achieving state-of-the-art performance when a larger dataset is available.

| Pre-training Data | SSL Method | EuroSAT Accuracy (%) |
| :---------------- | :----------- | :------------------- |
| ~12k images | BYOL | 79.78% |
| | Barlow Twins | 53.85% |
| ~30k images | BYOL | 84.39 |
| | Barlow Twins | 77.46% |
| ~65k images | BYOL | 84.44 |
| |**Barlow Twins** | **88.78%** |

![t-SNE Visualization](tSNE_barlow_twins_65024_images.png) <!-- Buraya t-SNE görselini ekle -->
*t-SNE visualization showing the feature separability of the models.*

---

## Repository Structure
