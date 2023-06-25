# Headline_Hindsight
Irti Haq| Andrew Simon | Jeleen Limawan | Joeph Rafael

Original Notebook: https://colab.research.google.com/drive/1GdG6mq2tDLAWhj9I-Gkv2TWDhMfmj9Xm?authuser=2#scrollTo=2ELJONJmxkDj

Video Demonstration: https://youtu.be/Jx4vaVxZVG8 

News headlines are used to capture attention, summarize, and inform readers of current events or they can be used to deceive, misinform, and manipulate us. If taken advantage of they provide us with a glimpse into the past and when used right can be one of the greatest orators of history; creating a microcosm that captures a period unlike anything else. 2016 to 2020 has for the most part been one of the most turbulent, interesting, and contentious periods in the 21st century. We have had everything from the election of Donald Trump, Brexit, and the start of the COVID-19 Pandemic. 

Our goal here is simple. Headlines can be a powerful tool to look at the past. Using the power of Machine Learning and Clever Data Visualization we hope to take advantage of headlines and use to them to document and capture the essence of this turbulent and consequential period in an objective way and uncover any forgotten or hidden patterns and insight. Ultimately creating tools that can help both our future selves and generations remember and understand what happened in the past. 

While headlines are powerful tools that can capture a period like nothing else, they aren’t infallible. As the title of this document demonstrated they are susceptible to bias and manipulation.  As article readers, it is important that we are aware of biases in news headlines and publication companies. In many ways, depending on our preferred news outlet and background we can easily end up living in entirely different worlds. As such a secondary goal of our project is to capture and communicate biases in the major news publications by looking at the differences and distribution of the topic covered. 

To achieve these goals, we hope to start by answering the following questions Throughout this notebook:
- What were the most common words brought up in news headlines and how has this varied over time?
- What are the relationships between words found in news headlines and do uncover or are associated with any hidden meanings and relationships? 
-  What are some of the biggest news topics and how have they varied over time? 
- What are the distribution and differences in the coverage of certain topics and events among the major news publications?

## Dataset
[All the News 2.0 — 2.7 million news articles and essays from 27 American publications - Components](https://components.one/datasets/all-the-news-2-news-articles-dataset/)

### About the Dataset
The dataset we are using is a collection of articles scrapped and cleaned from the top 27 American publications. [Link](https://components.one/datasets/all-the-news-2-news-articles-dataset/). There are 2.6 million articles in the dataset and they are from January 1, 2016, to April 2, 2020. The dataset contains when the article was published, the publication, the headline, and the contents of the article and has already been cleaned and is ready to analyze for the most part. There are a few parts things we had to take care of in our cleaning including removing a few articles that were either missing headlines or publications.

### Legitimacy
We concluded our dataset is legitimate and fits our needs through the following points:
- dataset includes articles from news sources all across the political spectrum from Fox News (right-wing publication) and Vox (left-wing publication)
- dataset includes 27 of the top publication companies and has 10s of thousands of articles per news source
- dataset has been used in multiple academic papers, including one by Kriste Krstovski ([Link](https://arxiv.org/abs/2209.08129))
- data source is very transparent about the methods it uses to collect the data and the amount of data it has including the number of articles from each publication and the number of articles from each year
- dataset houses 2.6 million news articles, which is enough for the purpose of this visualization
- the data contains scraped data either directly from the news source itself or Archive.com which is also a reputed source for internets archives

While it might not be a definitive source for news articles from that period, for our purposes, we believe that it should be adequate, the fact is we are trying to use the dataset to find overall patterns and for that, the size is what's most important and the spread.

### Data Processing
Given the size of our dataset, we had to preprocess the dataset in order to use it. The following are ways in which we preprocessed the data:
- removed the author, article, URL, and section columns to reduce the size of the dataset
- removed some of the more lifestyle-oriented publications, as some articles included book reviews or articles that did not include news
- filtered out some of the smaller less well-known publications as well
- removed articles that had missing data like either the publication or the headline
- removed articles that had less than 2 words since these headlines were all a result of scraping error
- used Non-Negative Matrix Factorization (NMF) to do some topic modeling using the headlines from our dataset.
- filled out any NAs with empty strings, removed any punctuation and made all of the headlines lowercase, removed stop words and other words that were either appearing too often or where inappropriate like the names of publications
- fixed and replaced contractions
- trained the model using Scikit Learn to calculate the TF-IDF (Term Frequency – Inverse Document Frequency) Matrix for headlines and non-negative matrix factorization of the TF-IDF Matrix to get both the Word Scores and Headline Scores for each of the topics for each year
- tuned hyper-parameters
- converted numpy matrixes to data frames
- took a sample of the dataset, due to its overwhelming size

All of The Code used to Pre-Process the Dataset and Train the model can be found in the NMF_CP2 Jupyter Notebook [Link](https://colab.research.google.com/drive/1RM6nXakddB3tf3MZPiWBKclSaAum9c9_?authuser=2#scrollTo=Ruvyu_kj6U5V)
