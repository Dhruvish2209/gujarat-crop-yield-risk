# Gujarat Crop Yield Risk Early-Warning System

A machine-learning project concept for estimating whether a crop-season yield in Gujarat may fall below its historical baseline, using crop production history and rainfall features where reliable public data can be aligned.

> **Current status:** Project scaffold. Data preparation, model training, evaluation, and API implementation have not been completed. No performance or deployment claims are made.

## Intended prediction

For a selected crop, district, and season, estimate a **below-baseline yield risk** from information available before or during that season. The target definition and prediction timing will be documented before modeling. This is an analytical prototype, not an official agricultural advisory.

## Planned workflow

1. Check public crop-yield/production and rainfall data availability, field definitions, units, date coverage, and geographic granularity.
2. Define the target transparently (for example, yield below a crop- and district-specific historical threshold) and document any exclusions.
3. Clean and align records by district, crop, season, and year; investigate missingness and boundary/name changes.
4. Build leakage-aware historical and rainfall features. Split evaluation by time so future seasons are not used to predict the past.
5. Compare a simple baseline with scikit-learn models; consider CatBoost only if it suits the data and validation setup.
6. Evaluate with appropriate classification metrics, class balance checks, and error analysis. Report results only after running the experiments.
7. If model validation supports it, expose a small prediction endpoint using FastAPI and add a Docker setup for reproducible local execution.

## Planned interface

The intended final prototype may include a FastAPI health route and prediction route, plus a lightweight local request example. API and Docker files will be added after the data and model pipeline exists. There is no deployed service at this stage.

## Data sources to investigate

- [District-wise, season-wise crop production statistics, data.gov.in](https://www.data.gov.in/resource/district-wise-season-wise-crop-production-statistics-1997)
- [Rainfall datasets, National Water Data Portal](https://nwdp.nwic.gov.in/en/dataset/rainfall-gujarat-sw-gw-manual-daily)

Dataset availability, permitted use, district mapping, and matching time periods must be verified before modeling. Do not commit restricted or large raw datasets; document acquisition steps in `data/README.md`.

## Stack

Python, Pandas, NumPy, scikit-learn, CatBoost, FastAPI, Docker.

## Planned structure

```text
data/       data-source notes and acquisition instructions
notebooks/  exploration and feature checks
src/        data preparation, training, and inference code
api/        FastAPI application (after model pipeline is implemented)
```

## Run locally

Setup instructions will be added with the first runnable implementation.