# 📧 Spam Classification MLOps Pipeline

[![DVC](https://img.shields.io/badge/-Data_Version_Control-2d394b?style=flat-square&logo=dvc&logoColor=white)](https://dvc.org/)
[![Python](https://img.shields.io/badge/Python-3.13+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.8+-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)

This project demonstrates a production-ready MLOps pipeline for **Spam Classification** using **DVC (Data Version Control)** for orchestration and experiment tracking.

## 🚀 Overview

The goal of this project is to build a scalable and reproducible machine learning pipeline that classifies messages as "Spam" or "Ham". It leverages DVC to manage the end-to-end lifecycle, from data ingestion to model evaluation, ensuring repeatability and tracking across different versions.

## 🏗️ Pipeline Architecture

The pipeline is organized into five distinct stages, each managed by DVC:

1.  **Data Ingestion**: Fetches the raw dataset from a remote source and splits it into training and testing sets.
2.  **Data Preprocessing**: Cleans the text data (lowercasing, removing special characters) and handles initial formatting.
3.  **Feature Engineering**: Converts raw text into numerical features using TF-IDF vectorization.
4.  **Model Building**: Trains a Random Forest classifier based on the engineered features and parameters defined in `params.yaml`.
5.  **Model Evaluation**: Evaluates the model on the test set, generating performance metrics (Accuracy, Precision, Recall, F1-score) and plots.

## 🛠️ Tech Stack

- **Orchestration**: [DVC](https://dvc.org/)
- **Experiment Tracking**: [DVCLive](https://dvc.org/doc/dvclive)
- **Machine Learning**: Scikit-Learn
- **Data Manipulation**: Pandas, NumPy
- **NLP**: NLTK
- **Package Management**: UV / Pip

## ⚙️ Setup & Installation

### 1. Clone the Repository
```powershell
git clone https://github.com/agarwalson02/spam_classifies_pipeline_dvc.git
cd YT_MLOPS_Pipeline_DVC
```

### 2. Set Up Environment
It is recommended to use a virtual environment.
```powershell
# Using uv (faster)
uv venv
source .venv/Scripts/activate # Windows

# Or using pip
python -m venv venv
.\venv\Scripts\activate # Windows
pip install -r requirements.txt
```

### 3. Initialize DVC
```powershell
dvc init
```

## 🏃 How to Run

### Reproduce the Entire Pipeline
To run all stages of the pipeline:
```powershell
dvc repro
```

### View Pipeline DAG
To visualize the dependency graph:
```powershell
dvc dag
```

### Check Metrics
To view the latest model performance metrics:
```powershell
dvc metrics show
```

## 📊 Experiment Tracking
We use **DVCLive** for automatic logging of parameters and metrics during the training process. You can view the experiments and plots generated in the `dvclive/` directory.

## 📂 Project Structure

```text
├── .dvc/               # DVC configuration
├── data/               # Versioned data (raw, interim, processed)
├── dvclive/            # Experiment tracking metrics and plots
├── logs/               # Execution logs
├── models/             # Saved model weights (.pkl)
├── reports/            # Evaluation reports
├── src/                # Pipeline source code
│   ├── data_ingestion.py
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   └── model_evaluation.py
├── dvc.yaml            # DVC pipeline definition
├── params.yaml         # Configurable hyperparameters
└── pyproject.toml      # Project dependencies
```

---
*Created by [Antigravity AI](https://github.com/google-deepmind) 🚀*
