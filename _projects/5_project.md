---
layout: page
title: Soil Moisture
description: Comparing UAV hyperspectral and satellite multispectral approaches
img: assets/img/soil-moisture-uav.png
importance: 5
category: work
related_publications: true
---

<style>
  p {
    text-align: justify;
    text-justify: inter-word;
  }
</style>

This project provides a comprehensive comparison of UAV-based hyperspectral and satellite-based multispectral data for soil moisture estimation using machine learning techniques, offering insights into the optimal remote sensing approach for precision agriculture.

<br>

### Overview

Soil moisture is a critical variable in agriculture, hydrology, and environmental monitoring. Accurate soil moisture estimation enables optimized irrigation management, improved crop yield predictions, and better understanding of hydrological processes. Remote sensing offers a non-destructive, spatially-explicit approach to soil moisture monitoring, but the choice between different platforms and sensors significantly impacts accuracy and operational feasibility.

<br>

### Research Objectives

This study compares two distinct remote sensing approaches for soil moisture estimation:

1. **UAV-Based Hyperspectral Imaging**: High spatial resolution, detailed spectral information, but limited spatial coverage
2. **Satellite-Based Multispectral Imaging**: Large spatial coverage, lower spectral resolution, freely available data

The comparison aims to determine which approach provides superior soil moisture estimation accuracy and identify the optimal trade-offs between spatial resolution, spectral detail, and operational constraints.

<br>

### Methodology

#### Data Acquisition Campaign

The study involved extensive field data collection campaigns conducted over **14 different dates from September 2021 to January 2023**. This multi-temporal approach ensured capture of diverse soil moisture conditions across seasons and weather patterns.

<br>


#### Used Data

**1. Satellite Multispectral Data**:
- Sentinel-2: 10-20 m spatial resolution
- Landsat-8/9: 30 m spatial resolution

<br>

**2. UAV Hyperspectral Data Acquisition**:

The aerial data of the region were captured by mounting the **CoSpectroCam** sensor on a **DJI Matrice 100 UAV**. The CoSpectroCam is an advanced optical coaxial system that combines an RGB camera with a spectrometer, providing both high-resolution imagery and detailed spectral information.

**CoSpectroCam Specifications**:
- **RGB Camera**: 700 × 800 pixels resolution
- **Spectrometer**: High spectral resolution of 0.35 nm
- **Spectral Range**: 339.6 nm to 1028.8 nm
- **Spectral Bands**: 2048 bands covering UV to near-infrared

**Key Advantages**:
- High spatial resolution imagery
- Captures subtle variations in soil properties
- Flexible acquisition timing
- Detailed spectral information across 2048 bands

<br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/uav-equipment.jpg" title="UAV Equipment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    (a) DJI Matrice 100 UAV equipped with CoSpectroCam and RGB sensors, (b) CoSpectroCam sensor, and (c) RGB camera used for high-resolution imaging.
</div>

<br>


### Modelling

We employed **several machine learning algorithms** to establish relationships between spectral signatures and soil moisture content:


<br>

### Performance Comparison

The Taylor diagram below illustrates the comprehensive performance comparison of soil moisture estimation models developed using three different remote sensing data sources: Sentinel-2, Landsat-8/9, and UAV hyperspectral data.

<br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/taylor-diagram-soil-moisture.jpg" title="Taylor Diagram Performance Comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Taylor diagram illustrating the performance of soil moisture estimation models developed using Sentinel-2, Landsat-8/9, and UAV hyperspectral data. The diagram shows correlation, standard deviation, and root-mean-square error for each approach.
</div>

<br>

### Applications

Precision Agriculture

Hydrological Modeling

Environmental Monitoring

Research and Development



<br>

### Future Directions

- Integration of UAV and satellite data through multi-sensor fusion
- Extension to other soil properties (organic matter, texture)


<br>



{% cite shokati2025soilmoisture %}

{% cite shokati2024randomforest %}

{% cite shokati2023uavimagery %}

