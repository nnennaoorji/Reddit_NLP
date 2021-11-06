# Classifying r/GRE and r/GMAT Posts: An Application of Natural Language Processing and Machine Learning 


## Problem Statement

In a hypothetical scenario, Manhattan Prep has hired me as a Consultant to build a machine learning model which is able to distinguish between posts which come from the r/GRE subreddit and the r/GMAT subreddit. The company would like to leverage NLP in improving user experience. The aim is to remain a top choice for GRE and GMAT resources.

## Executive Summary

Natural Language Processing is a tool that is increasingly being adopted by organizations in different fields to obtain raw customer feedback to better understand clients needs, and boost user experience. Manhattan Prep, a subsidiary of Kaplan Inc. is a schooling company, which amongst other services, produces top rated test preparation materials for the GRE, GMAT, LSAT and EA assessments. 

In a hypothetical scenario, the Company has hired me as a consultant to build a machine learning model which is able to accurately distinguish between posts from the GRE (r/GRE) and GMAT (r/GMAT) subreddits. The aim is to leverage this raw data, as potential feedback from its customers on the quality of its products related to both tests, which the Company can use as insights to continue to ensure that it is meeting test takers' needs. Ultimately, Manhattan Prep aims to remain a top choice for GRE and GMAT resources. 

To gather data for the analysis, a while loop was used to pull data from reddit using [Pushshift's](https://github.com/pushshift/api) API. A total of 10,000 posts and 8,500 posts were scraped from r/GRE and r/GMAT, respectively. Following data cleaning, count of data for r/GRE and r/GMAT were 9,447 posts and 8,072 posts, indicating a baseline accuracy of 54% and 46%, respectively. Titles and Self texts of each post were adopted as explanatory (X) features, while a binarized column indicative of each subreddit was adopted as the target (y) variable. Using scikit-learn's train/test split function, 25% of the dataset was set aside for assessing model performance on "unseen" data. 

Four classification models were estimated to meet the project's objective. These included a Multinomial Naive Bayes (MNB) model, a Random Forest (RF) model, and 2 logistic regression (Logreg) models. The second logistic regression model was estimated on a sub-sample of the dataset labelled "manhattan" which captured instances where "manhattan" was mentioned at least once in a self text. Utilizing VADER, a Sentiment Analysis was also conducted on this sub-sample to gauge users' overall sentiments about products related to the Manhattan Prep brand. 

All 4 models were low bias and low variance and recorded high accuracy scores. The MNB, RF and Logreg model (on overall sample) recorded 90% accuracy, while the Logreg model estimated on the Manhattan subsample had an accuracy score of 94%. Sensitivity and Specificity scores were also high across board, ranging from 80% to 98%. Findings from the VADER model were that sentiments associated with Manhattan Prep in both subreddits were neutral on average, and did not differ significantly between both subreddits. 

Overall, this study recommends the Logistic Regression model specified as the algorithm of choice for distinguishing between posts from r/GRE and r/GMAT. This is due to faster computational speed, higher sensitivity and specificity scores, relative to the other models. The study additionally recommends that deeper analysis be conducted on posts where compound sentiment scores associated with Manhattan Prep were negative, in order to uncover ways to potentially boost user experience. 
