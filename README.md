# Disaster Response Pipeline

## Table of Contents

1. [Installation](#installation)
2. [File Descriptions](#files)
3. [Results](#results)
4. [Licensing, Authors, and Acknowledgements](#licensing)
5. [Instructions](#instructions)

## Installation <a name="installation"></a>

Beyond the Anaconda distribution of Python, the following packages need to be installed for nltk:

* punkt
* wordnet
* stopwords

## File Descriptions <a name="files"></a>

There are three main foleders:

1. data
    * disaster_categories.csv: dataset including all the categories
    * disaster_messages.csv: dataset including all the messages
    * process_data.py: ETL pipeline scripts
    * DisasterResponse.db: output of the ETL pipeline, i.e. SQLite database
2. models
    * train_classifier.py: machine learning pipeline scripts to train and export a classifier
    * classifier.pkl: output of the machine learning pipeline, i.e. a trained classifer
3. app
    * run.py: Flask file to run the web application
    * templates contains html file for the web applicatin

## Results<a name="results"></a>

1. An ETL pipleline was built to read data from two csv files, clean data, and save data into a SQLite database.
2. A machine learning pipepline was developed to train a classifier to performs multi-output classification on the 36 categories in the dataset.
3. A Flask app was created to show data visualization and classify the message that user enters on the web page.

## Instructions

1. Run the following commands in the project's root directory to set up your database and model.

    * To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    * To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/
