# MLOps Project 1: Boston Housing Price Forecast



This project provides an automated end-to-end machine learning pipeline designed to forecast property values utilizing the classic Boston Housing dataset. The implementation relies on standard regression algorithms from the scikit-learn library.

---

## Repository Layout

| Branch Name | Core Files | Algorithm |
| --- | --- | --- |
| `main` | `README.md` | None

 |
| `dtree` | `train.py`, `misc.py`, `requirements.txt` | DecisionTreeRegressor

 |
| `kernelridge` | `train2.py`, `misc.py`, CI workflow | KernelRidge

 |

The core logic for handling data—including loading, preprocessing, model training, and evaluation—is centralized within the `misc.py` module. These functions are written generically to support any regression model compatible with scikit-learn.

---

## Setup Instructions

1. Initialize and activate a new conda environment running Python 3.11:


```bash
conda create -n mlops python=3.11 -y #[cite: 1]
conda activate mlops #[cite: 1]

```



```

2. Install the necessary Python packages[cite: 1]:

   ```bash
   pip install -r requirements.txt #[cite: 1]

```

---

## Execution Guide

To train and assess the Decision Tree implementation, execute the following command:

```bash
python train.py #[cite: 1]

```

To run the Kernel Ridge model pipeline, execute:

```bash
python train2.py #[cite: 1]

```

> **Note:** Upon execution, both scripts will output the Mean Squared Error (MSE) on the test data alongside the average MSE derived from 5-fold cross-validation.
> 
> 

---

## Automated Testing (CI/CD)

A continuous integration pipeline is configured via GitHub Actions (`.github/workflows/ci.yml`). This workflow triggers automatically whenever new commits are pushed to the `kernelridge` branch. It handles code checkout, environment setup, and executes both `train.py` and `train2.py`, printing the evaluation metrics directly into the GitHub Actions console logs.