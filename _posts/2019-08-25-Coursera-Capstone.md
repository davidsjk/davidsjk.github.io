---
title: "City Score"
date: 2019-08-25T15:34:30-04:00
categories:
  - blog
tags:
  - Coursera
  - Foursquare
  - Data Analysis
  - Data Science
  -
---
Predicting City Score Using Venue Frequency

**Introduction:** Every year, UN News analysis the 125 most populous cities of United States to determine the best cities to live. These cities are given an overall score from 0-10, and a ranking from 1-125. In order to be competitive in the Realestate business, or to personally purchase home in a nice neighborhood before the prices of homes rise, it is important to use data to predict potential cities that will become popular in the future. Although the Rankings provided by USNEWS is very helpful in determining current hotspots, as potential home buyers, it is imperative to be ahead of the curve and purchase a home in a city before the popularity and prices rise. Therefore, using the data gathered from Foursquare, we will attempt to identify variables that correllate with city popularity represented by the City Scores, which could potentially help us find cities that will become popular in the future.  
{: .notice}

**Interest**

This analysis may be useful to the following groups:

1. Real-estate Agents looking for potential cities to work in.
2. Individuals looking for a good place to live.
3. City developers and officials seeking to improve their cities can also use this information to determine what types of venues to increase or decrease.

**Procedure**

We began by creating a dataframe with the 5 top scoring cities and the 5 lowest scoring cities.
![5 top scoring cities and the 5 lowest scoring cities](/assets//images/Picture1.jpg)

Next, using the Foursquare API, we gathered venue information of each city.
The frequency of each venue category for each city was calculated using the information gathered from Foursquare.
![Venue Frequency](/assets//images/Picture2.jpg)

**K-Clustering:** To explore the data gained from Foursquare, we conducted a K-cluster analysis to see if the venue frequencies by themselves would create clusters that more or less aligned with their city scores. The initial analysis with the 10 cities revealed that there were cities with not enough data that was skewing the clusters. The initial cluster visualized onto a map can be found below.
Upon eliminating the cities that did not have enough venues and reducing the k to 2, the cluster formed according to city scores, with Austin and Denver in once cluster and San Juan, Stockton, and Mobile in the other.
{: .notice--info}
![K-clustering of Cities based on Venue Frequency](/assets//images/Picture3.jpg)

**Correlation**

Using Pandas .corr() function, the correlation of the venue frequency and the city scores were calculated. Upon inspection, 7 venues were found to be positive correlated with the city scores with a correlation score greater than 0.83. (Café, Clothing Store, Dessert Shop, Restaurant, Salad Place, and Theater)

**Multi Linear Regression Model:**   A multi linear regression model as created using the data from the remaining 5 cities. The city score was chosen for the dependent variable and the frequency of the 7 positively correlated venues were set as the independent variable. The model was tested using the venue frequency data gathered for the 4 test cities ((San Francisco, Phoenix, Memphis, and Scranton), and the predicted score was compared to the actual scores found on US NEWS.
{: .notice--info}
![Predictive Model](/assets//images/Picture4.jpg)

**Conclusion:** 1.	Conclusions
In this study, I analyzed the relationship between venue frequency and the overall city score based on the study conducted by US News. Using the correlation function and the K-cluster analysis, I identified that there was a positive correlation between the city score and the venue frequency of 7 venue categories (Café, Clothing Store, Dessert Shop, Restaurant, Salad Place, and Theater). I created a Multi Linear Regression Model and tested my theory that city scores can be predicted using venue category frequency. Although, many improvements can be made, the model was fairly successful in predicting the scores of randomly picked cities. Such prediction models can be used to assist real-estate agents and individuals looking to purchase a home in deciding which city to invest in. It can also help city planners in picking the next venue to invite  into their city.
{: .notice--success}

References:

[U.S. NEWS - Best Places to Live](https://realestate.usnews.com/places/rankings/best-places-to-live?sort=overall&high_to_low=true)

[Foursquare](https://foursquare.com)
