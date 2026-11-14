# Pore Pressure Prediction Using Eaton's Method

A Python-based petrophysical and geomechanical workflow designed to predict formation pore pressure from well logs using **Eaton’s Sonic Method**. 

This script automates the full geomechanical evaluation pipeline—from raw LAS well log ingestion to lithology discrimination, overburden stress integration, normal compaction trend (NCT) calibration, and final pore pressure profiling.

---

## Features
- **Automated LAS File Handling:** Reads standard Log ASCII Standard (`.las`) files using `lasio`, with automatic fallback to download an open-source sample dataset if no local file is provided.
- **Shale Discrimination:** Uses Gamma Ray (GR) cutoffs to isolate shale intervals where compaction trends apply.
- **Overburden Stress ($S_v$) Integration:** Computes cumulative lithostatic pressure from bulk density ($\rho_b$) logs, accounting for water depth and air gap elevations.
- **Hydrostatic Pressure ($P_h$) Modeling:** Calculates normal fluid pressure profiles based on formation water/seawater density.
- **Normal Compaction Trend (NCT):** Performs semi-log linear regression ($\ln(\Delta t)$ vs. depth below mudline) within user-defined compaction intervals.
- **Eaton’s Equation Implementation:** Applies the sonic Eaton exponent ($3.0$ standard) to estimate pore pressure relative to overburden and hydrostatic baselines.
- **Quality Control & Smoothing:** Integrates rolling median filters to eliminate high-frequency noise and interpolates pressure across non-shale layers.
- **Professional Visualization & Export:** Generates a publication-grade 3-track geomechanical composite plot (Sonic/NCT, Gamma Ray, and Pressure Profiles) and exports results to CSV.

---

## Prerequisites & Dependencies
Ensure you have Python 3.x installed along with the required scientific and petrophysical libraries:

```bash
pip install numpy pandas matplotlib lasio
