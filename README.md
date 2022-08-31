# Social_Media_Sentiment_Analyis

In this project we set out to determine if social media sentiment of a controversial content creator/artist can influence their viewership/sales. For our case study, we chose to focus our attention on Joe Rogan, a renown sportscaster and number one podcaster in the world.

# Data

We gathered data from three separate sources:
● Twitter: Using the snscrape library, we scraped 80 Mb worth of data, amounting to over 400,000 tweets posted in the last 500 days.

● Reddit: Using the reddit API, we scraped 15 Mb worth of data, gathering posts made in the last 500 days.

● Youtube: We scraped data from the website socialblade to gather the weekly viewership of Joe Rogan’s channel between November 2020 and now.

● After gathering all the data, we uploaded it to S3.

# Preprocessing

Using Spark, we did following preprocessing operations:
● Unioned twitter and reddit spark dataframes, joined on date.

● Added Youtube viewership data as a column, joined on date.

● Feature Engineering:

  ○ Text length (Count of characters): ran in 0.45 seconds
  
  ○ Emotion label (using Roberta English model): ran in 2.78 hours
  
  ○ Sentiment 1 score (using VaderSentiment model): ran in 17.47 minutes
 
 # Modelling:
 
 We then ran our data through three different models (Linear Regression, Random Forest, XGBoost) with viewership as a target variable. We determined some features to be significant, and concluded that social media sentiment is positively associated with an artist's viewiership numbers.
 
 Thank you to my partners Anthony Wang and Lawrence Lin for working on this project with me.
