# Project Four: Social Impact
### Group: Git Real
#### Team Members:
- Matt Reed
- Blago Ugrinov
- Sabrina Starr
- Dan Costa


### Executive Summary

Are US state economies distinct enough by employment sector to be clustered? Can these clusters provide insight into which US states or state economies are most resilient?

### Background

**Matt**

---

### File Structure

```
project
│    Data Dictionary.md
│    README.md
│    00 - Data Collection.ipynb
│    01 - Clustering.ipynb
│    02 - Cluster Merge.ipynb
│    03 - EDA.ipynb│
│
└──Development
│    Contains working versions of the notebooks
│         
│   
└──source_data
│    Datasets generated in the Data Collection and Clustering notebooks
│
│
└──state_data
│    HTML files by state and industry
│
│
└──state_employment
│    Employment files by state 
│      
│    
│          
└──state_metrics
     quarterly_personal_income.csv
     quarterly_real_gdp.csv
     yearly_pop_pcpi_employment.csv
```
---


### Data Formatting and Modeling

**Dan** - 
Data Scraping
Data Cleaning & Transforming



For Clustering
As a group we were extremely fascinated by the pure concept of what clustering was as an unsupervised learning technique. When we looked through all the available data we thought it would be interesting to see what kind of relationships a model would form between the different US states and if these relationships could predict anything or provide any insight of significance. Now that we finally completed the long and arduous process of pulling and organizing this state economic industry data we got our reward!
The clustering was done completely based on the data broken down by economic industry. The different states were set as the dataframe index (51 including District British Columbia) and there were 11 features, 10 distinct industries, and 1 as total non-farm which was essentially the sum of the others. From here all the data was scaled with a standard scaler and fed into for loops designed to determine the best clustering method and amount of clusters. The KMeans loop ran through possible clusters from 2 - 25 and kept running track of the silhouette scores. A loop for Kmeans also ran to calculate and plot inertia scores in order to find the ideal elbow point of diminishing returns. The DBScan for loop ran through various epsilons and minimum samples per cluster to find the best possible silhouette score for cluster of 2 or more. Kmeans had a good margin the better and more cohesive scores. The inertia elbow gave us wiggle room as to which breakdown of 3, 4, or 5 we would choose as the scores were all good and relatively close. We chose 5 clusters as we believed this would lead to more interesting analysis and eda with more granular groupings of states.


For EDA, we were able to input all of the clustering data into pivot tables for visualization. We started with looking at the unemployment rate as a way to analyze how well the economy was doing. The EDA was done post kmeans clustering. We had 5 total clusters. In the first cluster was Alabama, Arizona, Colorado, Indiana, Kentucky, Louisiana, Maryland, Massachusetts, Minnesota, Missouri, Oregon, South Carolina, Tennessee, Washington, Wisconsin. In the second cluster was Florida, New York, Texas. In the third cluster was Georgia, Illinois, Michigan, New Jersey, North Carolina, Ohio, Pennsylvania, Virginia. In the fourth cluster was Alaska, Arkansas, Connecticut, Delaware, District of Columbia, Hawaii, Idaho, Iowa, Kansas, Maine, Mississippi, Montana, Nebraska, Nevada, New Hampshire, New Mexico, North Dakota, Oklahoma, Rhode Island, South Dakota, Utah, Vermont, West Virginia, Wyoming. In the fifth cluster was just California. 

We observed a very large spike in unemployment rates during covid, looking at about a 10-15% unemployment rate increase across all clusters. The second cluster of states by far has the largest overall unemployment rate across ass industries. 

Overall the model seems to have clustered according to the rate of unemployment. California seems to have been an outlier because there was the least amount of data available.

Because of this EDA, we could argue that if the model clustered according the unemployment rate, that cluster 1 (0 in our jupyter notebooks) seems to be the most economically stable states. But causality is hard to conclude in this region because there are a few potential factors:
1. Population. The population in the more economically stable regions seems to be less than those grouped in the second cluster. We could argue that a large reason their unemployment rate is lower is because they have fewer people.
2. Dominant industry present. The most dominant industry in the cluster 1 group seems to be that of farming type industries. Because of this, we can conclude the areas are probably more rural. This means that maybe the population is living father apart from one another, extracting covid as a lesser rate, and therefore the state's economy being less effected by the pandemic. 
3. Age. Age could potentially play a part in the unemployment rate. If the states in cluster 1 have a higher aged population, their unemployment rate may be deemed as more steady because less of the population was employed to begin with.

Overall EDA uncovered many different avenues to possibly venture in the future. 

---

### Observations

**Collectively**
Discuss Findings

---

### Next Steps

**Collectively**
List these here
