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
