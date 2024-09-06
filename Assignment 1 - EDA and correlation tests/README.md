LINK TO AN EXPLANATORY VIDEO ON THE ASSIGNMENT: https://drive.google.com/drive/folders/1ayvgSJ-aFHdRFEBdjGe2us7sb11WQZxK?usp=sharing
# QUESTION 1
# EDA
- First and foremost, analysis of all the useful columns was to be done
- There was no column of ZIP codes in the housing projects dataset, ZIP codes had to be extracted from the project address column
- Then a serach for nan/empty cells was conducted, replacing empty cells with appropriate values, if possible
- It was found that the restaurant dataset contained 1053 unique zip codes, whereas the housing datsset contained only 78
- Also the ZIP codes in the restaurant datset contained some ZIP + 4 codes, which had to be converted to just the normal 5 digit ZIP codes for analysis with the housing dataset which didn't contain these pinpoint codes
- After this normalization, the number of unique ZIP codes in the restaurant dataset dropped to only 99
# Summarizing by ZIP using SQL
SQL commands were used in python itself employing the sqlalchemy library
## Restaurant dataset
- Score (Mean, Max, Min) 
## Housing dataset
- Site units (Total) 
- Project total units (Total)

# Hypotheses and correlation tests
Variables to be used:
- Score
- Construction type
- Site units
- Project total units
- Housing type
- Supportive housing
- LAHD funds
- Leverage
- Tax benefits
- Total development cost
  
# Hypothesis testing  
## Alternate hypothesis
The statistics of affordable housing projects has a relation to the health inspection scores of the restaurants in that ZIP code  
## Null hypothesis
There is no correlation between teh datasets
## Correlation metric 
Pearson correlation coefficient
## Columns used for correlation calculation (For a given ZIP code)
#### Restaurant dataset
1. Average score
2. Maximum score
3. Minimum score
#### Housing dataset
1. total_site_units  
2. total_project_units  
3. total_lahd_fund  
4. total_leverage  
5. total_tax_exempt  
6. total_spending  
## Test statistic 
t-value for correlation = r and degrees of freedom = n - 2
## Significance level and critical t-value
For a 95% conifdence level, we get the sinificance level of 0.05, and since we are using a two tailed test(testing for both positive and negative correlations), we'll use 0.05/2 = 0.025 as the significance level to reject the null hypothesis  
Looking up the t-distribution table for significance level = 0.025 and degrees of freedom = 53 - 2 = 51, we get the critical t-value as 2.31 

# QUESTION 2
# Dataset
- All india consumer price index data from january 2013 to november 2023
# EDA 
- Observing Nan Values
### Filling nan values
- Using the average of the prior and next row values
- Checking for nan values after the filling operation to check for the presence of any residual NaN arising from corner cases
# Correaltion heatmap plot
### Observations from the heatmap: 
- Comparatively low values of correlation are observed between the categories of Vegetables, Pulses & products, Sugar & confectionary  
- These categories also show significantly low correlations with the other columns in the dataset

# Hypotheses and testing 
### Alternate hypothesis
The correlations of the Vegetables, Pulses & products, Sugar & confectionary columns with the other columns are significantly lower than the correlations between the other columns
### Null hypothesis
The values are not significantly less
### Correlation metric 
Pearson correlation coefficient
### Test statistic 
ANOVA: Analysis of variance - useful particularly for the test of comparison of values in multiple columns 
### Significance level and critical t-value
For a 95% conifdence level, we get the significance level (alpha) of 0.05
### Test methodology
- ANOVA test first conducted on the entire correlation matrix, followed by ANOVA test for the columns other than 'Vegetables', 'Pulses and products', 'Sugar and Confectionery'.
- If significant outliers found in the first test and not in the second, it would prove that the 'Vegetables', 'Pulses and products', 'Sugar and Confectionery' CPI values have significantly low correlations with the other columns
# RESULTS
- From the two ANOVA tests, one conducted on the entire correlation matrix while the other conducted on the correlation matrix with the 'Vegetables', 'Pulses and products', 'Sugar and Confectionery' columns dropped, we get the result that these columns are significantly less correlated with the other columns
- This shows how the price variations of Vegetables, pulses and confectioneries don't follow the general market trends of other commodities, which probably is because of these items being of daily use and consumption, their sale being unaffected by market events
