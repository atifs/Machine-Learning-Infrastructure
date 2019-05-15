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

***


## Feature Engineering (Relevant Notebook: [Feature_Engineering.ipynb](https://github.com/amish-suchak/Machine-Learning-Infrastructure/blob/master/Feature%20Engineering.ipynb))

After analyzing the data, this is the next step of the process where we "Engineer" the features. This is still a part of the pre-processing step. It includes fixing the variables with NaNs, discarding rare labels, fixing the distribution of variables, and also splitting the data into testing and training sets.

### Splitting the data into training and testing sets 

We do this step before pre-processing the data. The test-set is not used to learn the transform parameters; it needs to be completely new data.

### Filling up the missing (NaN) values from the categorical and continuous variables

For the categorical variables, we fill the NaN values with "missing". For the continuous variables, we fill the missing data with the mode of the variable. 

### Fixing temporal variables  

We take the "Age" instead of the "Year". The age is just a number with respect to when the house was sold.

### Making numerical variables normally distributed 

Converting numerical values which do not contain 0 to a Gaussian distribution helps linear models converge better

### Removing rare occurences of labels

In categorical variables, we don't want to deal with variables that are present in less than 1% of observation so we can just remove them.

### Converting strings into categories 

In this stage, we convert the categorical strings that we have into numerical categories. These numerical categories are defined and ranked by the mean of the output. Categories with a lower sale price would be ranked 1 and higher mean sale price would be ranked 5. 

### Feature Scaling

This step just scales the features using the MinMaxScaler from the sklearn library. 

***

## Feature Selection

This step of the pipeline deals with selecting the appropriate features for our analysis. Feature selection is a vast topic with many methods to select features depending on the type of problem. For the Boston Housing Prices problem, we look at selecting features through a LASSO Regression method. Once the appropriate features are selected, the column names are stored in a list to use in the final model part of the process. 

