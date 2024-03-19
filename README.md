# Mental Health Disorder Prevalence

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)
- [References](#references)
 

### Project Overview
This project focuses on analyzing the global prevalence of mental health conditions spanning two decades, including depression and bipolar disorder. Its objectives are to investigate the average prevalence of these conditions worldwide, identify the global average prevalence, and pinpoint the country with the highest prevalence for each condition and corresponding year.


![image](https://github.com/Rodnah/MHDP/assets/147203468/464806ad-288c-4a73-a566-e558c1c126d9)


### Data Sources
The primary dataset was downloaded from [data.world](https://data.world/) as a CSV file. This CSV contains detailed information about various parameters within the dataset.

### Tools
1. Excel - Data Cleaning
2. SQL Server - Data Preprocessing
3. Tableau - [Data Visualization](https://public.tableau.com/app/profile/aminah.atobiloye/viz/HealthcareDashboards_17052101393530/Dashboard1)

### Data Cleaning
In the initial data preparation phase, I performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting.

### Exploratory Data Analysis
EDA involved exploring the data to answer critical questions, such as:
1. What's the average prevalence of mental health conditions?
2. What is the global average prevalence of mental health conditions?
3. Which country in the corresponding year had the highest prevalence of each mental health condition? 


### Data Analysis
Excerpt of some code worked with:
```sql
SELECT C.entity as Country,
       ROUND(AVG(b.anxiety_disorders), 2) as Avg_anxiety_disorders, 
       ROUND(AVG(p.schizophrenia),2) as Avg_schizophrenia, 
       ROUND(AVG(b.eating_disorders),2) as Avg_eating_disorders, 
       ROUND(AVG(b.drug_use_disorders),2) as Avg_drug_use_disorders,
       ROUND(AVG(p.bipolar_disorder),2) as Avg_bipolar_disorders,
       ROUND(AVG(p.depression),2) as Avg_depression,
       ROUND(AVG(b.alcohol_use_disorders),2) as Avg_alcohol_use_disorders
       
FROM `dda`.`behavioral_&_substance_related` b
JOIN `dda`.`country` c ON b.id = c.id
JOIN `dda`.`psychotic_&_mood` p ON c.id = p.id
GROUP BY Country;
```



### Results
The analysis results are summarized as follows:

1. Anxiety and schizophrenia have the highest and lowest prevalence rates, respectively.
2. Counties around the equator had lower mental health prevalence rates than other countries.
3. Depression was highest in 1995, anxiety was highest in 2002, alcohol and drug dependence in 2010 and 2017, respectively, bipolar and eating disorders in 2013 and 2016, and schizophrenia in 2006.

### Recommendations
Based on the analysis, I recommend the following actions:
1. Prioritize efforts to support individuals with anxiety disorders due to their high prevalence rates.
2. Investigate factors contributing to lower mental health disorder rates near the equator for potential insights into preventive measures.
3. Conduct further analysis to understand peak years, predict future ones, and tailor mental health policies to effectively target these disorders, providing timely and targeted interventions for optimal support and management.


### References
[data.world](https://data.world/)
