# MD_MCRI_b2f_challenge
### Repo for the analysis with the data shared by MCRI and MD for the B2F challenge.

<p>proteomics_challenge.py contains all the code used to perform the analysis.</p>

<p>A first pre-processing step with a **variance stabilizing normalization** is executed.</p>

<p>Afterwards a **PCA** is executed and the resulting components used as input for **t-SNE**.<br>
t-SNE is a dimensionality reduction algorithm very useful for mapping and visualizing how data is organized in human readable dimensions (2 and 3). The power of t-SNE helps to understand visually if and how data aggregates in similar groups.<br>
Afterwards in order to have a way to detect pòssible groups in a more robust way, a k-means is executed on top of the t-SNE results. This unsupervised learning algorithm will help us to classify our data in different groups, clusters.<br>
In order to find the optimal number of k-means clusters we use the elbow method to search between 1 and 15 clusters.</p>

This script can now be edited and used in other proteomics datafiles with the same structure as the challenge dataset.

## Note:

<p>Given the small size of the dataset of the challenge certain, more sensitive parameters for t-SNE have been set manually.<br>
  Assuming high throughput data will have a size in the order of hundreds or thousands times bigger these parameters are recommended to use at least the default values or even advisable to set them a bit higher. The parameters are the following:<br>
  - perplexity: *used*: **5** | *recommended*: **default** or for seriously large datasets **50<**;<br>
  - learning_rate: *used*: **15** | *recommended*: **default**;<br>
  - angle: *used*: **0.2** | *recommended*: **default** or for large data consider raising it a bit higher. This parameter is a tradeoff between accuracy and speed. The lower the value the more time t-SNE will take to run. For a very large ammount of data using a value closer the upper bound should still produce good results.</p>


