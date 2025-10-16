---
layout: page
title: Rainfall Erosivity Forecasting
description: Historical reconstruction and future prediction using ConvLSTM
img: assets/img/rainfall-erosivity.png
importance: 3
category: work
related_publications: false
---

<style>
  .project p {
    text-align: justify;
    text-justify: inter-word;
  }
</style>

This **ongoing project** focuses on reconstructing historical rainfall erosivity patterns and forecasting future erosion risks using deep learning and long-term precipitation data from Germany.

<br>

### Project Overview

Rainfall erosivity (a measure of the erosive power of rainfall) is a critical factor in soil erosion modeling and prediction. Understanding both historical trends and future patterns of rainfall erosivity is essential for effective soil conservation planning and climate change adaptation strategies. This project develops a comprehensive approach to extend our understanding of erosivity across nearly a century (1931–2030).

<br>

### Methodology

The project employs a three-phase approach spanning 95 years of data:

<br>

#### Phase 1: Relationship Development (2001–2025)

**Data Source**: RADOLAN high-resolution precipitation data
- **Temporal resolution**: 5-minute intervals
- **Spatial coverage**: Germany
- **Period**: 2001 to 2025

We investigate the relationship between rainfall characteristics and monthly rainfall erosivity using the RADOLAN dataset, which provides the highest resolution precipitation records available for Germany. This analysis establishes statistical and machine learning-based relationships between easily measurable rainfall metrics and the more complex erosivity index.

<br>

#### Phase 2: Historical Reconstruction (1931–2000)

Using the relationships established in Phase 1, we reconstruct historical monthly rainfall erosivity for the period **1931 to 2000**. This backward extension enables:
- Analysis of long-term erosivity trends over 70 years
- Assessment of climate variability impacts on erosion potential
- Identification of historical erosion risk periods
- Establishment of baseline conditions for comparison

This historical reconstruction provides crucial context for understanding how rainfall erosivity has evolved over time and helps identify whether current patterns represent significant departures from historical norms.

<br>

#### Phase 3: Future Forecasting (2026–2030)

**Model**: Convolutional Long Short-Term Memory (ConvLSTM) Network

With the complete time series from 1931 to 2025 (95 years of continuous data), we train a ConvLSTM deep learning model to forecast monthly rainfall erosivity for **2026 to 2030**. The ConvLSTM architecture is particularly suited for this task because it:
- Captures both spatial and temporal patterns in erosivity data
- Learns long-term dependencies in the time series
- Handles the complex, non-linear relationships in climate-driven processes
- Accounts for spatial autocorrelation in erosivity patterns



<br>

### Study Area

**Location**: Germany

**Temporal Coverage**:
- Historical reconstruction: 1931–2000 (70 years)
- High-resolution data: 2001–2025 (25 years)
- Future forecast: 2026–2030 (5 years)
- **Total span**: 100 years (1931–2030)

<br>

### Key Innovations

1. **Long-term Time Series**: Creation of a 95-year continuous erosivity dataset (1931–2025), one of the longest available for Germany

2. **Multi-decadal Perspective**: Analysis spanning nearly a century enables detection of long-term climate trends and cyclical patterns

3. **Deep Learning Forecasting**: Application of ConvLSTM for erosivity prediction, leveraging both temporal dynamics and spatial patterns

4. **Bridging Data Gaps**: Integration of modern high-resolution data with historical records through statistical relationships

<br>

### Expected Outcomes

This project will provide:

- **Historical Context**: 70 years of reconstructed monthly erosivity data (1931–2000) revealing long-term trends and variability

- **Complete Time Series**: Comprehensive 95-year dataset (1931–2025) for climate analysis and model training

- **Future Predictions**: Five-year erosivity forecasts (2026–2030) for proactive soil conservation planning

- **Risk Assessment**: Identification of periods with elevated erosion risk for targeted land management interventions

- **Climate Change Insights**: Evidence of temporal trends in erosivity related to climate variability and change

- **Decision Support**: Tools for policymakers and land managers to anticipate and prepare for erosion risks

<br>




