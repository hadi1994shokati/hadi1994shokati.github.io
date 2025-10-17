---
layout: page
title: Land Suitability
description: Ensemble MCDM and machine learning approaches for agricultural land assessment
img: assets/img/wheat-suitability.png
importance: 6
category: work
related_publications: true
---

<style>
  p {
    text-align: justify;
    text-justify: inter-word;
  }
</style>

This project integrates advanced multi-criteria decision-making (MCDM) techniques with machine learning to assess land suitability for wheat cultivation, providing actionable insights for sustainable agricultural planning and food security.

<br>

### Overview

Land suitability assessment is critical for modern agriculture, involving the evaluation of soil properties, climate, topography, hydrology, and socio-economic factors. This study provides a comprehensive framework for determining optimal land use for wheat cultivation. By combining multiple MCDM approaches with Random Forest machine learning, we offer a robust methodology for agricultural decision-making that balances productivity and environmental sustainability.

<br>

### Research Objectives

This study aims to:

1. **Determine land suitability** for wheat cultivation in western Iran by integrating MCDM and machine learning methods
2. **Compare advanced MCDM techniques** including TOPSIS, GRA, and SAW for land evaluation
3. **Identify the most important factors** influencing wheat cultivation suitability in the study area
4. **Develop spatial prediction models** using Random Forest and digital soil mapping techniques

<br>

### Methodology

#### Study Area

The Gavshan region (5,341 hectares) in western Iran.


<br>

#### Data Collection

**Soil Sampling and Analysis**:
- 70 soil profiles selected using stratified random sampling based on geomorphology
- Analysis of 10 soil properties and wheat yield measurements
- Laboratory analysis: organic carbon (OC), pH, electrical conductivity (EC), cation exchange capacity (CEC), calcium carbonate equivalent (CCE), particle size distribution, available phosphorus and potassium

**Field Data Collection**:
- Wheat yield sampling from 1 m² plots at each profile location
- Harvest date: August 23, 2019
- Uniform management practices across the study area

<br>

#### Multi-Criteria Decision Making (MCDM) Methods

Three advanced MCDM techniques were employed:

**1. TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)**:

**2. GRA (Gray Relational Analysis)**:

**3. SAW (Simple Additive Weighting)**:


**Attribute Weighting**:
- Shannon's entropy method used to determine objective weights
- Reduces subjective influence of decision-makers
- Accounts for information content and uncertainty in data

<br>

#### Machine Learning Modeling

**Random Forest (RF) Algorithm**:
- Ensemble learning for spatial prediction of land suitability values
- Environmental covariates from multiple sources:
  - Terrain features from 10 m digital elevation model (slope, LS factor, topographic wetness, aspect, curvature)
  - Landsat 8 OLI spectral bands and vegetation indices (30 m resolution)
  - Geomorphological map (categorical data)


<br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/wheat-methodology.jpg" title="Methodological Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comprehensive methodological framework showing the integration of field sampling, soil analysis, MCDM techniques, and machine learning modeling for land suitability assessment.
</div>

<br>

### Key Findings

#### Critical Factors for Wheat Cultivation

Shannon's entropy weighting revealed the most important attributes:

1. **Slope** (0.439 weight): Strongest influence on wheat suitability


2. **Organic Carbon (OC)** (0.135 weight): Key soil fertility indicator


3. **Cation Exchange Capacity (CEC)** (0.108 weight): Critical for nutrient dynamics


**Other factors** (in order of importance):
- Calcium carbonate equivalent (CCE): 0.090
- Electrical conductivity (EC): 0.086
- Gravel content: 0.077
- Soil thickness: 0.054
- Soil texture: 0.010

<br>


**Key Observations**:
- TOPSIS and GRA methods showed stronger correlation with wheat yield than SAW
- TOPSIS efficiently determined land suitability across most study areas
- SAW method, while simple, did not capture differences in land suitability as effectively

<br>

#### Random Forest Spatial Modeling

RF algorithm successfully mapped land suitability with high accuracy:

| Method | RMSE | MAE | R² |
|--------|-----|------|-----|
| **SAW** | **0.061** | **0.003** | **0.88** |
| **GRA** | **0.072** | **0.005** | **0.83** |
| **TOPSIS** | **0.081** | **0.017** | **0.80** |



<br>

### Spatial Distribution of Suitability

**Good Suitability Areas** (central region):
- Characteristics: Slope < 5%, yield > 1.4 t/ha, CEC > 15 cmol+/kg, OC > 1%
- Coverage: 33% (TOPSIS), 20% (GRA), 6% (SAW)
- Geomorphological units: Pi111, Pi211, Pl111

**Moderate Suitability Areas** (central, southern, eastern regions):
- Characteristics: Slope 5-10%, yield 1-1.4 t/ha, CEC 10-15 cmol+/kg, OC 0.5-1%
- Coverage: 16% (TOPSIS), 22% (GRA), 29% (SAW)
- Geomorphological units: Pi121, Pi212, Pl211

**Poor Suitability Areas**:
- High slope areas (>10%)
- Low OC and CEC values
- Predominantly in hilly and mountainous terrain

<br>

### Spatial Autocorrelation Analysis

Analysis confirmed the importance of key factors:

**Slope**: Strong negative spatial autocorrelation with wheat yield in high-slope areas (Hi111, Hi121, Hi131, Hi211, Mo111, Mo121)

**OC and CEC**: Positive spatial autocorrelation with yield in areas with high organic carbon and cation exchange capacity

**MCDM Methods**: Positive spatial autocorrelation with yields across the study area, with TOPSIS showing the strongest correlation


<br>

### Practical Applications

Agricultural Planning
Sustainable Land Management

Policy and Decision Support


<br>



{% cite nabiollahi2024landsuitability %}
