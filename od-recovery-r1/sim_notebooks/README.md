# Simulation Notebooks

This directory contains the core simulation workflow used to generate and
analyze synthetic multimodal OD data.

The notebooks are ordered and intended to be read sequentially.

---

## 00_prepare_sim_data.ipynb (Transparency only)

**Purpose**  
This notebook demonstrates how simulated OD inputs are constructed from
household travel survey (HTS) microdata.

**Important notice**  
This notebook requires restricted HTS microdata: data_hts_{reg}.csv (reg ∈ {seoul})

These files are **not provided** in the GitHub repository due to data access
and privacy constraints.

Accordingly, this notebook is provided **for transparency only** and is not
required to run the main simulation pipeline.

---

### Simulation logic

Given restricted HTS microdata, the notebook performs the following steps:

1. **HTS preprocessing**
   - Remove individual identifiers and time stamps.
   - Treat each trip as one observation (`COUNT = 1`).
   - Restrict OD support to observed OD pairs with positive transit demand.

2. **True OD mode counts**
   - Aggregate HTS trips by OD pair.
   - Construct ground-truth counts for:
     - Public transport (PT)
     - Walking (WK)
     - Private vehicle (VH)
   - Retain only OD pairs with nonzero PT demand.

3. **Land-use mixture features**
   - Derive destination land-use mixture vectors based on trip purposes.
   - These features are used as contextual covariates in downstream models.

4. **Mode-share priors**
   - Construct origin- and destination-level priors for VH and WK modes
     from HTS observations.

5. **Smart-card proxy generation**
   - Create a PT-only OD dataset mimicking smart-card observations.
   - Attach trip distance computed from OD centroids.

6. **Export simulation inputs**
   The following CSV files are generated and saved to `od_sim_data/`:
   - Destination land-use mixture and mode share
   - Origin and destination mode priors
   - Smart-card proxy OD data (PT only)
   - Ground-truth multimodal OD counts (all modes)

7. **HTS subsampling**
   - Generate five independent HTS samples (20% each) to simulate
     survey variability.
   - Each sample includes trip distance and OD attributes only.

---

## 01_run_pipeline.ipynb

**Purpose**  
Runs the OD estimation and reconstruction pipeline using simulated inputs.

This notebook:
- Consumes the exported simulation data from `od_sim_data/`
- Trains OD inference models
- Produces reconstructed OD matrices and evaluation metrics

---

## 02_select_k_and_plot.ipynb

**Purpose**  
Performs model selection and visualization.

This notebook:
- Selects the optimal latent dimension or cluster size
- Generates diagnostic and manuscript-quality plots
- Summarizes performance metrics
