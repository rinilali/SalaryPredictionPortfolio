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
   
   We found outthere were 7117 observations which were above the upper extremes and considered as outliers.
   After further investigation, we found out that the observations were valid based on the higher level of education, 
   higher job types and were assosciated with the Finance and oil industry. They were not removed from the Dataset.

5) Using the ANOVA method, I found out the correlation between various groups of categorical features and the target
   feature salary. Salary is correlated with jobType, industry, degree and major categories. 
   The F-value is large and the p-value close to zero which indicates strong correlation between these groups.

6) Summary of Categorical, Numeric and Target Features :-

   Categorical Variables :- jobType, industry, major, degree
   
   ![image](https://user-images.githubusercontent.com/69466709/109591358-5f495500-7adb-11eb-857f-2913827af117.png)
   
   Numerical Features :- yearsExperience and MilesFromMetropolis
   
   ![image](https://user-images.githubusercontent.com/69466709/109591418-74be7f00-7adb-11eb-83ea-14ece125d703.png)
   
   Target Feature :- Salary
   
   ![image](https://user-images.githubusercontent.com/69466709/109591451-84d65e80-7adb-11eb-8783-da8a4b85e5b0.png)
   
7) 




   ![image](https://user-images.githubusercontent.com/69466709/109589126-e0065200-7ad7-11eb-9645-dd0952645489.png)
   
   ![image](https://user-images.githubusercontent.com/69466709/109589199-f44a4f00-7ad7-11eb-90a1-8637102f5cde.png)
   
   ![image](https://user-images.githubusercontent.com/69466709/109589258-0c21d300-7ad8-11eb-94b2-ad5af83486e7.png)
   
   ![image](https://user-images.githubusercontent.com/69466709/109589509-69b61f80-7ad8-11eb-97c1-4f4e2aebbe64.png)
   
   ![image](https://user-images.githubusercontent.com/69466709/109589373-383d5400-7ad8-11eb-9fea-ade6478e824e.png)
   
   ![image](https://user-images.githubusercontent.com/69466709/109589565-82263a00-7ad8-11eb-9865-21d457bb8a11.png)   
   
   ![image](https://user-images.githubusercontent.com/69466709/109589633-9ec27200-7ad8-11eb-9136-d5a2e71b588c.png)
   
   
   ![image](https://user-images.githubusercontent.com/69466709/109589698-b699f600-7ad8-11eb-8a8b-e418a4ca9d24.png)




   
   





