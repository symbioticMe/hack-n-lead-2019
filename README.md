# [Hack n Lead 2019](https://womenplusplus.ch/hacknlead)

Our team chose the project from Credit Suisse, and developed a machine learning tool identifying clients that are likely to be involved in money laundry activities and to tell them apart from good clients.
===

## Repository structure

- clean_code: notebooks with the final code producing important results
- notebooks: exploritary notebooks which are not included in final result
- laundrywomen_presentation: our pitch presentation

===

## Project outline
## The future of financial crime - Discovery

+++
DATA SOURCES

Data provided by CreditSuisse:
> 'large.csv' (http://bit.ly/36jCXYi)    
> 'small.csv' (http://bit.ly/33kJboM)  
> 'country.csv' (http://bit.ly/36nQ5f4)  
> 'jeopardy.csv' (http://bit.ly/2NCgFZ8)

Open source data: 
1. Basel AML Index: independent annual ranking that assesses the risk of money laundering and terrorist financing around the world
https://www.baselgovernance.org/basel-aml-index/public-ranking
> 'AML_risk_ranking.csv'

2. Corruption Perceptions Index 2018 by Transparency International: ranks 180 countries by their perceived levels of public sector 
corruption according to experts and businesspeople
https://www.transparency.org/cpi2018
> 'corruption_index_cross-over.csv'


+++
DATA PRE-PROCESSING

- Feature augmentation
log and norm transformations

- Introduced 4 categories:
0: Normal individual
1: Company
2: Other institution
3: is_pep individual

- Adding new features from external sources   
0: AML risk score and rank for countries   
1: Corruption index for countries   


+++
DATA EXPLORATION

general statistics
- type of data
- structure and relationship of features

visualize data

test outlier detection method LOF

+++
MODELS

Model choice: to understand the model's behaviour

DecisionTreeClassifier
CatBoost
SVM

Steps:
- train-test split
- upsampling of minority class in training set
- cross-validation on training set; aim: optimize f1_micro score (detect minority class)
- test with test set
- evaluation: classification report, ROC

+++ 
INTERPRETATION

- Visualization feature importance from CatBoost and DecisionTree
- Plotting distribution of most important features
- 2D-distribution of highly interaction features
- Confirming / rejecting hypothesis about external data sources (+ CIP, - AML)
- Usual outlier detection method (LOF) is not suitable to detect suspicious behaviour
