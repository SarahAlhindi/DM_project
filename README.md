# DM_project  

## Names  
Sarah Waheed Alhindi 443200630  
Raneem Nasser Alyahya 443200702  
Shaug Majed Alyahya 443200888  
Shahad Shukri Bin Makhashen  443204385  

## Motivations: 
We are living in the “information age” or rather the “data age”, meaning that everything around us revolves around data. The data has become one of the most valuable assets that a person or an organization can have, Thus, most of the attacks nowadays are directed toward the data. To guard against such damage, organizations have realized the importance of protecting their digital assets, leading them to hire cybersecurity specialists. As a result, the demand for these professionals is higher now than ever before. In order to better understand this field, we decided to analyze a dataset of 1247 cybersecurity employees, containing information such as salary, job title, and experience level. Analyzing this dataset can provide insightful predictions regarding the salary range of cybersecurity employees. Also, the analysis groups cybersecurity employees based on shared characteristics, providing valuable insights for decision-making in the industry.

## Summary

### First steps
1. Define data mining task
2. Read and view dataset
3. Save original dataset
4. Describe dataset and attributes
5. Show sample of the dataset


### Missing values 
In this section we have written codes that aims to find missing values in the dataset. We concluded from the results that we have no missing values or NULLS in all of our attributes.

### Central tendency measures
We summerized our numeric attributes (salary, remote_ratio, salary_in_usd, and work_year) with some statistical measures. i.e: variance, mean, median, quartiles, maximum and minimum. 

### Graph visualization
In the graphs we used the box plot to see the variables distribution. 
We used salary_in_usd with 4 other attribute to see the distribution for each. 
Firstly, We noticed that there is a positive correlation between salaries and the level of experience, meaning that salaries tend to increase as experience levels go up. Secondly, we observed that in 2021, salaries were relatively similar among individuals, but in 2022, we observed a widening gap between them. Turning to employment type Our observation indicates that Full-Time (FT) positions offer higher salaries compared to other categories. Lastly, observation revealed that larger companies tend to offer higher salaries.

### Concept hierarchy generation for nominal data

The columns "company_location" and "employee_residence" have countries names and these attributes can be generalized to higher-level concept that is region to help understand and analyze the dataset better and improve algorithm performance and minimize overfitting.  

We used 7 regions as defined in the World Bank Development Indicators. These regions are:

1. East Asia and Pacific

2. Europe and Central Asia

3. Latin America & Caribbean

4. Middle East and North Africa

5. North America

6. South Asia

7. Sub-Saharan Africa

Note: UM (The United States Minor Outlying Islands) and AQ(Antarctica) don't belong to any of these regions, thus, they will be used as they are.


We have done Concept hierarchy generation for "job_title" as well to improve interpretation and scalability. Also, most job titles are essentially the same job but with different names, so we combined them into higher-level jobs titles. These titles are:

1.	Analyst
2.	Engineer
3.	Architect
4.	Manager
5.	Specialist
6.	Tester
7.	Lead
8.	Officer
9.	Researcher
10.	Consultant
11.	Other


### Encoding categorical data  
To deal with columns with character type we have encoded them, because most machine learning algorithms are designed to work with factors data rather than character data and it improves performance and Interpretability of data as well.

These columns are:
1.	experience_level
2.	employment_type
3.	employee_residence
4.	company_location
5.	salary_currency
6.	job_title
7.	company_size

For example, experience_level has become a factor with 4 levels,
1.	EN(Entry-level)
2.	MI(Mid level)
3.	SE(Senior level)
4.	EX(Executive level)


### Feature selection and dimensionality reduction
We excluded the salary and employment type columns from the model duo to redundancies and low variance. This leaves these columns to predict the salary_in_usd:
1. work_year
2. experience_level
3. job_title
4. salary_currency
5. employee_residence
6. remote ratio
7. company_location
8. company_size

### Finding and removing outliers
Through creating a box plot to visualize outliers for numeric attributes (remote_ratio, salary_in_usd, and work_year) then removing them to minimize noise and to get better analytical results when applying data mining techniques.
We noticed that remote_ratio and work_year have no outliers , while salary_in_usd have many exceptionally high values.


### Discretization  
We have divided the range of salary_in_usd into continuous intervals labeled and organized as concepts, to enhance interpretability and possibly avoid overfitting. 
1.	Very Low,
2.	Low
3.	High
4.	Very High
Now we can classify the employees’ salary into these intervals.


### Normalization  

The attributes that are numeric of the remaining attributes are work_year and remote_ratio, but these two have different scales, and to avoid giving one attribute greater weight, we must normalize them. We used Z-scaling to normalize them.


### Classification

We have developed and evaluated decision tree classifiers for the classification task using three distinct splitting criteria: 
1. Gini index
2. gain ratio
3. information gain. 

To ensure the reliability and robustness of our classifiers, we applied k-fold cross-validation for partitioning the data into training and test sets. This was done using three different fold sizes: 10, 5, and 3.  
  
We tested the performance of each method using the following metrics:
1. Accuracy: Percentage of test set tuples that are correctly classified
2. Precision(also know as exactness): What % of tuples labeled as positive are actually positive.
3. Sensitivity (also known as Recall): The proportion of actual positive cases that were correctly identified.
4. Specificity: The proportion of actual negative cases that were correctly identified.

We concluded that 10-fold cross-validation using the gain ratio criterion yielded the best performance for our dataset.


### Clustering

Data clustering is a process to partition data into groups or clusters, it is an unsupervised learning process, which is excuted without knowing the class label of the training data. And for this data mining task We used k-means clustering.

First we prepreocessed our data and transformed the rest of attributes into numeric types before clustering, enabling meaningful distance calculations using kmeans and other formulas, and allowing for maximum flexibility in data processing and interpretation. 
Also we removed the class label from the dataset as clustering is an unsupervised learning process.
And lastly we scaled all attributes.


After that we chose 3 different numbers to perform the k-means clustering using silhouette method to find the optimal number of clusters k and also we used elbow method to determines the number of clusters according to the turning point in a curve, and Lastly chose 2 which strikes a balance between having too few clusters (k=2), and having several clusters (k=4).
So we chose 2 , 3 and 4 as numbers of clusters.

Then we performed k-means clustering and visualize its result using three different k’s that have been chosen beforehand, and we compute WSS and Bcubed preceision and recall and average silhouette for each cluster as methods of evaluating clustering results. 

We can conclude from the graph and the results where k=2 is that the performance is the best, better than k=3 and k=4 because k=2 is the optimal k, since there is no overlapping between the two clusters, and the data in a cluster are close “similar” to each other and dissimilar to data in the other cluster.
