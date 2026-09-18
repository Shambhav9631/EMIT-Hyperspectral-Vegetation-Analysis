# EMIT Hyperspectral Vegetation Analysis

A Python-based workflow for analysing EMIT hyperspectral data and investigating vegetation condition using NDVI-guided sampling and spectral analysis.

## Overview

This repository provides a workflow for extracting and analysing hyperspectral information from NASA EMIT data.

The workflow uses NDVI-based vegetation classes to identify:

- Stress vegetation
- Moderate vegetation
- Healthy vegetation

The selected sample locations are matched with EMIT hyperspectral imagery to extract spectral reflectance profiles and evaluate spectral differences between vegetation conditions.

## Workflow

Sentinel-2 NDVI
↓
Vegetation Health Classification
↓
Stress / Moderate / Healthy
↓
Sample Point Generation
↓
EMIT Spatial Matching
↓
Hyperspectral Spectral Extraction
↓
Spectral Analysis
↓
Statistical Analysis
↓
Machine Learning Classification

## Main Analysis

The repository includes methods for:

- EMIT hyperspectral data inspection
- Hyperspectral reflectance extraction
- Wavelength analysis
- NDVI-guided sample selection
- Spatial matching of sample points with EMIT imagery
- Mean spectral profile generation
- Spectral variability analysis
- Spectral magnitude difference
- Euclidean spectral distance
- Spectral Angle Mapper (SAM)
- Statistical analysis
- ANOVA
- PCA
- Random Forest classification
- Support Vector Machine (SVM) classification
- Accuracy assessment
- Spectral and classification result visualization

## Hyperspectral Analysis

EMIT hyperspectral observations provide continuous spectral information across the visible, near-infrared and shortwave-infrared regions.

The workflow examines spectral responses across approximately 380–2500 nm and focuses on spectral differences among vegetation condition classes.

Important spectral regions include:

- Visible (VIS)
- Red Edge
- Near Infrared (NIR)
- Shortwave Infrared (SWIR)

## Sampling Approach

Vegetation condition classes are defined using NDVI thresholds.

The workflow then generates sample points from the selected vegetation classes and identifies valid points within the EMIT observation area.

The extracted spectra are grouped by vegetation condition for further analysis.

## Spectral Similarity and Separability

The workflow calculates spectral differences between vegetation classes using:

### Euclidean Distance

Measures the numerical distance between two spectral signatures.

### Spectral Angle Mapper (SAM)

Measures the angular similarity between spectral signatures.

### Spectral Magnitude Difference

Calculates the absolute difference between class-level mean spectral profiles across wavelengths.

These analyses help examine how well the vegetation classes can be separated using hyperspectral information.

## Statistical Analysis

Statistical methods are included to investigate differences among vegetation classes.

The workflow can include:

- t-test
- One-way ANOVA
- p-value analysis
- PCA

## Machine Learning

The extracted hyperspectral features can be used for vegetation condition classification.

Implemented methods include:

- Random Forest
- Support Vector Machine (SVM)

Classification results can be evaluated using:

- Confusion matrix
- Overall accuracy
- Precision
- Recall
- F1-score

## Repository Structure

```text
EMIT-Hyperspectral-Vegetation-Analysis/
│
├── notebooks/
│   ├── 01_EMIT_Data_Inspection.ipynb
│   ├── 02_EMIT_Preprocessing.ipynb
│   ├── 03_NDVI_Guided_Sampling.ipynb
│   ├── 04_EMIT_Spectral_Extraction.ipynb
│   ├── 05_Spectral_Analysis.ipynb
│   └── 06_Statistical_Classification.ipynb
│
├── src/
│   ├── emit_io.py
│   ├── sampling.py
│   ├── spectral.py
│   ├── statistics.py
│   └── classification.py
│
├── data/
│   └── README.md
│
├── outputs/
│   ├── figures/
│   ├── tables/
│   └── spectral_profiles/
│
├── examples/
│   └── README.md
│
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
