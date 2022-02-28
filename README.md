# Natural_Disaster_Udacity

The data of project uses the various users across the world posted in social media during various disasters such as earthquake, fire, missing person, food/ water related issues,etc. The focus is to develop a Web application which will categorize any given disaster message received from people.

## Table of Contents

- [Installation](#installation)
- [Overview of repository](#overview-of-repository)
- [How to run the code](#how-to-run-the-code)
- [High level data preparation steps taken](#high-level-data-preparation-steps-taken)
- [Using the Web App](#using-the-web-app)

## Installation

To clone the repository use: ```https://github.com/TBORHADE/Natural_disaster_udacity.git```

## Overview of repository

The repository contains the following files:

    Diasater_Response_Pipeline_Project_Udacity
    ├── README.md
    ├── ETL_Workflow.ipynb
    ├── ML_workflow.ipynb
    
    ├── data
      ├── disaster_categories.csv
      ├── disaster_messages.csv
      ├── DisasterResponse.db
      ├── process_data.py
      
    ├── models
      ├── train_classifier.py
      ├── classifier.pkl
      
    ├── app
      ├── run.py
      ├── templates
        ├── master.html
        ├── go.html

The input data files used for the project are:

1) disaster_messages.csv - Responses from people in social media for various disasters.
2) disaster_categories.csv - Category under which each disaster response falls.

## How to run the code

There are 3 parts to this project:
1) ETL pipeline
2) Machine Learning pipeline
3) Web App

**Excution of ETL pipeline:**
    ``` python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db ```
This will create a SQL database in the name DisasterResponse.db under the "data" folder.

**Exicution of ML pipeline:**
    ``` python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl ```
This will create a classification model pickle file in the name classifier.pkl under the "models" folder.

**Exicution of Web App:**
Go to the app folder and run:
    ``` python run.py ```
    
In a new terminal run:
    ``` env|grep WORK ```
    

    
## Data preparation steps takes
**ETL Pipeline**
 Extract the data from the CSV files from the "data" folder.
 Split the 'categories' column into individual categories.
 Merge the two datasets.
 Remove duplicates.
 Load into a SQL database and save it in the "data" folder.

**ML Pipeline**
  Load the data from the SQL database present in the "data" folder.
  Split the dataset into train and test.
  Apply feature extraction techniques: CountVectorizer, TfidfTransformer.
  Build a model using SGDClassifier.
  Hyperparameter tune the model using GridSearchCV.
  The best estimator obtained, train the dataset.
  Predict on test dataset.
  The estimation of performance metrics model.
  Train another model (AdaBoostClassifier) with another feature added using StartVerbExtractor (This step is performed only in the ipynb).

