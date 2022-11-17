# Project 3 - Classifying Reddit Posts (Depression and Anxiety) with Natural Language Processing and Machine Learning 

## Introduction
Mental illness is highly prevalent worldwide, constituting a major cause of distress in people's life with impact on society's health and well-being. Depression and anxiety are psychiatric disorders that are observed in many areas of everyday life and affect millions of people worldwide. 
These mental disorders manifest somewhat frequently in texts written by non diagnosed users on social media. Furthermore, social stigma around mental disorders influenced people to not speak out and turn to other means (eg. social platforms). For the scope of this project, I focused on scraping texts from Reddit, which is one of the common platforms for people to explode and share their thoughts. 

These are the two subreddits:

- Anxiety subreddit: https://www.reddit.com/r/Anxiety/
- Depression subreddit: https://www.reddit.com/r/depression/

## Problem statement

As such, it would be interesting to explore how we can help Reddit and other interested parties classify texts based on the differences in words used by people who suffer from depression and anxiety through natural language processing and classification models? Furthermore, how can sentiment analysis be utilized to detect emotions associated with depression and anxiety? 

## Data Cleaning and Preprocessing
- In this section, I checked for null values and re-labelled the subreddits topic (0 = anxiety, 1 = depression) before combining the titles and texts into a dataframe. 
- Created 2 separate columns for word and character count, which will be essential for the sentiment analysis portion where the models have a word count limit. This step is also useful to examine the distribution in number of texts written for each subreddit, but we did not find a significant difference between sub-reddits for average words/posts.
Preprocessing 
- Removed duplicate rows due to glitch on Reddit when users encounter errors, resulting in double posts.
- Removed default and custom stop words

Vectorizing (transformed text to vector forms)
- Regex to remove symbols and digits
- Tokenization: lower case and lemmatization
- Unigrams, Bigrams, and Trigrams 

## Modeling

The best model is Model 4 (TFIDF and Random Forest Classifier) with a test score of .838. See below for a list of models and their respective scores.

| Model      | Train score | Test score |
|------------|-------------|------------|
| CV and Logistic Regression (Baseline)   | .932        | .850       |
| CV and BernoulliNB      | .841        | .829       |
| TFIDF and MultinomialNB  | .845        | .829       |
| TFIDF and Random Forest Classifier  | .857        | .838       |


## Sentiment Analysis - Hugging Face

To address part 2 of the problem statement, I conducted a sentiment analysis using 2 models from hugging face to further label each post with the specific emotion(s). The question to think about is among those who experience depression and anxiety, what is the underlying root cause for such mood disorders? One explanation is that on top of feeling sad or anxious (primary emotions), these people could be feeling hurt, nervous, fearful, or annoyed. Hence, I hope that using a model that examines primary emotions (Model 1) as well as secondary emotions (Model 2) would provide some deeper insights into how people are feeling when they write their reddit post. 


### Hugging Face - Model 1 (jhart)

Model 1 has been trained on 6 diverse datasets predicting Ekman's 6 basic emotions + a neutral class. This model aims to classify emotions from English text data. 

- https://huggingface.co/j-hartmann/emotion-english-roberta-large 


### Hugging Face - Model 2 (arpanghoshal/EmoRoBERTa)

This model classifies emotions into 28 emotions, which includes primary and secondary emotions. 
- https://huggingface.co/arpanghoshal/EmoRoBERTa

### Overall thoughts on both models

I tested out both models to see if they would give the same prediction, turns out they did. However, this is only 1 data point and should be tested further.

On another note, I attempted to compare the results from the model against some manual coding and there were some discrepancies. Given that this project is a pilot one, it would be important for future projects to take a deeper look. In sum, Model 2 does not seem to predict that well, especially on long texts. Another reaason could be the large number of emotions (28) present in Model 2, compared to a smaller number of emotions (7) present in Model 1.

## Conclusion

To conclude, I hope that this project is a first step to work towards predicting/identifying the emotions associated with certain mood disorders. I was able to accurately classify topics based on texts using the proposed model. Moreover, this work shed light on the underlying feelings behind one's mood disorder. Both models provided great insights as to how the Redditors may have felt when writing the posts. This alone is an added layer of showcasing certain root emotions, beyond depression or anxiety.

However, there are some limitations that we need to consider for future work. 
- Data were retrieved from a specific time period. This could be a biased sample and more data could be included and across different time periods.
- Only texts, specifically lowercase, were included. This may have excluded punctuautions (e.g., !!! and ...) whereby the former may indicate screaming for help and the latter may indiciate feeling dejected. Emojis, pictures, videos, and gifs were also excluded. "A picture speaks a thousand words" and it is important to examine these in future. 
- The data only included English texts. As such, the results may only be generalizable to English speaking countries. Including texts from other languages would be helpful in broadening the scope of NLP and mood disorders.
- The geographical location is unknown. Looking at where the posts were published could allow us to provide more support where its needed and highlight the issues to government bodies.

## Recommendations for various parties (e.g., developer, moderators, stakeholders)
All parties could work together to: 
- create a system whereby it can automatically identify key words and provide support by flashing the suicide hotline. 
- create a dashboard for moderators. The top emotions can be shown after a post has been publsihed. Thereafter, the moderators can pin a response message to provide support to redditors.
- flag out potential posts that match certain emotions first, examine the links between the posts and suicide ideation, before making accurate predictions. 

