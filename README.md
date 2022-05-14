# DEEP-ESG-Data-Challenge
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
---

# Goal 
Considering the following structure of a chart of accounts with one root node (account 1):
```bash
1
├── 1.1  
├── 1.2  
│   ├── 1.2.1  
│   └── 1.2.2  
└── 1.3  
    └── 1.3.1  
        ├── 1.3.1.1  
        └── 1.3.1.3  
```
And the following example of a general ledger:
|Account number|Value    
| :-: |:-:|
|1.2.1|7|
|1.2.2|8|
|1.1|1|
|1.2.2|2|
|1.3.1.3|10|
|1.3.1.3|6|
|1.3.1.1|2|
|1.2.1|4|
|1.2.1|1|
|1.3.1.3|6|
|1.2.1|9|
|1.3.1.3|10|
|1.3.1.1|8|
|1.3.1.3|9|
|1.1|1|
|1.3.1.1|4|
|1.2.2|7|
|1.3.1.3|7|
|1.2.1|10|
|1.2.2|9|

The main goal of this challenge is to organize the Chart of Accounts given as input by adding each value addressed to a certain account number at the general ledger and sum these values to populate each line of the chart of accounts according to its number of identification, which is the same as the account number presented in the general ledger.<br>
Finally, we must make a final sum of all the values represented in each leaf of the chart of accounts that has a link to a certain node (01 to 05) and present the sum of values of each row of the chart, similar to the structure previously displayed above, resulting in a consolidated chart of accounts similar to the one below:

```bash
1 = 2 + 57 + 62 = 121
├── 1.1 = 2
├── 1.2 = 57
│   ├── 1.2.1 = 31 
│   └── 1.2.2 = 26
└── 1.3 = 62
    └── 1.3.1 = 14 + 48 = 62
        ├── 1.3.1.1 = 14
        └── 1.3.1.3 = 48
```

# Steps Taken

1. First, the libraries necessary for the development of this challenge were imported to the notebook:
 > - Pandas: For creation and visualization of DataFrames and also to save the final chart of accounts.
 > - Numpy: For converting data to numpy array, making it easier to develop loops.
 > - Os: To create an output directory where the final chart of accounts would be stored into. 

2. After that, both the chart of accounts and general ledger excel files given as input are opened and displayed as dataframes
3. The dataframes are converted into numpy array in order to make the loops necessary to populate the chart of accounts with the general ledger data
4. The first for-in loop is created to sum the values presented in the general ledger according to its account number identification, adding these sums to the chart of accounts and organizing the results for each specific account number.
5. A second for-in loop is created to store the summed values of the chart of accounts into a list.
6. A final for-in loop is created to make the final sum of values by adding the results to each root node presented in the chart of accounts.
7. The desired results in the list are then stored in a pandas DataFrame.
8. Finally, an output directory is created and an excel file of the final chart of accounts dataframe is saved into it, which is available for download.

