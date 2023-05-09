# Data Science Project Template

A simple project structure for data scientists to begin a new project. It provides necessary files to run a simple job on Databricks.
- It uses [gso-ml-toolkit](https://github.com/RoyalAholdDelhaize/gso-ml-toolkit) to create Databricks job. 
- It uses [gso-github-toolkit](https://github.com/RoyalAholdDelhaize/gso-github-toolkit) to add new repository to the secrets scopes.

## How to use
- Go to workflows, run `Create Repo` workflow by providing the following inputs:
    - Repo name: Name of the repository you want to create. (must follow naming convention, starts with opco name e.g. maxi, dll, alfa-beta
    - Product name: Name of the data science product, e.g. personalized-offers, topn, search.
    - Operation team: Name of the team who owns the product, e.g. DRS, DLL.

## What it does
- `Create Repo` creates a repository with provided repo name, runs cookiecutter to render files, adds and commits them to the new repository. As a last step, it also triggers [add_repo_to_becse_org_secrets](https://github.com/RoyalAholdDelhaize/gso-github-toolkit/blob/master/.github/workflows/add_repo_to_becse_org_secrets.yml) pipeline with repo name as an input, to update secret scopes. Those secrets are organizational secrets, defined for each opco in Becse (Maxi, DLL, Mega-Image, Alfa-Beta) which authenticates our pipelines to interact with resources (Databricks, AKS, ACR etc.)


## 📖 Repository structure consist of following files:
    ├── README.md              <- The top-level README for developers using this project
    ├── main.py                <- Main script to run model flow (i.e. from raw data to predictions)
    ├── databricks_job.json    <- Databricks job json file
    ├── pre-commit-config.yaml <- Pre-commit hooks
    ├── .gitignore             <- File with 
    ├── requirements.txt       <- Requirements for production
    ├── mlops_config.yml       <- Model governance file with tags and jinja parameters
    ├── .flake8                <- Configuration for flake8
    ├── pytest.ini             <- Pytest settings
    └── .github/workflows
        ├── CI.yml             <- Continues Integration to run tests and precommit
        └── CD.yml             <- Deployment pipeline for databricks job