# Project 4: Group Project

This project is a part of DSIR-EC-124 at [General Assembly](https://generalassemb.ly/). 

#### Project Status: [Incomplete]

## Project Obective


## Introduction


## Executive Summary
Notes from P3:
- Make sure you are specific. No mention of the type of model you plan to develop is mentioned in your problem statement.
- Does the student explain how the model works and evaluate its performance successes/downfalls? -- Focus here
- Does the student provide appropriate context to connect individual steps back to the overall project?






In order to represent the online presence mentioned previously, the models that I built leveraged data scraped from the social media platform, Reddit. In particular, the data came from the Backpacking and Ultrarunning subreddits, as these communities accurately represent our customer base. 

Once the data had been collected, using the [`reddit_scraper`](./data_cleaning_and_eda/reddit_scraper.ipynb) notebook, it was stored in the `raw_data` folder in a file called [`reddit.csv`](./raw_data/reddit.csv). From there, the data was cleaned utilizing the [`data_cleaning`](./data_cleaning_and_eda/data_cleaning.ipynb) notebook, then saved to the `clean_data` folder in a file called [`reddit_clean.csv`](./clean_data/reddit_clean.csv).

Exploratory Data Analysis (EDA) was then performed against the `reddit_clean.csv` in both the [`EDA_basic`](./data_cleaning_and_eda/EDA_basic.ipynb) and [`EDA_feature_engineered`](./data_cleaning_and_eda/EDA_feature_engineered.ipynb) notebooks, which can be found within the `data_cleaning_and_eda` folders. In order for the models to accurately classify which subreddit a post or selftext originated, it would be imperative to run the data through a vectorizer. To provide the model with the most useful data, first, the `title` and `selftext` columns were merged, in order to provide the model with additional text. Additionally, new columns were engineered to capture patterns in the newly formed `title_merge` column, such as `title_word_count`, `title_length`, and Sentiment Analysis. Upon completing these initial steps, the newly created dataframe was run through a `CountVectorizer`. The outputs were analyzed utilizing time series techniques, plotting, and examining newly formed relationships.

To model the data, I utilized many different types of models, such as Logistic Regression, KNN, and Random Forest. Additionally, I used different methodologies, including, but not limited to `CountVectorizer`, `TfidfVectorizer`, `Pipeline`, and `GridSearchCV`. Within each model, I tuned the model using the available hyperparameters in the pursuit of producing the most accurate model possible.

For more information on the data referenced in the Executive Summary, please refer to the [`Data Dictionary`](../master/Data_Dictionary.md)

### File Structure

```
project
│   Data_Dictionary.md
│   Project Three - Classifying Subreddits Backpacking vs Ultrarunning.pdf
│   README.md
│
│
└──clean_data
│     reddit_clean.csv
│         
│   
└──data_cleaning_and_eda
│     data_cleaning.ipynb
│     EDA_basic.ipynb
│     EDA_feature_engineered.ipynb
│     reddit_scraper.ipynb
│  
│
└──engineered_data
│     engineered_data_merged_columns.csv
│     engineered_data_title_and_selftext.csv
│
│
│
└──graphics
│     Contains images used for presentation and/or EDA
│      
│    
│          
└──models
│     model_five_rf_feature_union.ipynb
│     model_four_rf.ipynb
│     model_one.ipynb
│     model_three_lr_feature_union.ipynb
│     model_two.ipynb
│  
│ 
└──raw_data
      reddit.csv

```

### Conclusion & Next Steps
Using my most accurate model, which was built using Logistic Regression, and the aforementioned engineered features, I was able to predict that a post came from the Backpacking subreddit with 93.3% accuracy. Comparing this result to the baseline model that predicts with 50.0% accuracy, this model is more useful in identifying target markets in potentially conflicting market spaces. 

In focusing on the misclassified observations, I have been able to observe that in a number of posts, the wording was ambiguous and thus very challenging to accurately classify. My next step will be to generalize my model to hopefully account for some of the ambiguous terminology in the subreddit posts. Additionally, I would like to focus on improving my model by using such techniques as boosting or stacking, to hopefully improve the accuracy at which the model classifies.
