# SalaryPredictionPortfolio
Salary Prediction Portfolio

This project predicts the salary of the employee based on various categories like Job Type, Industry in which they are employed and Educational qualification of the  employee. It will also take into account the numerical categories like the experience of the employee and the distance from the metropolitan city.

## Problem Definition
The goal of this project is to examine the dataset given for various job postings and build a model to predict the salaries in the given test dataset.

## Tools Used

Python 3 (Jupyter Notebook)

## Libraries Used 

pandas     - For data structures, manipulation and analyzing Data

sklearn    - For classification, regression, Machine learning

matplotlib - For analyzing and plotting numerical data

numpy      - For multidimensional matrices and arrays, advanced mathematical functions

seaborn    - For visualization

scipy      - For Linear Algebra

## Directories

Data   - contains the data set used in the project

Code   - contains the jupyter notebook cantaing the entire code

Images - contains images of the various graphs plotted for analyzing the data

Results- contains the results obtained

## Data

**train_features.csv** contains metadata for an individual job posting.
The "jobId" column represents a unique identifier for the job posting.

**train_salaries.csv** contains salaries for job postings. 
Each row associates a "jobId" with a "salary".

**test_features.csv** contains metadata for an individual job posting.
We have to predict the salaries for the job postings provided in the csv file test_features.

**Categorical and Numerical Data**

Job Type - contains 8 different categories
           CEO, CFO, CTO, Janitor, Junior, Manager, Senior, Vice President
		   
Industry - contains 7 different categories
           Auto, Education, Finance, Oil, Health, Service, Web
		   
Degree   - contains the education qualification defined by 5 different categories
           High school, None, Bachelor's, Master's, Doctoral.
		   
Major    - contains the subjects which were taken by th employee defined by 9 different categories
           None, Literature, Biology, Chemistry, Physics, Computer Science, Math, Business, Engineering
		   
Years_of_Experience   - Employee experience in years varies from fresher to an experienced professional.

Miles_From_Metropolis - Distance from the Metropolitan city.

## Data Loading, Cleaning and Manipulation 

1) Import the required libraries.
2) Load the data in the Data Frames.
3) Describe the data and understand the statistics
4) We have merged the training data set having the target features (train_features.csv) and salaries (train_salaries.csv) in one file.
5) Cleaning the dataset
   1) Checked for duplicates. There were no duplicates present in the data.               
   2) Training dataset does not have null values				        
   3) Checked for invalid data in the dataset. There were 5 rows in the dataset containing salaries less than zero. 
      I have replaced the rows with the mean salary for the respective categorical and numerical features.
6) Stored the clean data in the csv file Train_Data.

## Exploratory Data Analysis (EDA)

This is the first step in Data Analysis. EDA is used to summarize the main features in the dataset. Also, it is used to understnad the relationships between the predictor and the target variables.

Steps :-

1) We have 1000000 rows and 9 coumns in our dataset.
2) Using descriptive analysis, we summarize and the categorical and numerical data.
3) Using value counts function, we analyze the distribution of data.
4) Used Box Plots to understand the salary distribution across various features. Check for outliers if any.
   
   ![image](https://user-images.githubusercontent.com/69466709/109588954-9158b800-7ad7-11eb-8f64-0ff6ade47550.png)
   
   ![image](https://user-images.githubusercontent.com/69466709/109588402-ab45cb00-7ad6-11eb-9743-ab6a90df4fec.png)

   ![image](https://user-images.githubusercontent.com/69466709/109588848-62424680-7ad7-11eb-92a3-7a4931592aac.png)

   
5) 
5) 
