# FICO Score Bucketing Optimization

## Overview

This project implements a **log-likelihood-based dynamic programming algorithm** to determine optimal FICO score buckets for credit risk stratification. The model simulates how financial institutions might discretize continuous credit scores into bins that best separate borrowers by default risk.

## Author

**Vanshwardhan Singh**

## Objective

To divide FICO scores into **10 optimal buckets** that:
- Maximize the separation of **default vs non-default** patterns
- Improve credit scoring interpretation and explainability
- Support use cases in **risk modeling, underwriting, and pricing**

## Methodology

- Uses a **synthetic loan dataset** with `default` flags and `fico_score` values
- Computes **cumulative defaults and totals** for every score point
- Applies **maximum log-likelihood segmentation** logic using dynamic programming
- Recovers bucket boundaries that **maximize statistical separation**

## Key Components

- **Log-Likelihood Function:** Measures goodness of split between default and non-default at each bucket boundary
- **Dynamic Programming Table:** Tracks optimal scores to split at, storing max log-likelihood value at each stage
- **Boundary Recovery:** Backtraces from optimal solution to extract final FICO score cutoffs

## Sample Output

