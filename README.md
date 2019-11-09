# Project 3 - Webscraping Reddit


## Problem Statement
In today's day and age of interconnectedness and oversharing, large retailers are at risk of falling behind the times and losing touch with the people they are responsible for as well as the people they serve.  Customers and employees alike are continually frustrated with their respective experiences - whether it be at a store, the movies or a restaurant.  This is evident given the amount of grief posted online .  People are sharing their negative experiences with each other, while retailers are left  out of the loop - despite having survey data and other resources available to them.  Retailers should strive for the satisfaction of both their employees and their customers, as it leads to better experiences and brand loyalty.

In order to unlock that level of satisfaction, retailers must first understand the general sentiment surrounding them - digging through the postings of reddit.com will help us do just that. However, we need to be able to differentiate between posts made by employees and customers in order to accurately use the data.  In order to do so, we will iterate through the models below in order to determine which is best for the task of identifying a post's subreddit:

- Logistic Regression (CountVectorized)
- Multinomial Naive Bayes
- Logistic Regression (TFIDTVectorized)
- Gaussian Naive Bayes

We define our best model as that which can successfully predict which subreddit a particular post came from with a high level of accuracy.  In other words, how accurately can our model distinguish between employee woes and customer woes?

## Project Files
- [NLP_with_Reddit_Notebook](./code/NLP_with_Reddit_Notebook.ipynb)
- [combined.csv](./datasets/combined.csv)

## Executive Summary
We began the process by scraping the social platform reddit.com.  We leveraged the posts found on r/TalesFromRetail as well as r/IDontWorkHereLady.  Once sufficient data was collected, we saved the output as a csv file in order to access across multiple steps in our code notebook.  In importing the csv file into a cleaning step, we took note of a couple of observations such as:
- There was a high number of common English words in both subreddits, which would be ineffective in solving our problem
- There also was a high number of common words shared in both subreddits, which would also be ineffective in solving our problem

We rectified the above by having our models eliminate the referenced words from the process, in hopes of becoming more accurate.

After understanding the data that we will be working with and cleaning it up for our models' use, we established  a baseline model score of .50 - meaning that our baseline model was 50% accurate in predicting which subreddit a post came from.  This was the score to beat for all models going forward.  With the below results, beat it they did.

Model    | Train Score | Test Score
  ------------- | ------------- | ------------- 
  Baseline                       | 0.5000  | 0.5000
  Logistic Regression (CVec)     | 1.0000  | 0.9238
  MultinomialNB                  | 0.9940  | 0.9641
  Logistic Regression (TFIDFVec) | 0.9985  | 0.9462
  GaussianNB                     | 0.9985  | 0.9731


## Conclusion & Recommendations
From the results of our analysis (the table above) we have concluded that the GaussianNB was the best performing model - predicting which subreddit a post came from with a 97.31% accuracy rate.  Not only does the Gaussian have the best test score overall, but it also has the smallest amount of discrepancy between its train score and its test score - meaning that the model is not as overfit (large bias) as the rest of the models.

Now with the ability to distinguish between employee and customer woes, retailers can work on leveraging the general sentiment for their benefit.  By determining which employees have went above and beyond, retailers can highlight their actions, giving them 'out-performance bonuses', promoting model employee behaviors and increasing productivity.  This ultimately leads to improving a retailer's bottom line.  As with customers, retailers promote brand loyalty by rewarding customers for their actions via exclusive rewards programs or employee discounts.

Ultimately, this process helps retailers keep their finger on the pulse and reduce the risk of being out of touch, and possibly losing great employees and loyal customers.

## Source Documentations
- [Reddit - Tales From Retail](https://www.reddit.com/r/TalesFromRetail/)
- [Reddit - I Don't Work Here Lady](https://www.reddit.com/r/IDontWorkHereLady/)
