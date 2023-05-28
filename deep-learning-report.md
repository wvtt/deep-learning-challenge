# Deep Learning Report

## Overview
The purpose of this project is to create a tool for Alphabet Soup that helps select applicants for funding with the highest chance of success in their ventures. The goal is to achieve 75% or higher accuracy for the model. CSV contains more than 34,000 organizations that have received funding from Alphabet Soup over the years. The dataset contains information from each organization including:

EIN and NAME—Identification columns
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organization classification
USE_CASE—Use case for funding
ORGANIZATION—Organization type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special consideration for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively

## Steps

* 1: Preprocessed data
-Dataset was checked for null and duplicated values
-EIN and NAME—Identification columns removed from the input data because they are neither targets nor features
-Created cutoff point to bin "rare" categorical variables together in a new value, Other for both CLASSIFICATION and APPLICATION_TYPE
-Converted categorical data to numeric with pd.get_dummies, split the preprocessed data into features and target arrays, then lastly split into training and tesing datasets

* 2: Compiled, trained, and evaluated the model
Model included the following layers: an input layer with 80 neurons, a second layer with 30 neurons, and an output layer with 1 neuron. There were 43 input features remaining after removing 2 irrelevant ones. I selected the relu activation function for the first and second layers and the sigmoid activation function for the output layer since the goal was binary classification. Model was trained for 100 epochs and achieved an accuracy score of approximately 74% for the training data and 72.9% for the testing data.

* 3: Optimization
Optimization was done using an automated model optimizer to get the most accurate model possible. This was done via creating s a keras Sequential model using the keras-tuner library with hyperparametes options.