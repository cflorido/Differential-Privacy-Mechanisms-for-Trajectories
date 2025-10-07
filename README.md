# Differential Privacy for Trajectories

This repository contains the final version of my thesis project focused on applying **differential privacy mechanisms** to human mobility trajectories.  
The main goal is to protect sensitive location data while preserving analytical value for mobility studies, such as transportation planning and urban analysis.

The project implements, tests, and compares multiple algorithms under different configurations, generating metrics and visualizations that illustrate the trade-off between privacy and utility.

---

## Objectives

- Apply differential privacy algorithms to real-world trajectory datasets  
- Compare different mechanisms by varying key metrics and parameters  
- Evaluate the impact of privacy on data utility and analytical outcomes  
- Produce relevant visualizations such as:  
  - Flow maps of trajectories  
  - Heatmaps of mobility density  
  - Origin-destination matrices  
  - Comparative performance graphs  

---

## Dataset

The experiments use the **Geolife Trajectories 1.3 dataset**, a large-scale GPS trajectory dataset collected in Beijing.  
It provides real-world mobility traces suitable for privacy-preserving analysis.

---

## Repository Structure

```bash
Final_version/
├── Anchor_graphs/             # Results and plots for the Anchor mechanism
├── Laplace_graphs/            # Results and plots for the Laplace mechanism
├── Pivot_graphs/              # Results and plots for the Pivot Sampling mechanism
├── anchor_code.ipynb          # Implementation of the Anchor mechanism
├── anchor_data_1.csv          # Anchor experiment data
├── laplace_code.ipynb         # Implementation of the Laplace mechanism
├── laplace_results.csv        # Laplace experiment results
├── LDPtrace_code.ipynb        # Core implementation of LDP for trajectories
├── pivot_sampling_code.ipynb  # Implementation of Pivot Sampling
├── pivot_data_1.csv           # Pivot experiment data
Geolife Trajectories 1.3/  # Dataset (not included due to size, see below)
Referencias/               # Bibliographic references
