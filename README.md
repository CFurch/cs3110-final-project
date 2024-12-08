# COMPAS Recidivism Differentially Private Analysis
Colin Furch and Alex Stute

We plan on examining the impact of differentially private algorithms on the COMPAS Recidivism dataset. 
The problem we intend to solve is effect of DP algorithms on the accuracy of datasets (other than the adult dataset with which we have previously examined).
Our analysis will include implementations of synthetic represenation, as well as comparisons between Zero-Centered, Renyi, and Epsilon-Delta differential privacy. 

## Analysis

### Data Pre-Processing
In order to gain accurate insights and to provide user-level privacy, several changes had to be made to the dataset. The data as provided had several rows which had nearly identical data, with the only differences being custody dates which had no impact on the recidivism or decile scores. This pre-processing significantly improves accuracy of later queries by reducing the necessary sensitivities which would otherwise make much of the data unusable. 
We also did some minor de-identification with the removal of names and date of birth as it would not be necessary in most cases for analysis.

### Synthetic Data
Alex Stute

### Alternative Algorithms
Colin Furch

During my analysis I decided to focus on comparing the accuracy and percent error of queries across a column that was shared between Adult and COMPAS data sets, namely ages. There is a noticeable difference


# Datasets
https://www.kaggle.com/datasets/danofer/compass
https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm

# TODO:
Synth Rep - 
Comparison of accuracy Adult Dataset and COMPAS Dataset

DP Definitions - 
zCDP/Renyi/Epsilon Delta of COMPAS vs ADULT
