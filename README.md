# Time-Series
---

Unit 10: Forecasting Net Prophet - MercadoLibre

---
For this assignment, I was tasked with finding out if Google search traffic for MercadoLibre links to any financial events for MercadoLibre, which is the most popular e-commerce site in Latin America with over 200 million users. For this analysis I utilized Google collab and Facebook's Prophet, along with Python libraries such as pandas and hvplot for the visualizations.

---
## Step 1: Find Unusual Patterns in Hourly Google Search Traffic

For Step 1, I read in the 'google_hourly_search_trends.csv', which has data regarding Google search traffic for MercadoLibre for every hour (indicates popularity). First, I looked at the Google search trends for the month of May, which is when MercadoLibre releases their quarterly financial results. When visualizing the data using hvplot, Google search traffic for MercadoLibre tends to oscillate everyday at similar times. From 8 a.m. to around 1 a.m. the search traffic gradually increases, then after 1 a.m. the Google search traffic decreases until the morning. 

When comparing the Google search traffic for the month of May compared to all other months, it turns out there is around a 8.5% increase in Google search traffic for the month of May, confirming that when MercadoLibre releases their quarterly financial results, that it increases Google search traffic for the company. 

---
## Step 2: Mine the Search Traffic Data for Seasonality

For step 2, I was tasked to mine the search traffic data to analyze any predictable seasonal patterns of interest in the company.
I first grouped the Google search traffic data to show the average search traffic for the days of the week. The hvplot I created indicates that search trends are at its highest on Monday, Tuesday, Wednesday, and Thursday then gradually fall throughout the rest of the week. Specifically, Tuesday has the most search traffic out of any weekday. 

I then created a heat map that visualizes how much search traffic there is for each day of the week for each hour of the day. This visually confirms what I've already analyzed. How hourly search traffic gradually increases from 10 a.m. to around 1-2 a.m. after midnight. It also seems that there is more search traffic for the first half of the week (however it does seem consistent throughout the week). Specifically, I would say search traffic is concentrated from 10 p.m. to 2 a.m. from Tuesday to Thursday.

Lastly, I graphed the average hourly google search traffic trends for each week in the year. It seems search traffic increases alot from weeks 42 to 51, which is the holiday season, so it makes sense. Furthermore, it takes a sharp dip for the last week of the year, then shoots all the way back up for the first couple months in the new year.

---
## Step 3: Relate the Search Traffic to Stock Price Patterns

For step 3, I wanted to know if any relationship between the search data and the company stock price exists. To begin this analysis, I read in the 'mercado_stock_price.csv', which has hourly stock data for MercadoLibre. When visualizing the close prices over time, it's apparent that from 2016 to 2020 there was a substantial increase in value for company. 

Many companies had trouble in the market at the beginning of 2020. However, after that initial shock, many e-commerce platforms found new customers and increased revenue. I wanted to see if this narrative was true MercadoLibre as well. To see if this was true, I had to splice the stock and search traffic data for the first half of 2020. It seems that MercadoLibre did end up gaining more revenue as a result since close prices were higher in June 2020 than they were in January 2020. On the other hand, hourly google search traffic looks like it overall decreased in 2020 after the initial shock. My theory is that MercadoLibre didn't gain more customers, but their existing customers were ordering more items due to the pandemic, which is how search trends didn't increase, but the value of the company increased. 

I later created columns for Stock Volatility, Lagged Search Trends, and Hourly Stock Return to see if a relationship existed between any of them. I found that there is a negative coefficient between Stock Volatility and Lagged Search Trends, which indicates there is a slight negative correlation between them. So as Stock Volatility goes up, Lagged Search Trends go down, and Vice Versa (keep in mind this relationship is loosely correlated).

---
## Step 4: Create a Time Series Model with Prophet

For Step 4, in summary, I used Facebook's Prophet to predict hourly google search traffic for MercadoLibre for the end of 2020. In short, my predictions indicate hourly google search traffic will decrease and level off for the end of 2020.

When viewing separate components of my predictions, the only thing worth noting that hasn't already been said is that hourly search traffic is at its lowest at end of October into November but will go up for the last couple weeks due to the holidays.  

---
## Step 5 (Optional): Forecast Revenue by Using Time Series Models

For Step 5 (the final step), I wanted a forecast of the total sales for the next quarter. This will help MercadoLibre with budgeting and help guide expectations for the company investors.
I read in the 'mercado_daily_revenue.csv' which contains daily historical sales figures (revenue data) where sales figures are quoted in the millions (USD).
When visualizing this data, it shows that MercadoLibre has been consistently increasing their daily revenue for the past year.

I used Facebook's Prophet to predict revenue for 3 months after May 2020 (so until around mid-August 2020). When plotting the components for my prediction, it indicates that Wednesdays are the peak day for revenue. My forecast predicts that revenue will continue to increase from May to August 2020. 

Lastly, I found the total revenue generated for the last quarter with the data I forecasted. I found that the best case will result in about $2,116,000,000, The worst case will result in about $1,773,000,000, and the most likely case will result in about $1,945,000,000.

*Side Note* I don't know how my notebook would be displayed not in Google collab. Also in step 5, for doing the forecast, we were asked to predict revenue 90 days
into the future which didn't include September. Thus, my forecast for revenue for the last quarter includes data only from mid-May to mid-August (90 days we were asked to forecast). 
