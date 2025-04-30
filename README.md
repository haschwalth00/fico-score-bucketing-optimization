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
Final optimized log likelihood: 1034.6281
Optimal Bucket Boundaries: [300, 551, 589, 620, 652, 681, 708, 734, 757, 779, 850]

This result means the FICO score range of 300–850 is optimally split at those points to differentiate borrower risk based on the data.

## Files

- `fico_bucket_quantization.py`: Full implementation including data loading, model logic, and output
- `ref data.csv`: Synthetic dataset with `fico_score` and `default` fields

## Use Cases

- Risk modeling for credit cards, loans, mortgages
- Scorecard design and explainability
- Regulatory reporting (bucketed PD/EL segmentation)

## Assumptions

- Bucket count (r) is set to 10 — can be changed in the code
- FICO scores range from 300 to 850 (standard U.S. convention)
- All data is synthetic and used solely for educational purposes

## Disclaimer

> This is an independently developed project using synthetic data. The methodology reflects statistical concepts used in real-world credit risk modeling but is intended for demonstration only.


