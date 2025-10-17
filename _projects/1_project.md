---
layout: page
title: Erosion-SAM
description: Semantic segmentation of soil erosion by water
img: assets/img/Erosion-SAM.png
importance: 1
category: work
related_publications: true
---

<style>
  p {
    text-align: justify;
    text-justify: inter-word;
  }
</style>

The **Erosion-SAM** project presents an automated approach for semantic segmentation of soil erosion features caused by water in agricultural landscapes. This work demonstrates how fine-tuning the Segment Anything Model (SAM) enables accurate detection of erosion and deposition features from high-resolution aerial imagery.



<br>

### Overview

Soil erosion by water poses significant challenges in agricultural landscapes. Traditional detection methods rely on manual field surveys or visual interpretation of aerial imagery—processes that are time-consuming and subjective. This project leverages the **<a href="https://segment-anything.com/" target="_blank">Segment Anything Model (SAM)</a>**, a foundation model pre-trained on over 1 billion masks, and fine-tunes it for the specialized task of identifying soil erosion features.

<br>

### Study Area and Dataset

**Location**: Southeastern Bavaria, Germany

**Data Acquisition**:
The project involved acquiring orthophotos following heavy rainfall events in erosion-prone areas **between May and September of 2011 and 2012**. To determine suitable acquisition times, **RADOLAN rainfall data**, with a spatial resolution of **1 × 1 km²**, were analyzed. When rainfall events met specific thresholds (either a total rainfall of at least 10 mm or a maximum 30-minute intensity exceeding 10 mm/h) indicating high erosion potential, aerial surveys were conducted using a small aircraft within 30 days after the identified erosive event.

**Dataset**: 
The images were then georeferenced. We manually identified and masked **405 individual images** from the aerial imagery that exhibited erosion and deposition features such as ephemeral gullies, rills and sediment fans. The fields were categorized into 3 land cover categories:
  - Grassland: 128 images
  - Cropland: 277 images (vegetated: 131, bare: 146)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Erosion-SAM1.png" title="Study area and dataset examples" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A) Soil erosion map of Germany and B) examples of manual segmentation of agricultural fields with erosive rainfall, showing erosion and deposition features across different land covers.
</div>

<br>

### Methodology

We applied **fine-tuning** to adapt SAM's pre-trained weights to soil erosion detection. Fine-tuning is a transfer learning approach that modifies a pre-trained model for a specific task, improving performance while reducing the need for large labeled datasets and computational resources.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Erosion-SAM2.png" title="SAM architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overview of the Segment Anything Model (SAM) architecture. The fine-tuning process adapts the model to soil erosion detection.
</div>

<br>

**Data Processing**:
- Large orthophotos divided into 256×256 pixel patches
- Empty masks filtered out
- Data split: 70% training, 15% validation, 15% testing

<br>

**Model Configuration**:
- Base: SAM (vit_b variant)
- Optimizer: AdamW
- Loss: Combined Dice loss and focal loss
- Strategy: Fine-tuning the mask decoder

<br>

### Results

The fine-tuned Erosion-SAM model successfully detected soil erosion features across different land cover types. We evaluated multiple fine-tuning approaches and compared them against the original SAM model.

<br>

#### Performance Metrics

The table below shows the performance of different approaches across land cover types. The numbers in **<span style="color: #3498db;">blue</span>** and **<span style="color: #e67e22;">orange</span>** represent the increase and decrease in performance compared to the original SAM baseline.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Erosion-SAM-table.png" title="Performance metrics comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Performance comparison of different fine-tuning approaches (Cropping, Resizing without prompt, Resizing with prompt) against the original SAM baseline across different land cover types. 
</div>

The **Resizing approach with prompt** demonstrated the best overall performance with substantial improvements across all metrics and land cover types, particularly excelling in grassland detection (IoU: 0.75, +0.38 improvement).

<br>

#### Segmentation Examples

<!-- Add your segmentation result figures here when available -->
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Erosion-SAM-results1.png" title="Segmentation results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Examples of erosion feature segmentation by Erosion-SAM showing original images, ground truth, and model predictions.
</div>


<br>


### Applications
The generated data sets can be applied to machine learning-based SE modeling, providing accurate and consistent training data across different land cover types, and offering a reliable alternative to traditional SE models. In addition, erosion-SAM can make a valuable contribution to the precise monitoring of SE with high temporal resolution over large areas, and its results could benefit reinsurance and insurance-related risk solutions.

<br>


### Publication

**Citation:**
> Shokati, H., Engelhardt, A., Seufferheld, K., Taghizadeh, R., Fiener, P., Lensch, H., & Scholten, T. (2025). Erosion-SAM: Semantic segmentation of soil erosion by water. *CATENA*, 254, 108954.

**DOI**: <a href="https://doi.org/10.1016/j.catena.2025.108954" target="_blank">10.1016/j.catena.2025.108954</a>

<br>

**Status**: Published in CATENA
{% cite shokati2025erosionsam %}