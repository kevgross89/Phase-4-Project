# Phase-4-Project

![CNNImage](https://github.com/kevgross89/Phase-4-Project/blob/main/Images/CNN-logo.png)

## General Overview

The stakeholder for this project is CNN (Cable News Network) which is a multinational 24 hour cable news channel. Specifically, this project is a tool that their news and reporting department could use to help identify real news vs. fake news.

From their [website](https://www.cnn.com/about) CNN's mission is below:

> **To Inform, Engage and Empower the World**
>* We are truth-seekers and storytellers. 
*We are journalists, designers and technologists, united by a mission to inform, engage and empower the world. 
*We bear witness to history as it unfolds and explain not just what happened, but why, and what it means to you. 
*Our products and platforms take you to the farthest corners of the world, and they bring the world to you, delivering content and services that enrich your lives, your families and your communities.
*We are available on more screens in more places than any other news source.
*We stand for excellence in our journalism and our products.
*We are committed to serving you.
*We are CNN.

## Business and Data Understanding

With so many sources of information online, it has become increasingly difficult to make sense of what content is based on fact, half-truths or lies. The use of digital platforms to share things we believe to be true when they may not can have a powerful ripple effect, influencing others to see them as facts.

Companies such as CNN pride themselves on reporting news that is real because if they were to report on news that is fake, their reputation would be severely damaged, and people would no longer turn to them for news. According to an [article](https://www.cnn.com/2021/05/31/health/fake-news-study) from CNN, "as many as three in four Americans overestimate their ability to spot false headlines – and the worse they are at it, the more likely they are to share fake news".

This project looks at over 40,000 articles from 2017, about half of which are real and half of which are fake. The data was pulled from [Kaggle](https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset?datasetId=572515&sortBy=voteCount) and includes the articles in text format in two different CSV files - one for real news and the other for fake news.

## Data Preparation

For this project, the data underwent common data cleaning tasks for text data: standardizing case, removing punctuation, and tokenizing. From there, all of the single letter words removed since they did not contain useful information. Additional data modification was used during the modeling phase to help maximize the accuracy of the model.

## Modeling

This project starts with a baseline model using a `TfidfVectorizer` and `MultinomialNB` classifier using `Cross_Val_Score`. From there, the model iteratively builds eliminating and adding features such as stopwords, stemming and lemmatizing words, engineering features, and adding in additional features. `NLTK` was used frequently throughout the modeling and preparation phases.

## Evaluation

The final model performed very well - it was able to identify real news and fake news correctly about 98% of the time on both the training and testing data.