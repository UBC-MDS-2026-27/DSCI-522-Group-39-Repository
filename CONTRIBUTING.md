# Contributing to Titanic Survival Prediction

Thank you for your interest in this project. Contributions should help make the Titanic survival analysis clearer, more reproducible, or more reliable.

## Before making a change

For a bug, question, or substantial proposed change, open a GitHub issue first so the project team can discuss the scope. Include enough detail to reproduce a problem, such as the command you ran, the error message, and the expected behavior. Small documentation fixes can be submitted directly as a pull request.

## Set up the project

Install [uv](https://docs.astral.sh/uv/getting-started/installation/), Python 3.12 or newer, and [Quarto](https://quarto.org/docs/get-started/). Then clone the repository, enter its directory, and sync the environment:

```sh
git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group-39-Repository.git
cd DSCI-522-Group-39-Repository
uv sync --locked
```

To check that the Quarto project renders, run:

```sh
uv run quarto render
```

## Pull request process

1. Start from the latest `main` branch and create a descriptive branch for one focused change, such as `clarify-data-source` or `add-survival-plot`.
2. Make changes in the source files. For the report, edit the `.qmd` file rather than generated HTML or PDF output.
3. If you add a Python dependency, use `uv add <package>` and commit the resulting changes to both `pyproject.toml` and `uv.lock`.
4. Render the project with `uv run quarto render` and review the resulting output. Explain in the pull request if you could not render it.
5. Open a pull request to `main`. Describe what changed, why it is needed, how you checked it, and link any related issue.
6. Ask a teammate to review the pull request. A human team member must review and merge it; do not push directly to `main`.

Keep pull requests focused and avoid including unrelated generated files, local environment files, or credentials.

## Generative AI policy

Generative AI tools may be used for brainstorming, explanations, debugging suggestions, or help drafting code and documentation. Contributors must disclose AI use in the relevant issue or pull request, including the tool and a brief description of how it was used; include example prompts when AI-generated material is substantial.

The contributor remains responsible for understanding, reviewing, testing, and correcting all submitted work, including any AI-assisted work. AI tools or agents must not open issues or pull requests, approve or merge changes, or make decisions on behalf of the team. Issues and pull requests must be opened and reviewed by human contributors.

## Code of Conduct

By participating, contributors agree to follow this project's [Code of Conduct](CODE_OF_CONDUCT.md).

## Attribution

These guidelines were written for this project with reference to the [dplyr contributing guidelines](https://github.com/tidyverse/dplyr/blob/master/.github/CONTRIBUTING.md) and the DSCI 522 Milestone 1 expectations.