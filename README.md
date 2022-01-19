# IBM-Attrition-Dataset---Random-Forest-Regression-Model

This is a Random Forest regression model I engineered using Pandas and Scikit-learn. 

The dataset can be found at: https://www.kaggle.com/pavansubhasht/ibm-hr-analytics-attrition-dataset

This project consists of 3 Jupyter Notebooks, each focusing on a different portion of the machine learning workflow.

1. Part 1 - Data Cleaning and Outlier Analysis
2. Part 2 - Exploratory Data Analysis and Feature Selection 
3. Part 3 - Data Preparation, Hyperparameter Tuning, Performance Evaluation

# Goal of Project

Engineer a regression model to predict the monthly incomes of different employees in the dataset.

# Summary of Model Performance

Training Score: 0.9621

Testing Score: 0.9479

Below is a distribution of actual vs. predicted values. As you can see, the model can predict monthly incomes on the testing set quite well. Furthermore, there are no signs of overfitting.

![image](https://user-images.githubusercontent.com/40840760/150053778-23ec1c88-d6a3-4df9-bfd8-7f4744b38ba2.png)

# Summary of Feature Selection Methods

METHODS FOR CHOOSING FEATURES:

    CHOOSING FEATURES FOR NUMERIC VARIABLES:
    1. Spearman's and Pearson's correlation coefficient of features vs. target labels
    2. Visual inspection of scatter plots to detect patterns when plotting  features vs. target labels.
    
    
    ![image](https://user-images.githubusercontent.com/40840760/150055657-b54b00d6-ceda-4139-8441-dd0c0d0d0990.png)

    
    CHOOSING FEATURES FOR CATEGORICAL VARIABLES:
    1. Features were chosen based on whether grouping by different categories in a column will yield different
       distributions for the target variable.
       
    ![image](https://user-images.githubusercontent.com/40840760/150055843-4d12c5a3-5c34-45c4-bc50-fcd905177efe.png)
    
    <b> To explain how categorical features were chosen, there are 2 categorical features above. On the left is OverTime, and on the right is JobRole </b>

OverTime was NOT CHOSEN as an input feature because it says very little about the target variable (monthly income). This is because monthly income distributions are the same when grouped by "yes" and "no". Furthermore, the average monthly income between those who do overtime and those who don't are very similar. As a result of these two facts, the OverTime feature says very little about the target variable and should not be included in the model.

On the contrary, "JobRole" is a feature that was CHOSEN. If we group monthly income by each job role, we can see that the distributions are radically different. Furthermore, the average income between each job role varies along with each role. As a result, the model can learn meaningful patterns for estimating monthly income; this is why this feature was selected as an input feature to the model.
       
# Summary of Methodology

1. 75%-25% Training and Testing Split. Used a random split,
2. GridSearchCV RF optimized parameters: min_samples_leaf = 1 and max_depth = 5








