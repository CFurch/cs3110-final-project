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

During my analysis I decided to focus on comparing the accuracy and percent error of queries across a column that was shared between Adult and COMPAS data sets, namely ages. 

In order to be able to draw conclusions from my analysis I made a few concessions, epsilon would remain consistent between $(\epsilon,\delta)$-DP and RDP, while $\rho$ would remain at a fairly low $.0001$ for zCDP. As I was using age, I settled on using a sensitivity of 100, and clipped my queries as such.
Queries were conducted 100 times each, then compared to the real results of their respective datasets.

From my analysis I noticed that $(\epsilon,\delta)$-DP provided accuracy that was consistently lower than RDP or zCDP across all datasets. Renyi then provided fairly high accuracy, followed by zCDP, though the estimation of rho in these tests is likely a culprit here.

Most notably however is the difference in accuracy between the two datasets. The COMPAS dataset using the same algorithms provided consistently worse accurcy across the queries, with the percent error roughly around 3 times higher. This error is interesting as it reveals potential limitations of differentially private algorithms for universal applications.


# Datasets
https://www.kaggle.com/datasets/danofer/compass
https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm
