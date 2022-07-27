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

#Data Cleaning
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
