# Links-Classification-Based-on-Meta-Data
Build a model to based on the extracted features to classify links to either related/unrelated to this series 

# Contents

1. Data Cleaning

2. Feature Extraction

3. Dataset splitting

4. Modeling

5. Evaluation

6. Results

7. Model Improvement

# Data Cleaning
Check if data has null values, and find the number of missing data at each
column

● Link_id =0

● Page_source_path=0

● Link_url=0

● Link_domain_name=0

● Content_name=0

● Trans_content_name=5085

● Altra_content_name=851

● Compaige_name=0

● Number_of_episodes=0

● Class=10

So we have missing data in class, Altra_content_name, and

Trans_content_name

Trans_content_name :

has more than 50% of the data missing

So it will not affect removing it from the dataset as it is considered noise

Altra_content_name:

Remove rows that contain missing values

Class:

Remove rows that contain missing values

# Feature Extraction
The dataset has nine columns we will use to know if the link is related or not

related to that TV show. to be able to do this we need to extract features from

each column before feeding it to a deep learning model

We will look at each column and extract its features

First, the dataset must be transformed into forms that we can feed it to the
model .

Each column will be handled to extract features, Let's start with the first column

# 1.Link_url:

Extract features from the URL link are one of the most important features that

we will feed to the model.

We have multiple features that we will extract

1. Extracting whois features from URLs such as

● Fetch the website age in days

● Fetch the website expiry date in days

● Fetch the website's last updated date in days

2. Extracting lexical features from URLs

● Numbers of dots

● Number of digits

● Number of special characters

● Number of hyphens(_)

● Number of the double slash (//)

● Number of single slash (/)

● Number of at the rate(@)

● Get protocol

● Count protocol


After getting features we need to normalize features before giving them to the model 


# 2.Page_source_path:

The same feature extraction method that applied to the link_urls will be applied

to Page_source_path. By doing this we find that all features have the same

values for all Page_source_path links except the number of digits

So all features will be dropped except the number of digits

After getting features we need to normalize features before giving them to the

model so the features will be normalized by max_min normalization to make

the training faster

# 3.Link_domain_nam ,Content_name,Altra_content_name,Compaige_name

All four columns are text data that need to be converted to numerical data

To make this we will use a bag of words techniques to convert it to numerical data

Bag of Words (BOW) is a method to extract features from text documents.

These features can be used for training machine learning algorithms. It creates a

vocabulary of all the unique words occurring in all the documents

4.Number_of_episodes,Link_id

Number_of_episodes, Link_id are numerical data so the only thing we need is

to normalize before giving them to the model so the features will be normalized

by max_min normalization to make the training faster

# 4. Class
Convert related and unrelated to numerical data
Related will be 1
Unrelated will be 0

# Dataset splitting

After data cleaning and feature extract, we will concatenate all features and
split the data set into train and test data

# Modeling
After data cleaning and feature extract, the features will be given to the deep
learning model to use them to class links if it is related or not to the TV show

Keras framework is used to create deep learning model
Keras model consists of :

● Five dense layers

● Two dropout layers

● Batch_size=32

● Epochs=100

Train data will be 70% of the dataset and test data will be 30%

# Evaluation

To evaluate the model we used

● Adam optimizer

● Binary_crossentropy

● Accuracy metric

# Results
After training the model we get these results

1. The training accuracy =95%

2. The validation accuracy =93%

3. The test accuracy =84.4%

# Here you will find two folders 
# DL_model
Contains

1. DL_model.ipynb:network architecture model

2. Model_weights

3. Features_data(x_data) which is csv files

4. Classes (y_data) which is csv files

5. Predicted_values from model which is csv files

# Extracted_preprocessing_data

Contains two main folders

1. Features extraction and pre-processing codes

2. CSV files extracted and pre-processing features
