# Data-Science-Pipeline
Udacity course Data Science Pipeline

### Table of Contents
1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation">
 
Anaconda distribution of Python, Python versions 3.*.

Libraries used:
1. numpy
2. pandas
3. matplotlib
4. seaborn
5. sklearn
6. spacy

## Project Motivation <a name="motivation"></a>
For this project, I was interestested in using Udacity data regarding women's clothing retailer.
"StyleSense", a rapidly growing online women's clothing retailer, is known for its trendy and affordable fashion, and its customer base has exploded in recent months. 
This influx of new customers is fantastic for business, but it has created a challenge: a backlog of product reviews with missing data. 
Customers are still leaving valuable feedback in the text of their reviews, but they aren't always indicating whether they recommend the product.

This model will analyze the text of a review, the customer's age, the product category, and other relevant information to predict whether or not the customer would recommend the product.

## File Descriptions <a name="files"></a>
There is 1 notebook available [here](https://github.com/gostrowska/Data-Science-Pipeline/blob/main/starter.ipynb)
There is a dataset used in analysis available [here](https://github.com/gostrowska/Data-Science-Pipeline/tree/main/data)
The dataset has been anonymized and cleaned of missing values.

There are 8 features for to use to predict whether a customer recommends or does not recommend a product. The Recommended IND column gives whether a customer recommends the product where 1 is recommended and a 0 is not recommended. This is your model's target/

The features can be summarized as the following:

    Clothing ID: Integer Categorical variable that refers to the specific piece being reviewed.
    Age: Positive Integer variable of the reviewers age.
    Title: String variable for the title of the review.
    Review Text: String variable for the review body.
    Positive Feedback Count: Positive Integer documenting the number of other customers who found this review positive.
    Division Name: Categorical name of the product high level division.
    Department Name: Categorical name of the product department name.
    Class Name: Categorical name of the product class name.

The target:

    Recommended IND: Binary variable stating where the customer recommends the product where 1 is recommended, 0 is not recommended.
## Results <a name="results"></a>
In the dataset features were separated from labels. Later 1 divided features into 3 categories: categorical, numeric and text data. While splitting data into train and test sets I used stratified sampling as dataset is imbalanced.
During data preprocessing I used QuantileTransformer and MinMaxScaler for numeric data, OneHotEncoder for categorical data. For text data I used SpacyLemmatizer and TF-IDF. i tested 3 models: Random Forest Classifier, Gradient Boosting Classifier and Ada Boost Classifier. To account for imbalanced data I evaluated modes with average precision score. Ada Boost Classifier performed the best during evaluation and this model was later tuned. Final model average precision score is 0.89 with learning_rate=0.5, n_estimators=200 parameters.

## Licensing, Authors, Acknowledgements <a name="licensing"></a>
Licensing for the data and other descriptive information of a dataset is [Udacity]([https://learn.udacity.com]).<br />
Author of the notebook: Grazyna Ostrowska
