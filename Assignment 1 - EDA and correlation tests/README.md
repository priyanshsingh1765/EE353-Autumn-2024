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
