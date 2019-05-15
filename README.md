# Machine Learning Pipeline

We look at the initial exploration when creating a machine learning pipeline by observing one of the most common applications -> [The Boston Housing Prices dataset](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview). The information presented here is a collection of work that I have studied in my University coursework, various books,research papers ,and other educational sources. 


  ## Data Analysis (Relevant Notebook : [Data_Analysis.ipynb](https://github.com/amish-suchak/Machine-Learning-Infrastructure/blob/master/Data_Analysis.ipynb))

We start with the Data Analysis step where we look at analyzing the different attributes of data and performing the preliminary data exploration step to determine the important features and discard the features that are irrelevant or do not contribute to the output variable (In this case, the price of the house). 

### NaN value analyzer 

This step analyzes all the instances of NaN value in the dataset. Unlike the .csv file having "0", the NaN values represent having no information at all. For each feature, we want to determine how much of the information we can use. Hence, we see if there are features with a high percentage of missing values. 

### NaN determine usefulness of variables 

This step determines whether the information that is "missing" is relevant. We change the feature to have a 0 if there is a NaN value and a 1 if there is any other value. The point is just to see whether the information in the NaN value influences the final sale price.

### Temporal variables 

We can take a look at the temporal variables and determine whether we might need them or discard them. For variables that include a temporal (time) element, it is better to extract a bit of information first instead of just taking the variables as they are. For example, instead of taking the year as simply, the year, we could take the difference and calculate the age.

### Discreet variable analysis 

This step analyzes the discreet variables. We make plots of the discreet variables vs the sale price to see if there is a change in the sale price between the different features to get an idea of what features would likely be discarded or adopted by the feature selection algorithm. 

### Numerical variable analysis 

This step analyzes the numerical variables. We start by looking at just the variables and understanding the distribution of samples. If there is a skewed distribution, we can take the log function of the variable to make the distribution more Gaussian. We can also make a scatterplot of the variable vs the sale price of the house. 

### Categorical variable analysis 

In this stage, we look at the categorical variables. These are variables defined by a string separated into different categories. We determine the cardinality of the data to see the amount of samples of each category for each feature. 

## Feature Engineering
