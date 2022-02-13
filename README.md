# Time-Series
---

Unit 10: Forecasting Net Prophet - MercadoLibre

---
For this assignment, I was tasked with finding out if Google search traffic for MercadoLibre links to any financial events for MercadoLibre, which is the most popular e-commerce site in Latin America with over 200 million users. For this analysis I utilized Google collab and Facebook's Prophet, along with Python libraries such as pandas and hvplot for the visualizations.

---
## Step 1: Find Unusual Patterns in Hourly Google Search Traffic

For Step 1, I read in the 'google_hourly_search_trends.csv', which has data regarding Google search traffic for MercadoLibre for every hour. First, I looked at the Google search trends for the month of May, which is when MercadoLibre releases their quartertly financial results. When visualizing the data using hvplot, Google search traffic for MercadoLibre tends to oscilate everyday at similar times. From 8 a.m to around 1 a.m the search traffic gradually increases, then after 1 a.m the Google search traffic decreases until the morning. 
When comparing the Google search traffic for the month of May compared to all other months, it turns out there is around a 8.5% increase in Google search traffic for the month of May, confirming that when MercadoLibre releases their quartly financial results, that it increases Google search traffic for the company. 

---
## Step 2: Mine the Search Traffic Data for Seasonality

For step 2, I was tasked to mine the search traffic data to analyze any predictable seasonal patterns of interest in the company.
I first grouped the Google search traffic data to show the average search traffic for the days of the week. The hvplot I created indicates that search trends are at its highest on Monday, Tuesday, Wednesday, and Thursday then gradually fall througout the rest of the week. Specifically, Tuesday has the most search traffic out of any week day. 
I then created a heat map that visualizes how much search traffic there is for each day of the week for each hour of the day. This visually confirms what I've already analyzed. How search traffic gradually increases from 10 a.m to around 1-2 a.m after midnight. It also seems that there is more search traffic for the first half of the week (however it does seem pretty consitent througout the week). Specically, I would say search traffic is concentrated from 10 p.m to 2 a.m from Tuesday to Thursday.
Lastly, I graphed the average google search traffic trends for each week in the year. It seems search traffic increases alot from weeks 42 to 51, which is the holday season so it makes sense. Furthermore, it takes a sharp dip for the last week of the year, then shoots all the way back up for the first couple months in the new year.

---
## Step 3: Relate the Search Traffic to Stock Price Patterns

