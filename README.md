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

## Benefits and Uses of the Model
    - Gain a better understanding of the variables that lead to injury/fatality of a collision.
    - Use for planning of road infracture to reduce collision.
    - Put up appropriate billboards like 'accident prone zone/slow down' in collision-prone areas.

## Exploratory Data Analysis and Pre-processing
    - Target classes injury and fatality were combined to create a single class converting the problem to a binary classification: 0 - Injury/Fatality and 1 - No Injury.
    - Missing values for categorical variables were imputed with the respective modes.
    - Value to identify pedestrians involved in collisions were synchronized across 3 categorical columns.
    - Missing values for 'Age' variable was imputed with the mode age in each user category. Users are: driver, passenger, pedestrian,      bicyclist, motorcyclist.
    - Age variable was binned to convert it to a categorical variable.
    - Time based features month, day, and time were transformed to cyclical features.
    - StandardScaler was applied to numerical features and OneHotEncoding for categorical features.
    
## Feature Selection
    - Chi-Square test for feature selection of  categorical features
    - Mutual info classif to measure the dependecy between numeric variables with the target variable.

## Key Insights
    The major features associated with a collision leading to  injury/fatality or not are, whether:
    - Helmet worn (for motorcyclists, bicyclists, snowmobilers, all-terrain vehicle riders)
    - No safety device used, or child restraint used
    - Pedestrians
    - Motorcyclist
    - Bicyclist
    - Single vehicle in motion ran off right shoulder
    - Female
    - Male
    - Rear-end collision
    - Ran-off left shoulder 
    
## Comparison of all Classifiers
<img width="455" alt="roc_train" src=“https://user-images.githubusercontent.com/58715002/215579563-e757b302-63c7-48dd-8fbb-a7f8aaeeef2a.png">
                                                                                                                                            
<img width="455" alt="roc_test" src=“https://user-images.githubusercontent.com/58715002/215579739-a8842fe2-f61f-44c7-9464-f5f3040b48e0.png">

<img width="276" alt="roc_scores" src="https://user-images.githubusercontent.com/58715002/215579809-80fd7383-8f1a-473f-aa85-d7b897a3fdfb.png">

Model of Choice is GradientBoost Classifier.
