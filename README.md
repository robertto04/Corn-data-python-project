# Agri-data-analysis

## Table of Contents
- [Project overview](#project-overview)
- [Data source](#data-source)
- [Tools](#tools)
- [Data exploration](#data-exploration)
- [Data cleaning](#data-cleaning)
- [Feature engineering](#feature-engineering)
- [Data analysis](#data-analysis)
- [Findings](#recommendations)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)
 
## Project Overview
This project aims to analyze the agricultural practices of farmers in Taita Taveta county and identify the key factors that influence their productivity. By examining variables such as education, gender, age bracket, crop details, acreage, fertilizer usage, laborers, and yield, we seek to uncover patterns and insights that can inform strategies for improving agricultural productivity in the region.

![taita](https://github.com/robertto04/Corn-data-python-project/assets/46019410/f334e888-8fd7-4368-82d8-d49c6a2ebe5e)


## Data Source
The dataset used for this project can be found here: [corn_data](https://www.kaggle.com/datasets/japondo/corn-farming-data)

## Tools
- Python
   - Data cleaning
   - Data analysis
- Tableau
   - Creating reports

## Data Exploration
1. What are the dimensions of the dataset?
2. What are the data types of each column?
3. Are there missing values?
4. What is the distribution of numerical variables?
5. Are there any outliers?
6. How are categorical variables distributed?
7. Are there any correlations between variables?

## Data Cleaning
In the initial data cleaning phase, I performed the following tasks:
  1. Handling with missing data.
  2. Handling outliers.

## Feature Engineering
I created two new columns;
1. Fertilizer_per_acre; fertilizer used divided by the acreage
2. Yield_per_acre; yield divided by the acreage

## Data Analysis
```python
# average yield per acre
data.Yield.sum()/data.Acreage.sum()

# What is the average amount of fertilizer used per acre
data.Fertilizer_per_acre.mean()

# correlation between fertilizer usage and yield
data[['Fertilizer_per_acre', 'Yield_per_acre']].corr()

# correlation between farm size and yield
data[['Acreage', 'Yield']].corr()

# analyze location data
sns.scatterplot(data=data, x='Latitude', y='Longitude', hue='Yield', palette='coolwarm')
```
## Findings
1. The majority of farmers appear to be between the ages of 36 to 45, with fewer farmers above the age of 65.
2. Rain is the primary water source for irrigation, and there's no indication of irrigation systems being used.
3. Most farmers rely on credit groups for financing their farming activities.
4. Extension servises are mostly provided by the County government.

## Recommendations
- Fertilizer Management: Ensure farmers have access to affordable fertilizer.
- Crop Insurance: While most farmers do not have crop insurance, promoting its benefits and facilitating its accessibility could help mitigate risks associated with crop failures due to factors like weather fluctuations.
- Record Keeping: Encourage farmers to maintain better farm records, as this can aid in decision-making processes, especially regarding crop management, resource allocation, and financial planning.

## Limitations
The analysis relies on a very small dataset which might not give a true picture of farming practices in the whole county.

## References
- [Matplotlib documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html)

🔚
