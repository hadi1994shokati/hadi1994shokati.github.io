---
layout: page
title: Soil Erosion
description: Combining physics-based and deep learning approaches
img: assets/img/erosion-modeling.png
importance: 2
category: work
related_publications: false
---

<style>
  .project p {
    text-align: justify;
    text-justify: inter-word;
  }
</style>

This **ongoing project** employs a novel hybrid modeling approach to estimate soil erosion by combining the strengths of physically-based models with the adaptive capabilities of deep learning.

<br>

### Project Overview

Soil erosion modeling traditionally relies on either physically-based models or data-driven approaches, each with their own strengths and limitations. This project bridges these two paradigms by developing a hybrid framework that leverages both methodologies for more accurate and robust soil erosion predictions.

<br>

### Methodology

#### Three-Stage Hybrid Approach

The project employs a three-stage modeling framework:

<br>

**Stage 1: Physics-Based Modeling (WaTEM/SEDEM)**

The <a href="https://www.kuleuven.be/geography/frg/modelling/erosion/watem" target="_blank">WaTEM/SEDEM</a> framework serves as the foundation for estimating soil erosion and deposition patterns. 

<br>

**Stage 2: Deep Learning Integration**

The outputs from WaTEM/SEDEM, along with additional environmental datasets, are used as inputs for a deep learning model. 

<br>

**Stage 3: Validation with Erosion-SAM**

For model validation and performance assessment, we utilize outputs from our previous [Erosion-SAM]({% link _projects/1_project.md %}) project.

<br>

### Expected Outcomes

The hybrid modeling framework is expected to provide:
- **More accurate predictions** of soil erosion patterns by combining physical understanding with data-driven learning
- **Robust estimates** that work across different landscapes and conditions
- **Improved spatial resolution** of erosion and deposition patterns
- **Transferable methodology** applicable to other regions and scales
