# Overview
This is the collab file to my Bachelor's thesis project. I am currently working in translating it and improving its documentation.
You can read more about the project and view my publication [here](https://vitela.javerianacali.edu.co/items/8088ca1c-a833-4e78-8e56-4b360e6270b6)

# Abstract
Medicine used for the treatment of leishmaniasis can be toxic and detrimental to health. Moreover, these treatments do not promise to cure the patient in all cases. To avoid prescribing these treatments to patients who will not benefit from them, several studies [4][7] have been done to try to predict, by means of blood metabolite samples, in which patients the treatment will be effective. In this project, a continuation of these studies was done, based on the same data used. These data looked at 535 attributes/metabolites for only 36 patients. The bulk of this project was in reducing the dimensionality of the data set (2 to 5 metabolites) and being able to arrive at results close to or better than the existing ones. Four different clustering models were trained to find possible groups and from each one choose a representative. For each model we searched for parameters that arrived at clusters with a better degree of separation. In the phase of choosing the representatives of each cluster, different metrics such as: proximity to the cluster center, or probability of being a member of the cluster, were used to decide which could be the best representatives. After having the representatives of each group, we moved on to the prediction phase, where we observed how good the prediction was with this small set of attributes. Finally, a model with 3 metabolites and an f1 score of 0.82 was arrived at, which was

# Sections:
## Scaling and Pre-Processing 
Here we scale the data since metabolites are found in varying quantities and the difference in units was creating noise.
We also found that there were metabolites that were highly correlated in a circular manner a -> b -> c -> a... To solve this, we implemented an algorythm that sorted all highly correlated variables by weighted average-correlation and that higher one was kept and the rest were removed from the set. 

## Clustering and Testing
There are two steps used for each clustering algorythm (KMeans, DBSCAN, Hierarchical and Gaussian Mixtures):
- Clustering methods are used to find groups then we test different ways of selecting representatives from each group like centrality or random selection to test which are better representatives.
- Selected representatives are tested as predictors using 3 prediction models (KNeighbors, Logistical Regression and Random Forest)
