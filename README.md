# COMPAS Recidivism Differentially Private Analysis
Colin Furch and Alex Stute

We plan on examining the impact of differentially private algorithms on the COMPAS Recidivism dataset. 
The problem we intend to solve is effect of DP algorithms on the accuracy of datasets (other than the adult dataset with which we have previously examined).
Our analysis will include implementations of synthetic represenation, as well as comparisons between Zero-Centered, Renyi, and Epsilon-Delta differential privacy. 

## Analysis

### Data/Chosen Variables
For our chosen data there are a few terms and variables that should be mentioned. We continued to utilize the adult dataset as a basis for comparison for the accuracy of our differentially private algorithms. However, the COMPAS dataset is not consistent with row-per-user privacy, and has to be adjusted as such. In order to provide user-level privacy, we needed to limit the contributions and modify our sensitivity. We decided on a maximum user contribution of 15 custody dates, and modified our sensitivity to reflect this.
Ideally we would also implement a clipping mechanism to prevent a user from exceeding this value.

### Synthetic Data
Alex Stute

### Alternative Algorithms
Colin Furch

During my analysis I decided to focus on comparing the accuracy and percent error of queries across a column that was shared between Adult and COMPAS data sets, namely ages. One thing is observable almost immediately is the impact of the sensitivity on the accuracy of the queries, especially with the $\epsilon,\delta$-algorithm.


# Datasets
https://www.kaggle.com/datasets/danofer/compass
https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm

# TODO:
Synth Rep - 
Comparison of accuracy Adult Dataset and COMPAS Dataset

DP Definitions - 
zCDP/Renyi/Epsilon Delta of COMPAS vs ADULT
