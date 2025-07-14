# Discrete AR(1) Time Series with Exponential Dispersion Models

## Overview

This repository contains the final project for the **Time Series** course (Semester 2025-2) at Universidad Nacional Autónoma de México (UNAM, IIMAS). The study presents an **autoregressive model of order 1 (AR(1))** with **Exponential Dispersion Model (EDM)** margins to analyze discrete count data, exemplified by daily railway accident counts in Mexico from October 2016 to April 2024.

## Author

* Allison Lara Nieva


## Methodology

1. **Data Preparation**

   * Download daily counts of railway accidents from datos.gob.mx (Oct 2016–Apr 2024).
   * Impute zeros for missing dates and split into training (≤ Dec 2022) and test (≥ Jan 2023) sets.

2. **Model Specification**

   * **AR(1)-Poisson**: thinning via binomial component and Poisson innovation.
   * **AR(1)-Negative Binomial**: beta‑binomial thinning and negative‑binomial innovation.
   * **AR(1)-Gaussian**: classical AR(1) with Gaussian noise for comparison.

3. **Parameter Estimation**

   * Maximize conditional log‑likelihood with constraints (ρ∈\[0,1], λ>0, p∈(0,1)) using SciPy.

4. **Validation & Comparison**

   * Compute **AIC** on training data and **MSE** on test data.
   * Assess computational cost (execution time) for each model.
   * Visualize predicted vs observed counts for 2023–2024.


## Key Results

* **Best AIC**: AR(1)-Negative Binomial (AIC = 9695.78), lowest training information criterion.
* **Best test MSE**: AR(1)-Poisson (MSE = 7.728) closely followed by Negative Binomial (7.813).
* **Gaussian AR(1)**: poorest fit (AIC = 9905.13, MSE = 8.975) and produced non-integer/negative predictions.
* **Computational time**: Negative Binomial required the longest estimation (≈ 271 s).
