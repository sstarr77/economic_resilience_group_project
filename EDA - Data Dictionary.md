### EDA Data Dictionary

This data dictionary provides an overview of features/variables/columns, alongside data types and descriptions. 

|Feature|Type|Source|Description|
|---|---|---|---|
|**title**|*object*|engineered_data_title_and_selftext.csv|Title of the Reddit post|
|**selftext**|*object*|engineered_data_title_and_selftext.csv|Selftext within the Reddit post| 
|**subreddit**|*object*|engineered_data_merged_columns.csv|Identifies which Subreddit the post was from. Options are backpacking or ultrarunning|
|**created_utc**|*int*|engineered_data_merged_columns.csv|Date of Reddit post, in Unix Epoch time| 
|**title_merge**|*object*|engineered_data_merged_columns.csv|Combination of **title** and **selftext** columns| 
|**title_sentiment_neg**|*float*|engineered_data_merged_columns.csv|A sentiment intensity score received from the SentimentIntensityAnalyzer. Sentiment strength is based on the input text: positive values are positive valence, negative values are negative valence| 
|**title_sentiment_neu**|*float*|engineered_data_merged_columns.csv|A sentiment intensity score received from the SentimentIntensityAnalyzer. Sentiment strength is based on the input text: positive values are positive valence, negative values are negative valence| 
|**title_sentiment_pos**|*float*|engineered_data_merged_columns.csv|A sentiment intensity score received from the SentimentIntensityAnalyzer. Sentiment strength is based on the input text: positive values are positive valence, negative values are negative valence|
|**title_sentiment_compound**|*float*|engineered_data_merged_columns.csv|A sentiment intensity score received from the SentimentIntensityAnalyzer. It is derived from the sum of positive, negative & neutral scores which is then normalized between -1 and +1|
|**title_length**|*int*|engineered_data_merged_columns.csv|Number of characters within the **title_merge** column|
|**title_word_count**|*int*|engineered_data_merged_columns.csv|Number of words within the **title_merge** column|
|**capitalized_letters_in_title**|*flintoat*|engineered_data_merged_columns.csv|Number of capitalized letters within the **title_merge** column|
|**sentences_in_title**|*int*|engineered_data_merged_columns.csv|Number of sentences within the **title_merge** column|