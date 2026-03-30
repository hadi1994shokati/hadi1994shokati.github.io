---
layout: page
title: Flood Mapping
description: Using fine-tuned SAM and ResNet-backboned U-Net
img: assets/img/flood-mapping.png
importance: 4
category: work
related_publications: true
---

<style>
  p {
    text-align: justify;
    text-justify: inter-word;
  }
</style>

This project develops efficient deep learning models for rapid flood mapping from aerial imagery, enabling quick identification of flood-affected areas for emergency response and damage assessment. 



<br>

### Overview

Flooding is a major natural hazard that requires rapid response to minimize loss of life and property and to facilitate damage assessment. Aerial imagery, especially from unmanned aerial vehicles (UAVs) and helicopters, plays a crucial role in identifying flood-affected areas. This study presents two state-of-the-art segmentation approaches for automated flood mapping from aerial imagery.

<br>


### Dataset and Study Area

We used the 
**<a href="https://www.kaggle.com/datasets/faizalkarim/flood-area-segmentation" target="_blank">Flood Area Dataset</a>**
Flood Area Dataset comprising 290 images with their corresponding masks. The images were captured after some flood events in different regions using UAVs and helicopters with optical sensors.

<br>


### Methodology

We developed and compared two complementary approaches for flood segmentation:

<br>

#### Approach 1: Fine-Tuned Segment Anything Model (SAM)

Building on the success of SAM for image segmentation, we fine-tuned the model specifically for flood detection from aerial imagery. We compared two prompting strategies:

**Point Prompts**: Users click on flooded areas to guide segmentation
- More flexible and intuitive for complex flood boundaries
- Better captures irregular flood patterns
- **Performance**: Accuracy 0.96, IoU 0.90

**Bounding Box (Bbox) Prompts**: Users draw boxes around flooded regions
- Simpler input method
- Less effective when floods extend to image edges
- **Performance**: Accuracy 0.82, IoU 0.67

**Key Finding**: Point prompts significantly outperformed Bbox prompts because flood imagery often shows water extending from edge to edge, making bounding boxes less effective at capturing boundary details.

<br>

#### Approach 2: U-Net with ResNet Backbones

We implemented U-Net architectures with pre-trained ResNet backbones for feature extraction:

**U-Net + ResNet-50**:
- Standard deep architecture
- **Performance**: Accuracy 0.87, IoU 0.72

**U-Net + ResNet-101**:
- Deeper architecture for more complex feature extraction
- Better segmentation of detailed flood boundaries
- **Performance**: Accuracy 0.88, IoU 0.74

**Key Finding**: The deeper ResNet-101 backbone improved performance by extracting more complex and detailed features, enhancing U-Net's ability to segment flood-affected areas accurately.

<br>

### Results

#### Performance Comparison

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/flood-mapping-results.png" title="Performance comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Performance comparison of fine-tuned SAM (with point and Bbox prompts) and U-Net models (with ResNet-50 and ResNet-101 backbones) for flood segmentation.
</div>

**Best Overall Performance**: Fine-tuned SAM with point prompts
- Highest accuracy (0.96) and IoU (0.90)
- Most suitable for operational flood mapping
- Requires minimal user interaction

**Best Fully Automated Approach**: U-Net + ResNet-101
- No prompts required
- Good performance (Accuracy 0.88, IoU 0.74)
- Suitable for batch processing of large image datasets

<br>

#### Segmentation Examples

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/flood-segmentation-examples.png" title="Flood segmentation examples" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Examples of flood segmentation results showing original aerial imagery, ground truth, and model predictions across different flood scenarios.
</div>

<br>

### Applications

The developed models provide valuable tools for multiple stakeholders:

**Emergency Response Teams**

**Insurance Companies**

**Urban Planning and Management**

**Research and Model Development**:



<br>

### Advantages Over Traditional Methods

- **Speed**: Near real-time processing compared to hours of manual interpretation
- **Consistency**: Objective, reproducible results across different analysts
- **Scalability**: Can process large numbers of images automatically
- **Accuracy**: Surpasses manual interpretation in challenging conditions
- **Flexibility**: Adaptable to different types of aerial imagery (UAV, helicopter, satellite)

<br>



### Publication

**Citation:**
> Shokati, H., Seufferheld, K. D., Fiener, P., & Scholten, T. (2026). Rapid flood mapping from aerial imagery using fine-tuned SAM and ResNet-backboned U-Net. *Hydrology and Earth System Sciences*, 30(5), 743-756.

**DOI**: <a href="https://doi.org/10.5194/hess-30-743-2026" target="_blank">10.5194/hess-30-743-2026</a>

**Status**: Published in Hydrology and Earth System Sciences (HESS)
{% cite shokati2025floodmapping %}