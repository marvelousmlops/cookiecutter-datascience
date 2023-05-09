# Data Science Project Template

A simple project structure for data scientists to begin a new project. It provides necessary files.
We keep the cookie cutter as simple as possible with focus on production and not development.

## How to use
- Go to workflows, run `Create Repo` workflow by providing the following inputs:
    - Repo name: Name of the repository you want to create. (must follow naming convention, starts with opco name e.g. maxi, dll, alfa-beta
    - Product name: Name of the data science product, e.g. personalized-offers, topn, search.
    - Operation team: Name of the team who owns the product, e.g. Data Science, MLOps.

## What it does
- `Create Repo` creates a repository with provided repo name, runs cookiecutter to render files, adds and commits them to the new repository. 


## 📖 Repository structure consist of following files:
    ├── README.md              <- The top-level README for developers using this project
    ├── main.py                <- Main script to run model flow (i.e. from raw data to predictions)
    ├── pre-commit-config.yaml <- Pre-commit hooks
    ├── .gitignore             <- File with 
    ├── requirements.txt       <- Requirements for production
    ├── .flake8                <- Configuration for flake8
    ├── pytest.ini             <- Pytest settings
    └── .github/workflows
        ├── CI.yml             <- Continues Integration to run tests and precommit
