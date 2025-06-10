# Stacking_Classifier_Toxicity_Prediction

This repository contains a machine learning pipeline to predict the toxicity of molecules using RDKit-generated molecular descriptors and ensemble classification techniques. The pipeline was designed to work with large-scale chemical datasets and demonstrates robust performance when validated on FDA-approved drug molecules.


## 📌 Problem Statement

Predict molecular toxicity using structural and physicochemical properties derived from SMILES strings. The project leverages data-driven feature engineering and ensemble machine learning for accurate classification.


## 📊 Dataset

- **Source:** The dataset utilized in this study consisted of a total of 209,232 small molecules, including 74,412 non-toxic and 134,820 toxic compounds
- **Structure:** SMILES strings with binary toxicity labels.
- **Validation:** Separate validation on FDA-approved drug molecules (unseen during training).


## 🧪 Methodology

![Flowchart](https://github.com/user-attachments/assets/7df91d38-e782-4716-a5a0-317f8318ee17)


### 1. Exploratory Data Analysis
- Analyzed structural and chemical properties.
- Identified key differentiators between toxic and non-toxic molecules:
  - Molecular weight
  - Atom chain lengths
  - Functional substructures

### 2. Feature Engineering
- Generated **210+ molecular descriptors** using RDKit.
- Performed experiments on a subset of **20,000 molecules** to fine-tune the pipeline before scaling to the full dataset.

### 3. Feature Selection
- Two-step ranking strategy:
  - **Random Forest feature importance**
  - **Mutual Information scores**
- Top 40 features from each method were merged, resulting in the final set of **selected descriptors**.

### 4. Model Training
- Benchmarked models: SVM, Logistic Regression, Random Forest.
- Final model: **Stacking Classifier**
  - **Base models:** Random Forest, LightGBM, SVM
  - **Meta learner:** Logistic Regression

### 5. Evaluation
- **Training accuracy:** 94%
- **Validation on FDA dataset:** 91%



## 🚀 Results

- High accuracy across training and validation.
- Generalized well to real-world drug molecules.
- Demonstrated the effectiveness of stacked ensembles for imbalanced and high-dimensional data.



## 📁 Repository Structure

