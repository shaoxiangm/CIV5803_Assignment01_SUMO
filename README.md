# CIV5803 SUMO baseline09

This repository contains the SUMO baseline developed for a CIV5803 electric mobility planning project. It is a frozen, corridor-level comparative traffic baseline for George Town, Penang. It is not a fully calibrated real-world traffic forecast model.

## Purpose

baseline09 supports relative congestion comparison, hotspot screening, corridor selection and downstream EV-energy analysis.

The selected downstream corridors are C1 – Lebuh Chulia, C2 – Jalan Masjid Kapitan Keling and C3 – Lebuh Farquhar. Downstream MATLAB EV analysis is not part of this SUMO baseline repository.

## Model status

**PASS_WITH_LIMITATIONS**

The frozen validation summary in `outputs/baseline09_sanity_summary.csv` records 3,640 vehicles loaded, 3,526 inserted (96.87%), 3,509 completed, and 131 remaining at the end of the run.

## Important limitations

- Demand was reduced and reconstructed.
- The model is not a fully calibrated 51-zone origin–destination model.
- Simulated throughput is not observed annual average daily traffic (AADT).
- The baseline is not intended for absolute traffic forecasting.
- Results should primarily be interpreted comparatively.

Further detail is in `docs/assumptions_and_limitations.md`.

## Repository layout

- `config/`: frozen SUMO configuration with repository-relative references.
- `network/`: OpenStreetMap-derived SUMO network.
- `additional/`: edge-data output configuration.
- `demand/`: instructions for the intentionally omitted route-demand input.
- `outputs/`: frozen validation and comparative outputs.
- `docs/`: limitations, corridor definitions and attribution.

## Requirements

This baseline was checked with **Eclipse SUMO 1.27.1**. Other versions may read the configuration, but have not been validated for identical output.

## Running the model

The original, authorised route file must first be supplied at `demand/am_baseline08.rou.xml`. From the repository root, run `sumo -c config/am_baseline09.sumocfg`.

Generated raw outputs are written to `outputs/generated/`, which is intentionally ignored by Git.

## Data and licensing

- The SUMO configuration, repository documentation and processed result summaries are project-authored materials.
- The network is derived from OpenStreetMap and carries the attribution and ODbL notice in `docs/ATTRIBUTION.md`.
- Certain course-provided or third-party source datasets are not redistributed in this repository. The route-demand input and calibration inputs are omitted pending confirmation of redistribution permission.

## Academic context

This repository contains the SUMO baseline developed for a CIV5803 electric mobility planning project.
