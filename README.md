# Podcast Review Data Analysis

This project is an analysis of podcast review data from iTunes US, aiming to get insights into the popularity of different podcast categories between 2005 to 2023.   

## Format

The analysis is performed with SQL and python, in a Jupyter notebook. And partly in a Looker studio [dashboard](https://lookerstudio.google.com/reporting/1868b3da-f6c9-4913-bce3-90613320b13c/page/p_p0d8qtyjpc)

## Dataset

The dataset comes from a website called Kaggle, to be found in sqlite format via [this url](https://www.kaggle.com/datasets/thoughtvector/podcastreviews/versions/28).
The raw dataset consists of 3 tables for podcasts, reviews and categories respectively, each containing 2 to 7 features. The tables can easily be joined as they all contain a common podcast_id. The dataset contains 2 million reviews of over 100k podcasts on iTunes US. Each review consists of a written text and 1-5 star rating, and could be categorised in one or more ways. 

In total there are 110 categories, of which main and subcategories, which makes that some podcasts are categorised in multiple ways, under one (or more) main categories and subcategories that fall under the main. We here work with one categorisation for each podcast, in order to avoid double counting. We aimed to choose the highest level possible for each podcast, however, there are podcasts under each of the 110 categories. 

In this analysis, we would like to find out:
* How many reviews and which average rating score an individual podcast gets on average. 
* Which categories had most podcasts, most reviews and highest average ratings overall, and over the years.
* How the above differed over the years. 
* Whether the year with the highest average rating and the year with the highest review volume differ in their average ratings.
  
For the latter, we investigate correlations between review volumes and average ratings, then run a t-test to find out whether the average rating is significantly lower in 2020: the year with the highest review volume, compared to 2015: the year with the highest average rating.

## Limitations

One downside of this dataset is that it is relatively small in terms of features, and thus there isn't much data on characteristics that could explain why some categories are more popular. For example,  user engagement data would have been interesting, to see how many people listened the entire podcast, how many minutes people listened on average, which % of the podcast duration this was etc. 
The quantitative features were deviating strongly from normality in their distribution. 
