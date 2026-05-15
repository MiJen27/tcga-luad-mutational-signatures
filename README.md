# TCGA-LUAD Smoking Mutational Signatures

This repository contains the split notebook workflow used for the TCGA-LUAD mutational signature analysis. The analysis focuses on the relationship between smoking status and mutational signature patterns in lung adenocarcinoma samples.

The analysis was performed using **Python 3.10.18**.

## Notebook order

1. `01_setup_environment.ipynb`
2. `02_sigprofiler_generation_and_fitting.ipynb`
3. `03a_merge_clinical_and_exposure.ipynb`
4. `03b_basic_cohort_plots.ipynb`
5. `04_unsupervised_signature_plots.ipynb`
6. `05_supervised_data_split.ipynb`
7. `06_supervised_balanced_random_forest.ipynb`

## Pipeline description

### 1. `01_setup_environment.ipynb`

This notebook sets up the working environment and checks that the required packages, folders, and input paths are available. It prepares the project structure needed for the following analysis steps.

### 2. `02_sigprofiler_generation_and_fitting.ipynb`

This notebook generates the SBS96 mutational matrix from TCGA-LUAD mutation data using SigProfilerMatrixGenerator. The generated matrix is then used for COSMIC mutational signature fitting with SigProfilerAssignment.

### 3. `03a_merge_clinical_and_exposure.ipynb`

This notebook merges clinical metadata with exposure information into one combined patient-level table. The resulting dataset contains selected clinical variables and smoking-related exposure variables used in later analyses.

### 4. `03b_basic_cohort_plots.ipynb`

This notebook creates basic cohort-level plots from the clinical and exposure data. These plots include descriptive visualizations such as smoking-status distribution and age distribution in the TCGA-LUAD cohort.

### 5. `04_unsupervised_signature_plots.ipynb`

This notebook performs exploratory analysis of mutational signature contributions. It includes heatmaps and visual comparisons of signature activities across smoking categories.

### 6. `05_supervised_data_split.ipynb`

This notebook prepares the supervised modelling dataset. It defines the binary smoking label, prepares patient-level SBS96 features, includes selected clinical covariates, and creates the train, validation, and test splits.

### 7. `06_supervised_balanced_random_forest.ipynb`

This notebook trains and evaluates a Balanced Random Forest classifier for distinguishing never-smokers from ever-smokers. The model uses SBS96 mutational-context features together with selected clinical covariates.
