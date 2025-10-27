# U.S. 2020 Election Demographics & Voting Analysis  

This repository contains an advanced **data science project** analyzing the **2020 U.S. General Election**.
Originally completed as part of a Master’s coursework with a **Pennsylvania-only dataset**, then became a personal project and was **expanded into a nationwide analysis** to provide deeper insights into demographic and voting patterns.  

Voting data too large to upload (even .zip) to Github, 51 state and D.C. files available at:
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/NT66Z3
(See notes in py notebook "Import MEDSL data (3 of 3)." Certain files were downloaded directly from state.gov websites for various reasons)

---  
## Project Overview  

* **Initial Study (Pennsylvania-only)**  
  * Combined data from the U.S. Census, Pennsylvania Redistricting Commission, and MIT Election Data & Science Lab.  
  * Pennsylvania was chosen for its nearly even Democrat/Republican split.  
  * Due to misalignment between **census blocks and voting precincts**, precise merging was only possible at the **county level**, leaving **67 clean records** for analysis.  
  * This constraint limited statistical power, and results were **unexpected**, prompting expansion.  

* **Expanded Study (Nationwide)**  
  * Combined U.S. Census and MIT Election Data & Science Lab files to analyze **all 50 states plus the District of Columbia**.  
  * Allowed for **much richer statistical analysis** and confirmation of predictors of party affiliation across the U.S.  
  * Used advanced statistical and machine learning methods to identify demographic factors most strongly associated with voting outcomes.  

---  
## Repository Structure  
```
project_on_2020.ipynb     # Main analysis notebook
Data_folder/ 
├── raw/                  # Raw input data
│   ├── Census DP1 data
│   ├── Census P2 data
│   ├── census_metadata.csv 
│   └── ...
├── processed/            # Cleaned or merged datasets for analysis
│   ├── DHC_tidy
│   ├── PUR_tidy
│   ├── MEDSL_tidy
│   ├── MERGED_DF.csv
│   ├── VOTE_DF.csv
│   └── ...
```
* **raw**: Original input files (census data, state-level election results, metadata).  
* **processed**: Clean datasets produced during analysis. (Users may skip preprocessing and start directly with these files.)  

---  
## Methodology  

1. **Data Preparation & Cleaning**  
   * Merged U.S. Census, state election results, and districting data.  
   * Resolved mismatches between census blocks and voting precincts by aggregating to **county-level records**.  
   * Created final analysis datasets at both the Pennsylvania and nationwide levels.  

2. **Exploratory Data Analysis (EDA)**  
   * Examined demographic distributions (age, income, education, race, urban/rural).  
   * Visualized voting patterns and turnout rates.  
   * Identified correlations between demographics and party outcomes.  

3. **Modeling Approaches**  
   * **Unsupervised Learning** – clustering demographics to explore hidden voter groupings.  
   * **Logistic Regression** – predicting likelihood of Democratic vs Republican vote share.  
   * **Classification Models** – Decision Trees, Random Forests, and Lasso Regression for feature selection.  
   * **Multivariate Analysis (MANOVA)** – testing multivariate relationships across demographic predictors.  

4. **Evaluation**  
   * Cross-validation with **StratifiedKFold**.  
   * Model accuracy, precision, recall, F1, ROC-AUC.  
   * Feature importance analysis with **permutation importance** and **partial dependence plots**.  

---  
## Tech Stack  
**Language & Environment**  
   * Python (Jupyter Notebook)  

**Core Libraries**  
   * **Data Handling**: `pandas`, `numpy`, `collections.Counter`  
   * **Visualization**: `matplotlib`, `seaborn`, `PartialDependenceDisplay`  
   * **Statistics**: `scipy.stats`, `statsmodels` (including MANOVA, VIF)  
   * **Machine Learning**:  

   * Models: `LogisticRegression`, `DecisionTreeClassifier`, `RandomForestClassifier`, `LassoCV`  
   * Preprocessing: `StandardScaler`, `MinMaxScaler`  
   * Evaluation: `train_test_split`, `cross_val_score`, `confusion_matrix`, `classification_report`, ROC/AUC metrics  
   * Feature Selection: `RFECV`, permutation importance  

---  
## Key Takeaways  
* **Pennsylvania-only analysis** showed the challenges of small-sample modeling after discovery that there was no accurate way to match census blocks with precincts.  
* **Nationwide analysis** provided a more robust dataset, allowing for stronger conclusions on which demographic factors most strongly associate with party affiliation.  
* Demonstrated ability to:  
   * Integrate disparate large-scale datasets.  
   * Apply **both statistical and machine learning techniques**.  
   * Communicate findings through clear visualizations and structured reporting.  

---  
## Next Steps  

Future improvements could include:  

* Incorporating **geospatial analysis** at precinct or district levels.  
* Using **time-series election data** (past election cycles) to identify demographic shifts.
* Include economic demographics (e.g. income and education) in analysis

---  
This project represents a **milestone in my transition from coursework to independent data science research**.
---
