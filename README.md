## Introduction
This dataset is the national collision data from 2019 for Canada. It contains police-reporting of motor vehicle collisions on public roads and tracks a number of variables relating to the collisions like:
- month, day, time
- number of vehicles involved
- type of collision, eg. rear-end, head-on, etc.
- place of collision, eg. intersection, ramp, rail-road crossing, etc.
- weather
- type of road surface, eg. dry, wet, snow, etc.
- traffic condition, eg. traffic signal operational, stop-sign, etc.
- vehicle type
- age and sex of the driver
and a list of other features.

## Objective
Develop a classification model to predict whether or not a particular collision will lead to an injury/fatality or no injury.

## Benefits and Use of the Model
- Use for planning of road infracture to reduce collision.
- Gain a better understanding of the variables that lead to injury/fatality in a collision.
- Optimize exisiting services. Example medical availablity near collision-prone areas.   
- Put up appropriate billboards like 'accident prone zone/slow down' in collision-prone areas.

## Exploratory Data Analysis and Feature Engineering
- Converted the problem to binary classification by combining target classes injury and fatality to create a single class  0 - Injury/Fatality and 1 - No Injury.
- Imputed missing values for categorical variables with their respective modes.
- Analyzed and imputed missing values for 'Age' variable with the mode age in each user category. User categories are: driver, passenger, pedestrian, bicyclist, motorcyclist.
- Discretized 'Age' variable.
- Synchronized the value to identify pedestrians involved in collisions across 3 categorical variables.
- Transformed time based features month, day, and time to **cyclical features**.
- Applied **StandardScaler** to numerical features and **OneHotEncoding** for categorical features.
    
## Feature Selection
- Chi-Square feature selection for categorical features.
- Mutual info classif to measure the dependecy between numeric variables and the target variable.

## Key Insights
Gradient Boost model has the best scores for train and test data. For Gradient Boost the following features seem to be the most important for predicting whether a collision will lead to injury/fatality or not in a collision: 
- Number of vehicles involved in the collision
- Whether safety device is used or child restraint is used
- Whether the person involved in collision is a female
- Whether the person involved in collision is a male
- Whether the person is a passenger
- Whether the age of the person involved in collision is between 0 to 15.
  
## Comparison of Classifiers
<img width="850" alt="roc_train_test" src="https://user-images.githubusercontent.com/58715002/215581601-c445d809-96ff-495c-8a83-8e2b33300c27.png">
<img width="276" alt="roc_scores" src="https://user-images.githubusercontent.com/58715002/215579809-80fd7383-8f1a-473f-aa85-d7b897a3fdfb.png">
