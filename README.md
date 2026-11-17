# DSCI 522: Titanic Survival Prediction

## Authors

- Tahir Hussain, Jaylon Huang, Rakshit Kapoor, Teeba Obaid

## Summary

This project will investigate whether passenger characteristics can be used to predict survival on the Titanic. We will build and evaluate a basic classification model using publicly available passenger data. Results and their implications will be added after the analysis is complete.

## Data

The analysis will use a publicly available Titanic passenger dataset. The report will document the original source, its license, the variables used, and the steps for downloading a copy to `data/raw/`. Cleaned data will be saved in `data/processed/`.

## How to run the analysis

The project uses Python, `uv` for environment management, and Quarto to render the report.

1. Clone the repository and enter the project directory:

   ```sh
   git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group-39-Repository.git
   cd DSCI-522-Group-39-Repository
   ```

2. Install [uv](https://docs.astral.sh/uv/getting-started/installation/) and [Quarto](https://quarto.org/docs/get-started/).

3. Create the project environment:

   ```sh
   uv sync
   ```

4. Render the report:

   ```sh
   quarto render analysis/titanic-survival-prediction.qmd
   ```

The setup and render commands will work once the corresponding environment files and report are in the repository.

## Dependencies

Python dependencies are managed with `uv` and will be listed in `pyproject.toml`. Quarto must also be installed to render the report.

## Licenses

- Project code: MIT License.
- Project report: Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0).

License texts will be provided in `LICENSE.md`.

## Generative AI use

Generative AI was used to help draft this README. The team is responsible for reviewing and verifying all project materials.

Example prompt: “Create a README for our basic Titanic survival-prediction project, following the DSCI 522 Milestone 1 requirements.”

## Report

The rendered report will be linked here when it is published: [add the rendered report URL].