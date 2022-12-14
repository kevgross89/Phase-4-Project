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

|              **Type of Model**             | **Training Accuracy** |
|:------------------------------------------:|:---------------------:|
|               Baseline Model               |         87.53%        |
|              Stopwords Removed             |         90.76%        |
|                   Stemmed                  |         90.75%        |
|                 Lemmatized                 |         90.02%        |
|             Engineered Features            |         97.79%        |
|            Bigrams and Trigrams            |         87.93%        |
|       Bigrams and Trigrams Engineered      |         97.56%        |
|   Bigrams and Trigrams Stemmed Engineered  |         97.40%        |
| Bigrams and Trigrams Lemmatized Engineered |         97.37%        |
|     Engineered with Additional Features    |         97.97%        |

|              **Type of Model**             | **Training Accuracy** | **Testing Accuracy** |
|:------------------------------------------:|:---------------------:|:--------------------:|
|             Engineered Features            |         97.79%        |        98.05%        |
|       Bigrams and Trigrams Engineered      |         97.56%        |        97.72%        |
|   Bigrams and Trigrams Stemmed Engineered  |         97.40%        |        97.61%        |
| Bigrams and Trigrams Lemmatized Engineered |         97.37%        |        97.62%        |
|     Engineered with Additional Features    |         97.97%        |        98.26%        |

The final model performed very well - it was able to identify real news and fake news correctly 97.97% of the time on the training data and 98.26% of the time on the testing data.

## Recommendation

This model should be utilized by CNN when they are scraping the web looking for news to report on. By using this automated process, CNN will be able to save time, money and resources by having a machine comb through news articles and be able to **accurately predict whether or not an article is real news or fake news over 98% of the time**.

Additionally, our data was a bit dated so we could attempt to find newer data. News and technology changes at a rapid pace so it is hard to know if our model is still relevant. Furthermore, we could try to add in more engineered features such as average word length and maximum word length. These statistically engineered features will help our model become more accurate. Lastly, we could look at when each article was published to see if there is a time series analysis that we could run to see if real news and fake news stories have changed over time. Maybe fake news articles spike around elections or midterms, or maybe they operate in some sort of cyclical pattern. 

![FakeNews](https://github.com/kevgross89/Phase-4-Project/blob/main/Images/fake-news-1600-x-840-62e8dd9ad22e7-sej.png)