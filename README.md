# hts-sc-odmatrix-fusion-2025
This repository provides the implementation of a data-fusion framework for generating multiday, multimodal, time-dependent origin–destination (TD–OD) matrices by integrating Household Travel Survey (HTS) data with Smart-Card (SC) transit transactions. The framework estimates private-vehicle and walking demand relative to transit at hourly resolution, enabling city-scale multimodal travel analysis without requiring complete multimodal observations.

Key components include:
1.  Adaptive Representation Learning (ARL): robust generalization of sparse survey-based mode-share ratios.
2.  Iterative Proportional Fitting (IPF): ensures survey–smart-card consistency at multiple aggregation levels.
3.  Validation module: compares fused TD–OD matrices against independent passive datasets (TomTom and cellular signaling).
