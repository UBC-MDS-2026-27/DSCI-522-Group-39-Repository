
# Contributing to Titanic Survival Prediction

**DSCI 522 — Group 39**

Our project investigates whether passenger characteristics can predict survival on the Titanic. Contributions should help improve the analysis, make the work reproducible, or communicate the findings more clearly.

The following guidelines explain how to contribute to the project.

## Discussing Changes

We use GitHub Issues to discuss tasks, report problems, and coordinate substantial changes before starting work.

When creating an issue, explain the problem or proposed improvement and why it matters. For bugs, include the relevant commands, error messages, and steps to reproduce the problem.

Minor documentation corrections may be proposed directly through a pull request.

## Reproducing the Project Environment

Our project uses Python, [uv](https://docs.astral.sh/uv/getting-started/installation/) to manage dependencies, and [Quarto](https://quarto.org/docs/get-started/) to create the report.

Install Python 3.12 or newer, uv, and Quarto before proceeding.

Clone the repository and open its directory:

```sh
git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group-39-Repository.git
cd DSCI-522-Group-39-Repository
```

Set up the Python environment:

```sh
uv sync --locked
```

Run the analysis and render the Quarto project:

```sh
uv run quarto render
```

If a new Python package is needed, add it using `uv add <package>` and commit the updated `pyproject.toml` and `uv.lock` files.

## Working with Data and Analysis

To keep our analysis reliable and reproducible:

- Store original data in `data/raw/` and cleaned or transformed data in `data/processed/`.
- Split the data before exploratory analysis or preprocessing to prevent information from the held-out test set influencing the analysis.
- Explain analytical decisions, support findings with appropriate evidence, and cite data sources and references.
- Edit the Quarto source file (`.qmd`) rather than manually changing rendered HTML or PDF files.
- Check that the analysis runs correctly and that figures and explanations are consistent with the results.

These practices will guide our work as the analysis develops.

## Contributing Through GitHub

We use separate branches and pull requests to review changes before adding them to `main`.

1. Update your local `main` branch before starting a new task.
2. Create a branch with a descriptive name and keep its changes focused on one task.
3. Commit changes regularly using meaningful messages.
4. Review and test your work, including rendering the report when relevant.
5. Push your branch and open a pull request to `main`. Explain what changed, why, how it was tested, and reference any related issue.
6. Have at least one teammate review and approve the pull request. Address necessary feedback before it is merged.

Do not push directly to `main`. Keep temporary files, local environments, credentials, and unrelated generated files out of commits. Include the final rendered report when required for submission.

## Generative AI Policy

Generative AI tools may be used for brainstorming, explanations, debugging, coding assistance, and drafting documentation.

Contributors must:

- Understand, review, and test any AI-assisted work before submitting it.
- Check the accuracy of generated code, information, and references.
- Disclose which AI tool was used and how it assisted in the relevant GitHub issue or pull request.
- Include example prompts when AI-generated contributions are substantial.

GitHub issues and pull requests must be opened, reviewed, and merged by human contributors. AI tools may assist, but contributors remain responsible for their work and decisions.

## Code of Conduct

All contributors are expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md), which outlines expectations for respectful communication, constructive feedback, and collaboration.

## Attribution

These guidelines were developed for DSCI 522 Group 39, drawing on the course's Milestone 1 requirements and the [dplyr contributing guidelines](https://github.com/tidyverse/dplyr/blob/master/.github/CONTRIBUTING.md), and adapted to our Titanic survival prediction project.
