# bioinformatics-bipolar-drug-discovery
This repository aims to leverage bioinformatics techniques to explore proteins related to bipolar disorder, focusing on the protein Norepinephrine transporter.

## Background
This is a drug discovery project which focuses on [Norepinephrine](https://my.clevelandclinic.org/health/articles/22610-norepinephrine-noradrenaline). It is involved with the mood disorder, Bipolar Disorder (BD). 

## Data Collection and Processing
The data is obtained from the ChEMBL Database using the chembl web service package in Python. The specific protein chosen is the Norepinephrine transporter, with the chembl id: CHEMBL222 and target organism: Homo sapiens. <br> 
To preprocess the data: <br> 
- the standard values are first checked if they are all IC50 type
- the missing values were handled
- compounds were labeled (active, inactive, or intermediate).

## Exploratory Data Analysis (EDA)
To explore the data: <br>
- descriptors were calculated using Lipinski descriptors (set of rules to evaluate the druglikeness of a compound)
- for uniform distribution of data, IC50 is converted to pIC50 with log transformation
- this analysis focused on the active and inactive bioactivity classes
- for statistical analysis, Mann-Whitney U Test is used

## Feature Engineering
Using PaDEL Descriptor, fingerprint descriptors were calculated. The dataset for model development is prepared here.

## Model Development and Evaluation
Based on model comparison, LGBMRegressor is the best model for the dataset. <br>
- R-Squared: 0.43
- Adjusted R-Squared: 0.56
- RMSE: 0.82

## Conclusion
In conclusion, this project explored the biological data of Norepinephrine transporter using the drug discovery process in bioinformatics. From the analyzed descriptors in this dataset, the fact that LogP does not show a significant difference between the 'active' and 'inactive' groups suggests that hydrophobicity is not a key factor in determining bioactivity for this particular target. In this case, other molecular properties or structural features may play a more critical role in driving the observed activity. <br> <br>

_Note:_ The model built is not yet exported with pickle. Further hyperparameter tuning and data preprocessing is recommended for higher R-Squared.

### References
[Drug Discovery Using Machine Learning - Data Professor](https://www.youtube.com/watch?v=jBlTQjcKuaY&t=5075s) <br>
[PaDEL-Descriptor Website](http://yapcwsoft.com/dd/padeldescriptor/) <br>
[Noradrenaline plays a critical role in the switch to a manic episode and treatment of a depressive episode](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5036557/)
