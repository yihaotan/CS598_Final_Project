# Reproducibility README for "An Extensive Data Processing Pipeline for MIMIC-IV"

## Citation
Johnson AE, Pollard TJ, Shen L, Lehman LW, Feng M, Ghassemi M, Moody B, Szolovits P, Celi LA, and Mark RG. MIMIC-IV (version 0.4), a large, publicly available database for research in critical care. Nature Scientific Data, 2021.

## Link to the original paper's repo
https://github.com/healthylaife/MIMIC-IV-Data-Pipeline

## Dependencies
- Python (v3.6 or higher)
- Python packages listed in requirements.txt
- IDE such as VSCode

## Environment setup
1. Clone this repo.
```
git clone https://github.com/yihaotan/CS598_Final_Project.git
```
2. Create and activate a virtual Python environment.
```
python -m venv venv 
source venv/bin/activate
```
3. Install the Python packages in requirements.txt
```
pip3 install -r requirements.txt
```
4. Navigate to the `mainPipeline.ipynb` Jupyter notebook

5. Run the Jupyter notebook

Since the mimiv-iv dataset is already present in /mimiciv directory, run the Jupyer notebook with the following parameters. The numbers below represent the steps in the Jupyter notebook.
1. Data Extraction: Version 1, Mortality, ICU, Heart Failure
2. Features selection: Diagnosis and Chart Events (Labs and Vitals)
3. Clinical Grouping: Convert ICD-9 to ICD-10 and group ICD-10 codes
5. Feature selection: Yes, Yes
6. Cleaning of features: Remove outliers (Default: 98)
7. Time-Series Representation: First 72 hours, 1 hour, No imputation, 2 hours
8. Machine Learning Models: Logistic Regression, Concactenate, No CV, False


## Data download instruction
1. Register for access to the MIMIC-IV database at https://mimic-iv.mit.edu/access/.

2. Follow the instructions provided to download the necessary files for the version of MIMIC-IV you plan to use.

3. Extract the downloaded files to a folder on your local machine.


## Table of results

| Metric             | Baseline        | Model 1        |
| ------------------ |---------------- | -------------- |
| BCE Loss           |    9.46         |   8.22         |
| AU-ROC             |    0.60         |   0.58         |
| AU-PRC             |    0.20         |   0.23         |
| AU-PRC Baseline    |    0.13         |   0.14         | 
| Accuracy           |    0.80         |   0.81         |
| Precision          |    0.23         |   0.28         |
| Recall             |    0.25         |   0.23         |
| Specificity        |    0.88         |   0.90         | 
| NPV                |    0.89         |   0.88         |
| ECE                |    0.16         |   0.15         |
| MCE                |    0.75         |   0.66         |
