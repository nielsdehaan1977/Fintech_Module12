# Fintech_Module12

![credit_risk_loans.jpg](https://github.com/nielsdehaan1977/Fintech_Module12/blob/main/Images/credit_risk_loans.jpg)

## Predict Risk with Supervised Learning. This notebook uses a dataset of historical lending activity from a peer-to-peer lending services company and uses logistic regression on both the original dataset and a resampled data set using RandomOverSampler from imbalanced-learn library. 

## credit_risk_resampling.ipynb
---

### This notebook can be used as a template to build a model that can identify the creditworthiness of borrowers using and imbalanced dataset (in this case more healthy than unhealthy loans) using supervised learning. 

The tool can help to write a credit risk analysis report.  
* The tool goes through on the following steps: 
1. Split Data into Training and Testing Sets
2. Create a Logistic Regression model with the Original (imbalanced) dataset
3. Predict a Logistic Regression model with Resampled (Balanced using RandomOverSampler) training data 
4. Compare Logistic Regression Models results
5. Provide an example Credit Risk Analysis Report

---
## Table of Content

- [Tech](#technologies)
- [Installation Guide](#installation-guide)
- [Usage](#usage)
- [Contributor(s)](#contributor(s))
- [License(s)](#license(s))

---
## Tech

This project leverages python 3.9 and Jupyter Lab with the following packages:

* `Python 3.9`
* `Jupyter lab`

* [JupyterLab](https://jupyter.org/) - Jupyter Lab is the latest web-based interactive development environment for notebooks, code, and data.

* [pandas](https://pandas.pydata.org/pandas-docs/stable/index.html) - Pandas is an open source, BSD-licensed library providing high-performance, easy-to-use data structures and data analysis tools for the Python programming language.

* [numpy](https://numpy.org/doc/stable/index.html) - NumPy is the fundamental package for scientific computing in Python.

* [balanced_accuracy_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.balanced_accuracy_score.html) - The balanced accuracy in binary and multiclass classification problems to deal with imbalanced datasets. It is defined as the average of recall obtained on each class.

* [confusion_matrix](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.confusion_matrix.html) - Compute confusion matrix to evaluate the accuracy of a classification.

* [classification_report_imbalanced](https://imbalanced-learn.org/dev/references/generated/imblearn.metrics.classification_report_imbalanced.html) - Build a classification report based on metrics used with imbalanced dataset.

---

## Installation Guide

### Before running the application first install the following dependencies in either Gitbash or Terminal. (If not already installed)

#### Step1: Activate dev environment in Gitbash or Terminal to do so type:
```python
    conda activate dev
```
#### Step2: install the following libraries (if not installed yet) by typing:
```python
    pip install pandas
    conda install -c conda-forge imbalanced-learn
    pip install -U scikit-learn
```
#### Step3: Start Jupyter Lab
Jupyter Lab can be started by:
1. Activate your developer environment in Terminal or Git Bash (already done in step 1)
2. Type "jupyter lab --ContentsManager.allow_hidden=True" press enter (This will open Jupyter Lab in a mode where you can also see hidden files)

![JupyterLab](https://github.com/nielsdehaan1977/Fintech_Module12/blob/main/Images/JupyterLab.PNG)


## Usage

To use the credit_risk_resampling jupyter lab notebook, simply clone the full repository and open the **credit_risk_resampling.ipynb** file in Jupyter Lab. 

The tool will go through the following steps:

### Import the Data
* Import of data to analyze

### Prepare the Data
* Split the data into Training and Testing Sets

### Create a Logistics Regression model with original data
* How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

### Create a Logistics Regression model with resampled training data
* How well does the logistic regression model, fit with oversampled data, predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

### Write a Credit Risk Analysis Report
* **Overview of the analysis:** Explains the purpose of the analysis.
* **Results:** Describes the balanced accuracy scores and the precision and recall scores of both machine learning models.
* **Summary:** Summary of the results from the machine learning models. Compares the two versions of the dataset predictions. Includes recommendations for the model to use, if any, on the original vs. the resampled data.


## Contributor(s)

This project was created by Niels de Haan (nlsdhn@gmail.com)

---

## License(s)

MIT
