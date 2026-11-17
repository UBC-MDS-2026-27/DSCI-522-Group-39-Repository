# DSCI 522: Titanic Survival Prediction

## Authors

Tahir Hussain, Jaylon Huang, Rakshit Kapoor, and Teeba Obaid

## Summary

This project asks whether passenger information can be used to predict survival on the Titanic. We plan to build and evaluate a basic classification model using a publicly available passenger dataset. The analysis is still in progress, so this README does not yet report model results. Any eventual patterns should be interpreted as associations in this historical dataset, not as evidence of cause and effect or as a model for real-world decisions.

## Data

The project will use a publicly available Titanic passenger dataset. The analysis report will identify and cite the data source, describe the observations and variables used, and document how the data is downloaded to `data/raw/` and prepared for analysis in `data/processed/`.

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

The intended licenses are the MIT License for project code and the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0) for the report. The corresponding license texts and team copyright attribution should be maintained in [`LICENSE.md`](LICENSE.md).

## Generative AI use

Generative AI assisted with drafting this README and the project contribution and conduct documents. The authors are responsible for reviewing, correcting, and verifying all project content.

Example prompt: “Fill the README, contributing guide, and code of conduct based on the examples shared, adapting them to our Titanic survival-prediction project.”

## Report

The report has not yet been rendered or published. Add a link to the rendered report here when it is available.