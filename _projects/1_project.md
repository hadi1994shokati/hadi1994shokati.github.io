---
layout: page
title: Erosion-SAM
description: Semantic segmentation of soil erosion by water
img: assets/img/Erosion-SAM.png
importance: 1
category: work
related_publications: true
---

The **Erosion-SAM** project introduces an innovative approach for automated semantic segmentation of soil erosion features caused by water in agricultural landscapes. Published in **CATENA** (Volume 254, 2025), this work demonstrates how fine-tuning the Segment Anything Model (SAM) can achieve state-of-the-art performance in detecting erosion and deposition features from high-resolution aerial imagery.

{% cite shokati2025erosionsam %}

## Background and Motivation

Soil erosion by water is one of the most significant environmental challenges facing agricultural landscapes worldwide. Traditional methods of erosion detection rely on manual field surveys or visual interpretation of aerial imagery—both time-consuming and subjective processes. Automated detection using deep learning offers a promising solution, but requires substantial amounts of labeled training data.

This project addresses this challenge by leveraging the **<a href="https://segment-anything.com/" target="_blank">Segment Anything Model (SAM)</a>**, a foundation model pre-trained on over 1 billion masks. Through fine-tuning, we adapted SAM's powerful segmentation capabilities to the specialized task of identifying soil erosion features in agricultural fields.

## Study Area and Dataset

The study area was defined as the **southeastern region of Bavaria, Germany**, known for its susceptibility to soil erosion. The dataset acquisition followed a systematic approach:

- **Time Period**: May to September of 2011 and 2012
- **Image Resolution**: 0.2 m (high-resolution aerial orthophotos)
- **Trigger Mechanism**: **RADOLAN** rainfall data (1 × 1 km² spatial resolution) was analyzed to identify erosive rainfall events
- **Threshold Criteria**: Events with ≥10 mm total rainfall or ≥10 mm/h maximum 30-minute intensity
- **Data Collection**: Aerial surveys conducted within 30 days after identified erosive events using small aircraft

The dataset comprises **405 manually annotated images** exhibiting erosion and deposition features including:
- Ephemeral gullies
- Rills
- Sediment fans
- Sheet erosion

The images were categorized by land cover type:
- **Grassland**: 128 images
- **Cropland**: 277 images
  - Vegetated cropland: 131 images
  - Bare cropland: 146 images

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Erosion-SAM1.png" title="Study area and dataset examples" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A) Soil erosion map of Germany in a 75 × 75 m raster showing the study area in southeastern Bavaria, and B) examples of manual segmentation of agricultural fields with erosive rainfall, illustrating erosion and deposition features across different land covers (grassland, vegetated cropland, and bare cropland).
</div>

## Methodology

### Fine-Tuning SAM

The **Segment Anything Model (SAM)** represents a major breakthrough in image segmentation technology. While SAM delivers impressive zero-shot performance, its accuracy can be challenged by complex, domain-specific tasks such as detecting subtle soil erosion features. To overcome these limitations, we applied **fine-tuning**—a transfer learning approach that adapts a pre-trained model (including its architecture and weights) to a specific task rather than training a new model from scratch.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Erosion-SAM2.png" title="SAM architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overview of the Segment Anything Model (SAM) architecture, consisting of an image encoder, prompt encoder, and mask decoder. The fine-tuning process adapts the model's weights to the specific task of soil erosion detection.
</div>

**Benefits of Fine-Tuning:**
- Improves performance on specialized tasks
- Reduces the need for large labeled datasets
- Lowers computational demands compared to training from scratch
- Saves time while leveraging knowledge from pre-training
- Particularly effective when task-specific datasets are limited

### Data Preprocessing

The preprocessing pipeline involved:

1. **Image Patching**: Large orthophotos were divided into 256×256 pixel patches using a patchify approach with a step size of 256 (no overlap)
2. **Quality Control**: Empty masks and patches without erosion features were filtered out to ensure training efficiency
3. **Data Augmentation**: Applied to increase dataset diversity and model robustness
4. **Train-Val Split**: 70% training, 30% validation with stratified sampling by land cover type

### Model Training

- **Base Model**: SAM (vit_b variant)
- **Optimizer**: AdamW
- **Loss Function**: Combined Dice loss and focal loss
- **Batch Size**: Optimized for GPU memory constraints
- **Training Strategy**: Fine-tuning the mask decoder while keeping the image encoder frozen initially, then gradual unfreezing

## Results and Performance

The fine-tuned Erosion-SAM model achieved state-of-the-art performance in detecting soil erosion features across different land cover types. Key findings include:

### Quantitative Performance

The model demonstrated strong segmentation performance with metrics evaluated separately for each land cover category:

- **Overall Performance**: High accuracy across all land cover types
- **Precision and Recall**: Balanced performance indicating both accurate detection and minimal false positives
- **IoU (Intersection over Union)**: Strong overlap between predicted and ground truth masks
- **F1-Score**: Robust classification performance

### Qualitative Results

Visual inspection of model predictions revealed:
- Accurate delineation of erosion features such as rills and gullies
- Successful detection of subtle deposition zones (sediment fans)
- Robust performance across varying image conditions (lighting, vegetation cover)
- Effective generalization to different agricultural field types

### Model Comparison

Erosion-SAM was compared against:
- **Original SAM (zero-shot)**: Significant improvement after fine-tuning
- **U-Net architectures**: Competitive or superior performance with less training data
- **Other semantic segmentation models**: Better feature extraction and boundary delineation

## Key Innovations

1. **Domain Adaptation**: First application of fine-tuned SAM for soil erosion detection
2. **Multi-Scale Feature Detection**: Capable of identifying both large erosion features and subtle surface changes
3. **Transfer Learning Efficiency**: Achieved high performance with relatively limited training data
4. **Land Cover Generalization**: Robust performance across diverse agricultural environments

## Applications and Impact

**Erosion-SAM** has significant practical applications for:

- **Precision Agriculture**: Automated erosion monitoring for sustainable farm management
- **Environmental Monitoring**: Large-scale erosion assessment from aerial or satellite imagery
- **Soil Conservation Planning**: Rapid identification of erosion hotspots for targeted intervention
- **Policy and Regulation**: Objective, repeatable erosion monitoring for compliance verification
- **Research**: Facilitates large-scale erosion studies previously limited by manual interpretation

## Publication Details

**Citation:**
> Shokati, H., Engelhardt, A., Seufferheld, K., Taghizadeh, R., Fiener, P., Lensch, H., & Scholten, T. (2025). Erosion-SAM: Semantic segmentation of soil erosion by water. *CATENA*, 254, 108954.

**DOI**: <a href="https://doi.org/10.1016/j.catena.2025.108954" target="_blank">10.1016/j.catena.2025.108954</a>

**Journal**: CATENA (Elsevier) - Q1 journal in Soil Science

## Code and Resources

The implementation code and trained models are available for research purposes. The project demonstrates the potential of foundation models like SAM for specialized environmental monitoring tasks when properly fine-tuned.

## Future Directions

Ongoing and planned extensions include:
- **Temporal Analysis**: Multi-temporal erosion monitoring and change detection
- **Multi-Source Integration**: Combining aerial, UAV, and satellite imagery
- **3D Erosion Mapping**: Integration with DEMs for volumetric erosion estimation
- **Real-Time Processing**: Deployment for operational erosion monitoring systems

## Acknowledgments

This research was conducted at the **University of Tübingen** in collaboration with experts in soil science, computer vision, and geoinformatics. We acknowledge the support from the agricultural community in Bavaria for providing field access and validation data.
