# Prompts

## Rakshit's Prompt

**AI tool / model used:** ChatGPT and GitHub Copilot

**Task / context:** Learning, reviewing, and contributing to the DSCI 522 Titanic survival prediction project while understanding the analysis and making my own decisions.

**Representative prompt:**

"I'm a DSCI 522 student, and my goal is to understand the work and produce my own submissions. Act as a patient tutor and critical thinking partner, not a ghostwriter. Guide me through problems in small steps: first ask what I've tried or expect, then offer a hint before giving a full explanation. Explain why an approach works, and ask clarifying questions rather than making assumptions. Give honest, specific feedback about incorrect reasoning, unsupported conclusions, and reproducibility concerns. Use brief, generic examples when useful, but don't write my assignment or report for me. If I ask for a complete solution, remind me to try the next step myself first. For Python environment management, use uv."

**Review and verification:**

I checked suggestions against the repository and the project requirements. For the modeling update, I compared the QMD source with the rendered HTML and checked that the reported results and generated outputs were consistent. For the license update, I checked the summary and link against the selected CC BY-NC-ND 4.0 license. I reviewed and approved changes only after these checks.

## Teeba's Prompt

**AI tool:** ChatGPT

**Task:** Revising the Titanic survival prediction modeling code.

Our Titanic survival prediction analysis has two methodological concerns:

**Representative prompt:**

"Potential data leakage from performing feature selection and preprocessing before cross-validation.
The absence of survival labels in Kaggle's test dataset, preventing direct evaluation of model performance.
Using the existing logistic regression code [insert code here], what modifications are needed to perform feature selection, imputation, and standardization within each cross-validation training fold, introduce a stratified 70/30 split of the labeled dataset, and evaluate the model on an independent held-out test set? Explain the reasoning behind these changes."

**Review and verification:**

Reviewed the suggested code modifications against the existing implementation, tested the revised code, and verified the model outputs and successful Quarto rendering.

## Jaylon's Prompt

**AI tool / model used:** ChatGPT

**Task / context:** Understanding, reviewing, and improving the Titanic survival prediction project, including exploratory data analysis, data leakage prevention, cross-validation, model evaluation, and project documentation.

**Representative prompt:**

"I'm working on a DSCI 522 group project involving Titanic survival prediction. Act as a tutor and critical reviewer. Help me understand the existing code and methodology before suggesting changes. Review the implementation for potential issues such as data leakage, inappropriate train/test splitting, cross-validation, and model evaluation. Explain why a change is needed and suggest improvements while keeping the code consistent with the concepts and tools covered in our course. Also review our README and report for clarity, reproducibility, and consistency with the actual implementation. Avoid making unsupported assumptions or inventing results."

**Review and verification:**

I reviewed the suggestions against our existing code, course concepts, and project requirements. I tested relevant code changes locally, checked model outputs and evaluation results, and verified that the rendered Quarto report and README accurately reflected the implementation.

## Tahir's Prompt

**AI tool / model used:** ChatGPT

**Task / context:** Understanding, reviewing, and improving the Titanic survival prediction project, including exploratory data analysis, data leakage prevention, cross-validation, model evaluation, and project documentation.

**Representative prompt:**

"I'm working on a DSCI 522 group project involving Titanic survival prediction. Act as a tutor and critical reviewer. Help me understand the existing code and methodology before suggesting changes. Review the implementation for potential issues such as data leakage, inappropriate train/test splitting, cross-validation, and model evaluation. Explain why a change is needed and suggest improvements while keeping the code consistent with the concepts and tools covered in our course. Also review our README and report for clarity, reproducibility, and consistency with the actual implementation. Avoid making unsupported assumptions or inventing results."

**Review and verification:**

I reviewed the suggestions against our existing code, course concepts, and project requirements. I tested relevant code changes locally, checked model outputs and evaluation results, and verified that the rendered Quarto report and README accurately reflected the implementation.