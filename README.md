# SalaryPredictionPortfolio
Salary Prediction Portfolio

This project predicts the salary of the employees based on various categories such as Job Type, Industry in which they are employed and Educational qualification of the  employee. It will also take into account the numerical categories like the experience of the employee and the distance from the metropolitan city.

## Problem Definition
The goal of this project is to examine the dataset for various job postings and build a model to predict the salaries in the given test dataset.

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

1) Imported the required libraries.
2) Loaded the data in the Data Frames.
3) Described and analyzed the data and its statistics
4) Merged the training data set having the target features (train_features.csv) and salaries (train_salaries.csv) in one file.
5) Cleaned the dataset
   1) Checked for duplicates. There were no duplicates present in the data.               
   2) Training dataset does not have null values				        
   3) Checked for invalid data in the dataset. There were 5 rows in the dataset containing salaries less than zero. 
      Replaced the rows with the mean salary for the respective categorical and numerical features.
6) Stored the clean data in the csv file Train_Data.

## Exploratory Data Analysis (EDA)

This is the first step in Data Analysis. EDA is used to summarize the main features in the dataset. Also, it is used to understand the relationships between the predictor and the target variables.

Steps :-

1) We have 1000000 rows and 9 columns in our dataset.
2) Using descriptive analysis, summarized the categorical and numerical data.
3) Using value counts function, analyzed the distribution of data.
4) Used Box Plots to understand the salary distribution across various features. Checked for outliers if any.
   
   ![image](https://user-images.githubusercontent.com/69466709/109588954-9158b800-7ad7-11eb-8f64-0ff6ade47550.png)
   
   ![image](https://user-images.githubusercontent.com/69466709/109588402-ab45cb00-7ad6-11eb-9743-ab6a90df4fec.png)

   ![image](https://user-images.githubusercontent.com/69466709/109588848-62424680-7ad7-11eb-92a3-7a4931592aac.png)
   
   There were 7117 observations which were above the upper extremes and considered as outliers.
   After further investigation, it was evident that the observations were valid based on the higher level of education, 
   financially rewarding job roles and were assosciated with the Finance and oil industry which are considered as profitable
   sectors. 
   No action was taken and they were not removed from the Dataset.

5) Using the ANOVA method, the correlation between various groups of categorical features and the target
   feature salary were analyzed. Salary is correlated with jobType, industry, degree and major categories. 
   The F-value is large and the p-value close to zero which indicates strong correlation between these groups.

6) Summary of Categorical, Numeric and Target Features :-

   **Categorical Variables :- jobType, industry, major, degree**
   
   ![image](https://user-images.githubusercontent.com/69466709/109591358-5f495500-7adb-11eb-857f-2913827af117.png)
   
   **Numerical Features :- yearsExperience and MilesFromMetropolis**
   
   ![image](https://user-images.githubusercontent.com/69466709/109591418-74be7f00-7adb-11eb-83ea-14ece125d703.png)
   
   **Target Feature :- Salary**
   
   ![image](https://user-images.githubusercontent.com/69466709/109591451-84d65e80-7adb-11eb-8783-da8a4b85e5b0.png)
   
7) Using graphical representations to understand how the average salary varies across the various categorical and 
   numerical features :-
   
   **Average Salary By Job Type**
   
   ![image](https://user-images.githubusercontent.com/69466709/109589126-e0065200-7ad7-11eb-9645-dd0952645489.png)
   
   The average salary is lowest for the jobType "Janitor" and highest for "CEO". 
   Job Designation "CEO", "CFO" and "CTO" are better paid as compared to "Janitor".
   
   **Average Salary By Industry**
   
   ![image](https://user-images.githubusercontent.com/69466709/109589199-f44a4f00-7ad7-11eb-90a1-8637102f5cde.png)
   
   "Finance" and "Oil" industry have higher salaries than others.
   
   **Average Salary By Degree**
   
   ![image](https://user-images.githubusercontent.com/69466709/109589258-0c21d300-7ad8-11eb-94b2-ad5af83486e7.png)
   
   Jobs with educational background of Masters and Doctoral will have higher salaries as compared to jobs having 
   No degree 'None' or "High School".
   
   **Average Salary By Major**
   
   ![image](https://user-images.githubusercontent.com/69466709/109589509-69b61f80-7ad8-11eb-97c1-4f4e2aebbe64.png)
   
   Salaries were low for a jobId having no major 'None'.
   
   **Average Salary By Years of Experience**
   
   ![image](https://user-images.githubusercontent.com/69466709/109589373-383d5400-7ad8-11eb-9fea-ade6478e824e.png)
   
    Salary increases linearly with experience
   
   **Average Salary By Miles from Metropolitan city**
   
   ![image](https://user-images.githubusercontent.com/69466709/109589565-82263a00-7ad8-11eb-9865-21d457bb8a11.png)
   
   Salary decreases linearly if we move away from a metropolitan city.
   
8) Below is the plot for Salary Distribution :-
   
   ![image](https://user-images.githubusercontent.com/69466709/109589633-9ec27200-7ad8-11eb-9136-d5a2e71b588c.png)
   
   The most number of jobs have their salaries in the range of 80 to 150.
   
9) Correlation by Heatmap :-   
   
   ![image](https://user-images.githubusercontent.com/69466709/109589698-b699f600-7ad8-11eb-8a8b-e418a4ca9d24.png)
   
   The most important feature related with salary is job type.
   There is positive correlation between "salary" and "yearsExperience" and negative correlation between "salary" 
   and "milesFromMetropolis".
   
## Baseline Model

Created a simple baseline model using the average salary and calculating the Mean Squared Error(MSE) on the basis 
of two feature variables ***Job Type*** and ***Industry***.

Mean squared error(MSE) with Feature ***JobType*** -  ***963.2***

Mean squared error(MSE) with Feature ***Industry*** - ***1367.119***

Need to develop models in order to reduce the mean squared error (MSE) less than 360 and make better predictions.

## Hypothesize Solution

Used four different models in order to reduce the MSE amd improve accuracy.
Target feature *Salary* is dependent on multiple *categorical* and *numerical* features.

They are :-

1) Multiple Linear Regression
2) Random Forest
3) Gradient Boosting
4) Polynomial Regression

## Develop Models

In order to devlop models, train and test the data, we need to create features ready for modelling.

   ### Preparing Data
   
    1) Have used one hot encoding method to transform categorical values to numeric.
    2) Standardized the numeric features yearsExperience and milesFromMetropolis using minmaxscaler method.
    
   ### Test Models
   
    1) Created subset of training data. 
    2) 80 % of the data is used for training and 20 % is used for testing the model.
    3) Fit the model
    4) Obtain the predictions
    5) Check for accuracy
    
   ### Model Evaluation using Visualization
   
   Created visualizations using the actual and the predicted values from the training/testing data.
   
   ***For Multiple Linear Regression***
   
   ![image](https://user-images.githubusercontent.com/69466709/109682184-2d240b80-7b4c-11eb-8611-50778a735927.png)
   
   ***For Random Forest***
   
   ![image](https://user-images.githubusercontent.com/69466709/109686111-f9e37b80-7b4f-11eb-95af-26993095f627.png)
   
   ***For Gradient Boosting***   
   
   ![image](https://user-images.githubusercontent.com/69466709/109687098-eb499400-7b50-11eb-8cc5-c6b900e0fad6.png)
   
   ***For Polynomial Regression***
   
   ![image](https://user-images.githubusercontent.com/69466709/109687671-788ce880-7b51-11eb-9e04-acbae4ca8137.png)
    
   ### Observations  
       
       The below table shows the errors and accuracy for each model :-
       
   ![image](https://user-images.githubusercontent.com/69466709/109732084-77c47880-7b8a-11eb-8029-858e5e12e784.png)
       
   ### Test Models using the 5-fold cross validation
   
   The cross validation score is used to evaluate the models.
   
       The cross validation score for Linear Model: 0.7435
       
       The cross validation score for Random Forest Model: 0.7515
       
       The cross validation score for Gradient Boost Model: 0.7622
       
       The cross validation score for Polynomial Regression Model: 0.7638

## Deploy Models

Selected the model ***Gradient Boosting*** for salary prediction.
Obtained predictions using the model and stored the file in csv format.

   ### Feature Importance
   
   This shows the importance of features in obtaining the prediction using the model
   
   ![image](https://user-images.githubusercontent.com/69466709/109696628-41bbd000-7b5b-11eb-951b-8a3402a45bea.png)
   
## References

   * Wikipedia
   * For Python Libraries - python.org
   * Article - https://towardsdatascience.com/categorical-encoding-using-label-encoding-and-one-hot-encoder-911ef77fb5bd
   * https://scikit-learn.org/stable/modules/linear_model.html
   * Article - https://towardsdatascience.com/simple-and-multiple-linear-regression-in-python-c928425168f9
   * Article - https://towardsdatascience.com/random-forest-in-python-24d0893d51c0
   * Other Data Science Projects
