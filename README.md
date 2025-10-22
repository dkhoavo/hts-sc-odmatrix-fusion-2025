# hts-sc-odmatrix-fusion-2025
This repository provides the implementation of a data-fusion framework for generating multiday, multimodal, time-dependent origin–destination (TD–OD) matrices by integrating Household Travel Survey (HTS) data with Smart-Card (SC) transit transactions. The framework estimates private-vehicle and walking demand relative to transit at hourly resolution, enabling city-scale multimodal travel analysis without requiring complete multimodal observations.

Key components include:
1.  Adaptive Representation Learning (ARL): robust generalization of sparse survey-based mode-share ratios.
2.  Iterative Proportional Fitting (IPF): ensures survey–smart-card consistency at multiple aggregation levels.
3.  Validation module: compares fused TD–OD matrices against independent passive datasets (TomTom and cellular signaling).

Household travel survey data (Singapore 2022; Seoul 2021) and smart-card transaction data (Singapore, July 19–24 2022; Seoul, Oct 19–24 2021) were obtained from the respective transport agencies under data-use agreements and are not publicly available. TomTom vehicle probe data for Singapore (July 2022) are available from TomTom under a commercial license. Cellular signaling data for Seoul (July 2021) are publicly accessible from the Seoul Open Data Portal (https://data.seoul.go.kr/dataVisual/seoul/seoulLivingMigration.do) under the provider’s terms of use. Partial or simulated datasets supporting this study are available from the corresponding author, Bansal, upon request and with permission from the respective transport agencies.
