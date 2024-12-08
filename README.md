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

In my analysis, I focused on using synthetic representations and synthetic data to examine the correlation between race and decile score of a person in the dataset. To start, I created a one-way marginal for decile scores so that their accuracy to the actual scores could be compared. This one-way marginal gets the count of all the possible decile scores and creates a normalized synthetic representation. The accuracy of this representation was then compared to the actual data by creating synthetic decile_score data from the representation and calculating the percent error present for each decile score value.

Next, a two-way marginal was created between race and decile score. This was done by first creating a one-way marginal for race, then that was used alongside the decile scores to create a two-way marginal. This two-way marignal was then used to create decile score distributions for each race in the dataset. The findings from the synthetic data seem to match the given analyzed solution through Propublica, with African-American people tending to have a higher decile score than Caucasians, who see a sharp drop off in decile scores overall.

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
