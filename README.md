# DSCI 522: Titanic Survival Prediction

## Authors

Tahir Hussain, Jaylon Huang, Rakshit Kapoor, and Teeba Obaid

## Summary

This project investigates whether passenger information can predict survival on the Titanic. Using the Kaggle Titanic dataset (891 labelled training passengers and 418 unlabelled test passengers), we conduct an exploratory data analysis, engineer domain-informed features, and evaluate a regularized logistic regression pipeline via 5-fold stratified cross-validation. Logistic regression on the 5 correlation-selected features reaches 77.4% cross-validation accuracy, and adding our optional features (`Age`, `FamilySize`, passenger titles) and the `Sex × Pclass` interaction lifts accuracy to **82.6%** (F1 = 0.761, ROC-AUC = 0.871), compared with 61.6% for a majority-class baseline. We interpret observed patterns as associations in this historical dataset, not as evidence of cause and effect or as a basis for real-world decisions.

## Data

The project uses a publicly available Titanic passenger dataset. The analysis report identifies and cites the data source, describes the observations and variables used, and documents how the data is downloaded to `data/raw/` and prepared for analysis in `data/processed/`.

The dataset is split into 891 training records (12 columns, including the Survived target) and 418 test records (11 columns, without the target). Each row represents an individual passenger.

Data link: https://www.kaggle.com/competitions/titanic/data

## How to run the analysis

The project uses Python, [uv](https://docs.astral.sh/uv/) to manage the Python environment, and [Quarto](https://quarto.org/) to render the report. Install [uv](https://docs.astral.sh/uv/getting-started/installation/), Python 3.12 or newer, and [Quarto](https://quarto.org/docs/get-started/) first. These tools are installed separately.

From a terminal, clone the repository and enter its directory:

```sh
git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group-39-Repository.git
cd DSCI-522-Group-39-Repository
```

Create the project environment from the committed dependency files:

```sh
uv sync --locked
```

Render the Quarto project from its root directory:

```sh
uv run quarto render
```

Rendering requires an internet connection if the analysis needs to download the dataset. The report and data-download workflow are under development; update these instructions if their paths or behavior change.

## Dependencies

The project uses Python 3.12 or newer and the Python packages listed in [`pyproject.toml`](pyproject.toml), with exact resolved versions recorded in [`uv.lock`](uv.lock). Quarto must also be installed separately.

## Licenses

The project uses the MIT License for project code and the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0) for the report. The team maintains the corresponding license texts and copyright attribution in [`LICENSE.md`](LICENSE.md).

## Generative AI use

Generative AI assisted with drafting this README and the project contribution and conduct documents. The authors are responsible for reviewing, correcting, and verifying all project content.

Example prompt: “Fill the README, contributing guide, and code of conduct based on the examples shared, adapting them to our Titanic survival-prediction project.”

## Report

The rendered analysis report is available in the repository at [`analysis/titanic-survival-prediction.html`](analysis/titanic-survival-prediction.html) (generated from [`analysis/titanic-survival-prediction.qmd`](analysis/titanic-survival-prediction.qmd)).