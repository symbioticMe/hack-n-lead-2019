# [Hack n Lead 2019](https://womenplusplus.ch/hacknlead)

===

## Steps

1. `Fork` this repository
2. Add your team members as contributors
3. Put your presentation in the `docs/` folder
4. This repository **must** be open source (and licensed) in order to submit

===

## Project outline
## The future of financial crime - Discovery

+++
DATA SOURCES

Data provided by CreditSuisse:
> 'large.csv'
> 'small.csv'
> 'country.csv'
> 'jeopardy.csv'

Open source data: 
1. Basel AML Index: independent annual ranking that assesses the risk of money laundering and terrorist financing around the world
https://www.baselgovernance.org/basel-aml-index/public-ranking
> 'AML_risk_ranking'

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


+++
DATA EXPLORATION

general statistics
- type of data
- structure and relationship of features

visualize data

+++
MODELS

Model choice: to understand the model's behaviour

DecisionTreeClassifier
CatBoost
SVM

Steps:
> train-test split
> upsampling of minority class in training set
> cross-validation on training set; aim: optimize f1_micro score (detect minority class)
> test with test set
> evaluation: classification report, ROC
