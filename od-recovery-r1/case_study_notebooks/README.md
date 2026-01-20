# Case Study Notebooks (Transparency Only)

This directory contains city-specific notebooks used to generate the
Singapore and Seoul results reported in the manuscript.

These notebooks are provided **for transparency and inspection only**.
They are not required to reproduce the core simulation pipeline.

---

## Contents

- `natcom_sgp_od_matrix_gen.ipynb`  
  Singapore OD–time matrix generation and processing.

- `natcom_seoul_od_matrix_gen.ipynb`  
  Seoul OD–time matrix generation and processing.

- `natcom_result.ipynb`  
  Final result aggregation and figure generation.

---

## Notes on reproducibility

- Some notebooks require locally available OD inputs that cannot be
  publicly shared.
- City-specific processing steps are intentionally kept explicit
  rather than abstracted, to maximize clarity.
- The generalizable methodology is implemented in `sim_notebooks/`.

These notebooks reflect the **exact analytical steps** used in the paper
and are included to support methodological transparency.
