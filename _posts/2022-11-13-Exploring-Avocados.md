---
layout: post
title:  "Exploring Avocados"
date:   2022-11-13
author: Jackson Switzer
description: Know your price! Exploratory Data Analysis of a dataset about prices and sales of avocados
image: /assets/images/avocadopic.jpg
---

## Introduction (and a due apology)

First I need to apologize. Fans of the blog will know I promised an analysis of the Rate My Professors data of BYU religion faculty. The issue is, Rate My Professors updated their code since I wrote my webscraping blog, and my code no longer works. I should have saved the dataframe, I know. But I didn't. After an hour fiddling around, I decided it wasn't worth the time to keep trying to get it working again. So this exploratory data analysis, unfortunately, is about something else, something--dare I say it--even more important.

Avocados are a staple food of the rising generation. Without them, millenials' favorite snack (avocado toast) would just be toast. Naturally, many millenials take the local avocado market into account when deciding where to live. This exploratory data analysis should help readers get a feel for the ebb and flow of avocado prices and know where the avocado market is booming.

I promise this analysis is ethical, just as the collection of my previous dataset was. I downloaded the data from [here](https://www.kaggle.com/datasets/neuromusic/avocado-prices). It's a public Kaggle dataset. My title picture is also available for public use, taken from Wikimedia Commons.

## Distribution of Average Weekly Prices

We have thousands of weekly averages for hass avocado prices. I can see they vary a lot from week to week, but it's hard to tell what a typical price is and to quantify the variability. The histogram below, of the price in dollars, helps us visualize this.

![Histogram of average weekly prices](https://raw.githubusercontent.com/jacksonswitzer/stat386-projects/main/assets/images/avg_price_histogram.png)

We can see that the price is typically between $1.00 and $1.50 per avocado, and it sometimes reaches as low as $0.50 and as high as $3.00.

Here is the code used to generate the above plot. To avoid visual clutter, I'll leave out the code for the rest of the plots, but those interested may find it in my GitHub repository, linked at the end of the post.

```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.color_palette("tab10")  #set a simple color palette
sns.set(rc={'figure.figsize':(11.7,8.27)})  #make the plot output larger than the default
ff = sns.histplot(data=d['AveragePrice'])  #specify the variable to chart
ff.set_xlabel('Average Price')  #change x and y labels
ff.set_ylabel('Number of weeks since the start of 2015 with this average price')
plt.show()
```

## Average Sales by Region

We also have data about how many avocados were sold, and in which part of the country. By making a bar chart of average sales per week in each region over the four-year time period, we see that some markets sell far more avocados than others. Los Angeles and surrounding areas by far sell the most avocados, and Syracuse comes in at last.

![Bar chart of sales by region](https://raw.githubusercontent.com/jacksonswitzer/stat386-projects/main/assets/images/sales_by_region.png)

## Average Price Over Time

A third useful visualization is to see how avocado prices have changed over time. The histogram gives us a sense of the distribution, but not a sense of whether price and time are correlated.

![Plot of average prices by month](https://raw.githubusercontent.com/jacksonswitzer/stat386-projects/main/assets/images/avg_price_over_time.png)

We see in this plot that the price hasn't followed one simple, steady progression, but there are patterns; it hasn't typically changed dramatically in a single month.

## Conclusion

An EDA like this helps us understand the composition of large datasets and guides our research questions. Now millenials know which regions have the highest avocado consumption, so they can move to a place which helps them associate with like-minded avocado lovers. For any questions about the code, check out [the GitHub repository](https://github.com/jacksonswitzer/avocado_eda); if you have any questions you'd like answered from the data, let me know in the comments, and you can look forward to it in a future post.
