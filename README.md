# MMM Workflow Automation

[![Python Version](https://img.shields.io/badge/python-3.12%2B-blue.svg)](https://www.python.org/downloads/)
[![Poetry](https://img.shields.io/endpoint?url=https://python-poetry.org/badge/v0.json)](https://python-poetry.org/)
[![PyMC](https://img.shields.io/badge/PyMC-Bayesian_Modeling-blue.svg)](https://docs.pymc.io/)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B.svg)](https://streamlit.io/)

Infrastructure for automating the Marketing Mix Modeling (MMM) process using Claude Code Workspace agents.

---

## 📖 Table of Contents
1. [What does the project do (so far)?](#1-what-does-the-project-do-so-far)
2. [How is the project used so far?](#2-how-is-the-project-used-so-far)
3. [How to set up a virtual environment?](#3-how-to-set-up-a-virtual-environment)
4. [How to install and set up the project with Poetry?](#4-how-to-install-and-set-up-the-project-with-poetry)
5. [Why do we use Poetry?](#5-why-do-we-use-poetry)

---

## 1. What does the project do (so far)?

The project provides an initial infrastructure to create a Workspace agent with Claude Code aimed at automating the **Marketing Mix Modeling (MMM)** process. Through the configured Python libraries, it supports:

- **Data Cleaning, Validation, and Transformation**: Powered by `pandas`, `numpy`, and `pandera`.
- **MMM Model Training and Evaluation**: Powered by probabilistic and Bayesian libraries like `pymc` and `arviz`, supported by traditional machine learning tools like `scikit-learn`.
- **Deployment and Data/Model Visualization**: Using static and dynamic charts with `matplotlib`, `seaborn`, and `plotly`, all wrapped in an interactive web application built with `streamlit`.

Currently, the project configures the main ecosystem under the rigorous versioning and dependency resolution standards required in modern Data Science.

## 2. How is the project used so far?

At this stage, the project does not contain production code logic. The usage so far focuses on environment setup:
1. Downloading (or cloning) the repository.
2. Isolating and reproducing the necessary core dependencies to start development.
3. Having the foundations ready to start creating or including your own ETL scripts, PyMC training scripts, and Streamlit app views.

## 3. How to set up a virtual environment?

We recommend using Python's built-in `venv` module. 

> **Note**: During the initialization of this project, the automatic creation of internal virtual environments by Poetry was deliberately disabled to allow users to manage their environment manually.

1. Ensure you have Python installed (`>= 3.12`, `< 3.15`).
2. Open your terminal in this directory and run:
   ```bash
   python3 -m venv .venv
   ```
   *(You can replace `.venv` with your preferred virtual environment name).*
3. Activate the virtual environment:
   - **macOS / Linux**: 
     ```bash
     source .venv/bin/activate
     ```
   - **Windows**: 
     ```bash
     .\.venv\Scripts\activate
     ```

## 4. How to install and set up the project with Poetry?

First, you need to have the Poetry CLI installed.
```bash
# Recommended by Poetry:
pipx install poetry

# Or via regular pip:
python3 -m pip install poetry
```

Then, ensure your virtual environment is activated (see section 3) and run the following command in the root directory (where `pyproject.toml` is located):
```bash
poetry install
```

By doing this, Poetry will instantly read the dependencies configured in both `pyproject.toml` and `poetry.lock`, resolve all packages, ensure their versions are compatible, and seamlessly install them into your environment.

## 5. Why do we use Poetry?

Poetry is a powerful, modern alternative to the traditional Python ecosystem pattern (e.g., `requirements.txt` + `setup.py`):

1. **Intelligent Conflict Resolution**: Poetry proactively detects conflicts and warns you if a library is incompatible with others. For example, it effortlessly handles the specific Python and Pandas version constraints required by libraries like `pymc` and `streamlit`.
2. **100% Deterministic and Reproducible (Locking)**: By automatically generating a `poetry.lock` file, Poetry records the *exact and fixed* versions of your entire dependency tree. Anyone who clones this repository will install exactly the same environment, eliminating the "works on my machine" problem.
3. **Single File Configuration (`pyproject.toml`)**: We consolidate environment needs, metadata, and extra tool configurations into a single, standardized file, instead of having multiple scattered configuration files.
