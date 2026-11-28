
# Contributing to Titanic Survival Prediction

**DSCI 522 — Group 39**

Our project investigates whether passenger characteristics can predict survival on the Titanic. Contributions should help improve the analysis, make the work reproducible, or communicate the findings more clearly.

The following guidelines explain how to contribute to the project.

## Discussing Changes

We use GitHub Issues to discuss tasks, report problems, and coordinate substantial changes before starting work.

When creating an issue, explain the problem or proposed improvement and why it matters. For bugs, include the relevant commands, error messages, and steps to reproduce the problem.

Minor documentation corrections may be proposed directly through a pull request.

## Reproducing the Project Environment

This project runs in a Docker container so all contributors share the exact same Python, `uv`, and Quarto environment.

### 1. Initial Setup

Before starting, follow the setup steps in [`README.md`](README.md) to:
1. Verify that your Git identity (`git config --global user.name` and `git config --global user.email`) is configured on your host machine (mounted into the container via `~/.gitconfig`).
2. Generate an SSH key (`ssh-keygen -t ed25519`) if you do not already have `~/.ssh/id_ed25519.pub`.
3. Clone the repository and pull the pre-built project Docker image (`docker compose pull`).

*(Note: To keep run-only instructions in [`README.md`](README.md) and contributor instructions here, we do not repeat those initial setup commands in this file.)*

### 2. Connect Positron to the Container over SSH

1. Install [Positron](https://positron.posit.co/) on your local machine if you have not already.
2. Start the container in the background from the repository root:
   ```bash
   docker compose up -d
   ```
3. In Positron, open the Command Palette (`Cmd+Shift+P` on macOS / `Ctrl+Shift+P` on Windows and Linux), choose **Remote-SSH: Connect to Host...**, and connect to:
   ```bash
   ssh -p 2222 root@localhost
   ```
4. Once connected, open the `/workspace` folder in Positron.
5. Select the container's Python interpreter located at `/opt/venv/bin/python` (configured via `UV_PROJECT_ENVIRONMENT=/opt/venv` in the `Dockerfile`).
6. In the Positron terminal inside the container, verify that your Git identity is recognized:
   ```bash
   git config user.name
   git config user.email
   ```
7. When you finish working, disconnect from the remote session in Positron and stop the container from your host terminal:
   ```bash
   docker compose down
   ```

#### Troubleshooting SSH and Container Connection Issues

- **`~/.ssh/id_ed25519.pub` became a directory**: If you ran `docker compose up -d` before generating `~/.ssh/id_ed25519.pub`, Docker creates an empty directory at `~/.ssh/id_ed25519.pub` on your host machine, causing mount or login errors. To fix this, stop the container (`docker compose down`), remove the empty directory (`rmdir ~/.ssh/id_ed25519.pub`), generate your SSH key (`ssh-keygen -t ed25519`), and start the container again.
- **Host key verification failed (`WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!`)**: When the container image is rebuilt, its SSH host key changes. Run `ssh-keygen -R "[localhost]:2222"` on your local machine to clear the old key and reconnect.
- **SSH still prompts for a password on Linux**: Ensure your public key exists at `~/.ssh/id_ed25519.pub` with readable permissions (`chmod 644 ~/.ssh/id_ed25519.pub`) and that your image is up to date (`docker compose pull`), which includes `StrictModes no` in `/etc/ssh/sshd_config.d/container.conf`.

### 3. Adding or Updating Python Packages

Because dependencies are baked into the Docker image at `/opt/venv`, follow these steps whenever you add or update a Python package (or modify the `Dockerfile`):

1. Create and switch to a feature branch for your change.
2. Inside the running container (in `/workspace`), add or update the package with `uv` using exact version pinning:
   ```bash
   uv add "package-name==x.y.z"
   ```
3. Verify that both `pyproject.toml` and `uv.lock` are updated, then commit and push them to your **feature branch** on GitHub.
4. Pushing dependency or `Dockerfile` changes to any branch automatically triggers the `.github/workflows/publish-dockerhub.yml` GitHub Actions workflow. Wait for it to build and publish the new Docker image (`tahir1710/dsci-522-group-39-repository`) and commit the updated `sha-` image tag to `docker-compose.yml` **on your feature branch**.
5. Pull the workflow's commit on your feature branch and test the new image locally:
   ```bash
   git pull
   docker compose down
   docker compose pull
   docker compose up -d
   ```
6. Once verified, open a pull request to `main`. After a teammate reviews, approves, and merges your PR into `main`, the merge will trigger another image build and automatically update the `sha-` image tag in `docker-compose.yml` on `main`. Teammates on `main` can then run `git pull` and `docker compose pull` to get the updated environment.

### 4. Rendering the Report and Updating GitHub Pages

After editing `analysis/titanic-survival-prediction.qmd`, render the self-contained HTML report inside the container and update `docs/index.html` for GitHub Pages:

```bash
uv run quarto render
mkdir -p docs
cp analysis/titanic-survival-prediction.html docs/index.html
touch docs/.nojekyll
```

Verify that both `analysis/titanic-survival-prediction.html` and `docs/index.html` render cleanly before committing and opening your pull request.

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

These guidelines were developed for DSCI 522 Group 39, drawing on the course's Milestone 1 and Milestone 2 requirements and the [dplyr contributing guidelines](https://github.com/tidyverse/dplyr/blob/master/.github/CONTRIBUTING.md), and adapted to our Titanic survival prediction project.
