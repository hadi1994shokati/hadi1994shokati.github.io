---
layout: page
title: Erosion-SAM
description: Semantic segmentation of soil erosion by water
img: assets/img/Erosion-SAM.png
importance: 1
category: work
related_publications: true
---

The **Erosion-SAM** project presents an automated approach for semantic segmentation of soil erosion features caused by water in agricultural landscapes. Published in **CATENA** (2025), this work demonstrates how fine-tuning the Segment Anything Model (SAM) enables accurate detection of erosion and deposition features from high-resolution aerial imagery.

{% cite shokati2025erosionsam %}

## Overview

Soil erosion by water poses significant challenges in agricultural landscapes. Traditional detection methods rely on manual field surveys or visual interpretation of aerial imagery—processes that are time-consuming and subjective. This project leverages the **<a href="https://segment-anything.com/" target="_blank">Segment Anything Model (SAM)</a>**, a foundation model pre-trained on over 1 billion masks, and fine-tunes it for the specialized task of identifying soil erosion features.

## Study Area and Dataset

**Location**: Southeastern Bavaria, Germany

**Data Acquisition**:
- **Period**: May to September, 2011 and 2012
- **Resolution**: 0.2 m aerial orthophotos
- **Trigger**: RADOLAN rainfall data (1 × 1 km²) to identify erosive events (≥10 mm total rainfall or ≥10 mm/h max 30-min intensity)
- **Timing**: Aerial surveys within 30 days after erosive events

**Dataset**: 405 manually annotated images showing:
- Ephemeral gullies, rills, sediment fans, and sheet erosion
- Land cover categories:
  - Grassland: 128 images
  - Cropland: 277 images (vegetated: 131, bare: 146)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Erosion-SAM1.png" title="Study area and dataset examples" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A) Soil erosion map of Germany in a 75 × 75 m raster and B) examples of manual segmentation of agricultural fields with erosive rainfall, showing erosion and deposition features across different land covers.
</div>

## Methodology

We applied **fine-tuning** to adapt SAM's pre-trained weights to soil erosion detection. Fine-tuning is a transfer learning approach that modifies a pre-trained model for a specific task, improving performance while reducing the need for large labeled datasets and computational resources.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Erosion-SAM2.png" title="SAM architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overview of the Segment Anything Model (SAM) architecture. The fine-tuning process adapts the model to soil erosion detection.
</div>

**Data Processing**:
- Large orthophotos divided into 256×256 pixel patches (step size: 256, no overlap)
- Empty masks filtered out
- Data split: 70% training, 15% validation, 15% testing

**Model Configuration**:
- Base: SAM (vit_b variant)
- Optimizer: AdamW
- Loss: Combined Dice loss and focal loss
- Strategy: Fine-tuning the mask decoder

## Results

The fine-tuned Erosion-SAM model successfully detected soil erosion features across different land cover types. The model showed strong segmentation performance with accurate delineation of erosion features such as rills and gullies, successful detection of deposition zones (sediment fans), and robust generalization to different field conditions.

### Segmentation Examples

<!-- Add your segmentation result figures here when available -->
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Erosion-SAM-results1.png" title="Segmentation results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Examples of erosion feature segmentation by Erosion-SAM showing original images, ground truth, and model predictions.
</div>

The model demonstrated effective performance across varying conditions including different lighting, vegetation cover, and agricultural field types.

## Applications

- **Precision Agriculture**: Automated erosion monitoring for farm management
- **Environmental Monitoring**: Large-scale erosion assessment
- **Soil Conservation**: Rapid identification of erosion hotspots
- **Research**: Large-scale erosion studies

## Publication

**Citation:**
> Shokati, H., Engelhardt, A., Seufferheld, K., Taghizadeh, R., Fiener, P., Lensch, H., & Scholten, T. (2025). Erosion-SAM: Semantic segmentation of soil erosion by water. *CATENA*, 254, 108954.

**DOI**: <a href="https://doi.org/10.1016/j.catena.2025.108954" target="_blank">10.1016/j.catena.2025.108954</a>
