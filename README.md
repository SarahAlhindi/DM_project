# DM_project  

## Names  
Sarah Waheed Alhindi 443200630  
Raneem Nasser Alyahya 443200702  
Shaug Majed Alyahya 443200888  
Shahad Shukri Bin Makhashen  443204385  

## Motivations: 
We are living in the “information age” or rather the “data age”, meaning that everything around us revolves around data. The data has become one of the most valuable assets that a person or an organization can have, Thus, most of the attacks nowadays are directed toward the data. To guard against such damage, organizations have realized the importance of protecting their digital assets, leading them to hire cybersecurity specialists. As a result, the demand for these professionals is higher now than ever before. In order to better understand this field, we decided to analyze a dataset of 1247 cybersecurity employees, containing information such as salary, job title, and experience level. Analyzing this dataset can provide insightful predictions regarding the salary range of cybersecurity employees.

## Summary
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
