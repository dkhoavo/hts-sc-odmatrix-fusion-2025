# Simulation Pipeline for Multimodal TD–OD Flow Recovery

This repository provides a transparent and reproducible simulation pipeline
for multimodal time-dependent origin–destination (TD–OD) flow recovery.
The code accompanies a Nature Communications manuscript and is structured to
clearly distinguish between:

- a generic, reproducible simulation and model-selection workflow, and
- city-specific case-study notebooks provided for methodological transparency.

## Repository structure

- `sim_notebooks/`  
  Core simulation workflow, including data preparation, OD inference, and
  model selection.

- `case_study_notebooks/`  
  City-specific notebooks used to generate the Singapore and Seoul results
  reported in the manuscript (provided for transparency only).

- `od_sim_data/`  
  Simulation input data. Raw household travel survey (HTS) microdata are not
  publicly distributed due to data access constraints.

- `od_sim_result/`  
  Generated simulation outputs, intermediate results, and figures.

## Execution order (simulation workflow)

1. `sim_notebooks/00_prepare_sim_data.ipynb`  
   Transparent generation of simulated inputs from restricted HTS microdata
   (transparency only; raw HTS data not included).

2. `sim_notebooks/01_run_pipeline.ipynb`  
   Multimodal TD–OD inference and reconstruction pipeline applied to the
   simulated inputs.

3. `sim_notebooks/02_select_k_and_plot.ipynb`  
   Model selection, performance evaluation, and figure generation.

## Environment setup

The computational environment is specified in `environment.yml`.
