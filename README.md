# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Useful Resources
- [ScriptRunConfig Class](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.scriptrunconfig?view=azure-ml-py)
- [Configure and submit training runs](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-set-up-training-targets)
- [HyperDriveConfig Class](https://docs.microsoft.com/en-us/python/api/azureml-train-core/azureml.train.hyperdrive.hyperdriveconfig?view=azure-ml-py)
- [How to tune hyperparamters](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-tune-hyperparameters)


## Summary
The client data is collected by a financial institution which is an outcome of direct marketing campaigns over the call.The outcome signifies whether the cleint subscribe for the financial product or not. 

## Scikit-learn Pipeline
**Explain the pipeline architecture, including data, hyperparameter tuning, and classification algorithm.**
The pipeline is designed to implement the classification algorithm by creating the model using the training data.The pipeline includes the following steps:
1) Creating a compute cluster
2) Reading the data from URL
3) Data Cleaning
4) Feature Engineering
5) Spliting the data into train and test subsets for model development
6) Training the model using the train dataset based on the various values passed in the parameter space
7) The classification model is developed based on the parameter values passed in the hyper parameter drive
8) The model with the best accuracy which is a primary_metric_goal is registered
**What are the benefits of the parameter sampler you chose?**
The random parameter sampling is used since it supports both discrete and continous values for hyperparameter.It randomly selects the value for hyperparameter from the space.It supports early stopping for the low performing jobs which therefore saves the computation efforts.
**What are the benefits of the early stopping policy you chose?**
The bandit policy is used for early stopping since it ends a job when the primary metric isn't within the specified slack factor/slack amount of the most successful job.
## AutoML
Automl automates the steps taken in the scikit learn pipeline.The end user need not to pay attention to the hyper parameter tunning as this would be taken care by the Automl 
## Pipeline comparison
The scikit-learn pipeline gave the accuracy of around ~91.4% whereas the automl gave the accuracy of around ~91.6%

## Future work
The model end-point can be consumed for predicition data

