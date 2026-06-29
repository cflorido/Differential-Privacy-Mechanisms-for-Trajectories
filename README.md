# Differential Privacy for Trajectory Data

This repository contains the experiments and thesis artifacts for evaluating differential privacy mechanisms on human mobility trajectories, using the GeoLife dataset as the main source of GPS traces.

## Project Goals

- Study how privacy-preserving mechanisms affect trajectory utility.
- Compare Laplace, Pivot Sampling, Anchor, and related LDP-based approaches.
- Generate reproducible maps, origin-destination matrices, and comparison metrics.

## Repository Structure

```text
.
├── artifacts/
│   ├── anchor/
│   │   ├── analysis_outputs/
│   │   └── maps/
│   ├── laplace/
│   │   ├── analysis_outputs/
│   │   └── maps/
│   └── pivot/
│       ├── analysis_outputs/
│       └── maps/
├── data/
│   └── raw/
│       └── geolife_trajectories_1_3/
├── docs/
│   └── references/
├── notebooks/
│   ├── 01_ldp_trace_foundations.ipynb
│   ├── 02_laplace_mechanism_analysis.ipynb
│   ├── 03_pivot_sampling_analysis.ipynb
│   └── 04_anchor_mechanism_analysis.ipynb
└── README.md
```

## Notebook Guide

- `01_ldp_trace_foundations.ipynb`: base concepts and LDP trajectory groundwork.
- `02_laplace_mechanism_analysis.ipynb`: Laplace mechanism experiments and visual outputs.
- `03_pivot_sampling_analysis.ipynb`: Pivot Sampling experiments, OD matrices, and maps.
- `04_anchor_mechanism_analysis.ipynb`: Anchor-based experiments and comparison outputs.

## Data and Outputs

- Raw trajectory files are stored in `data/raw/geolife_trajectories_1_3`.
- Bibliographic material is grouped in `docs/references`.
- Generated CSV, HTML, and PNG outputs are organized by mechanism inside `artifacts`.

## Technical Methodology

The research workflow followed in this repository is organized as a reproducible experimental pipeline:

1. Data acquisition and selection

- Real trajectories were taken from the GeoLife Trajectories 1.3 dataset.
- Individual `.plt` files and user trajectory folders were selected as the base input for the experiments.

2. Trajectory loading and preprocessing

- GPS points were loaded from the original GeoLife trajectory files.
- Raw trajectories were converted into analysis-ready coordinate sequences.
- In the mechanism-specific notebooks, trajectories were also transformed into local representations and grid-based views when required by the experiment.

3. Differential privacy mechanisms

- `02_laplace_mechanism_analysis.ipynb` evaluates point-wise perturbation with the Laplace mechanism under multiple privacy budgets.
- `03_pivot_sampling_analysis.ipynb` evaluates Pivot Sampling over multiple grid resolutions and parameter settings.
- `04_anchor_mechanism_analysis.ipynb` evaluates an Anchor-based mechanism and compares its outputs against the original trajectories.
- `01_ldp_trace_foundations.ipynb` contains the conceptual and algorithmic groundwork for the LDP trajectory setting used across the study.

4. Spatial aggregation and OD construction

- Perturbed and original trajectories were mapped to spatial cells.
- Origin-destination matrices were generated for each configuration.
- Supporting artifacts such as cell assignments, minima, and intermediate CSVs were persisted for later inspection.

5. Parameter sweeps

- The experiments were not limited to a single configuration.
- Laplace experiments sweep multiple `epsilon` values and grid step sizes.
- Pivot and Anchor experiments sweep multiple `k` values and spatial step sizes.

6. Utility evaluation

- The notebooks compute comparison metrics between original and perturbed trajectories.
- The evaluation includes geometric and statistical indicators such as mean distance, maximum distance, standard deviation, length error, direction error, Hausdorff distance, and execution time.

7. Reporting and visualization

- Each mechanism exports structured CSV outputs for downstream analysis.
- HTML and PNG artifacts are produced for maps, tables, and summary charts.
- Results are grouped by mechanism inside `artifacts` to keep the analytical trail auditable.

## Notes

- The notebooks were updated to use the current folder layout.
- Output folders keep historical experiment artifacts so previous results remain traceable.
