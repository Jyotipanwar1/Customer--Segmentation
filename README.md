# Customer--Segmentation
CLuster our customers

# Problem Statement
In ecommerce companies like online retails, customer segmentation is necessary in order to understand customers behaviors. It leverages aqcuired customer data like the one we have in our case, transactions data in order to divide customers into groups.
Our goal in this Notebook is to cluster our customers to get insights in:
* Increasing revenue (Knowing customers who present most of our revenue)
* Increasing customer retention
* Discovering Trends and patterns
* Defining customers at risk
* We will do RFM Analysis as a first step and then combine RFM with predictive algorithms (k-means).
** RFM Analysis answers these questions:** 
* Who are our best customers?
* Who has the potential to be converted in more profitable customers?
* Which customers we must retain?
* Which group of customers is most likely to respond to our current campaign?

# RFM analysis
* RFM (Recency, Frequency, Monetary) analysis is a proven marketing model for behaviour based customer segmentation.
* It groups customers based on their transaction history in other terms– how recently (R), how often (F) and how much (M) did they buy.
* RFM helps divide customers into various categories or in better terms into clusters to identify customers who are more likely to respond to a promotion or not... so we try to predict the next purchases of the customers

This project focus on customer analysis and segmentation. Which help to generate specific marketing strategies targeting different groups. RFM Analysis, Cohort Analysis, and K-means Clusters were conducted on a UK-based online retail transaction dataset with 1,067,371 rows of records hosted on themMachine Learning Repository.


# Meaningful Finding
Special group
Group of 2009 Dec, have a high retention rate, keep remaining around 20 - 40 %
Group of 2010 Dec, have a relatively low retention rate that keeping under 12 % afterward
Special period
All groups have a significant increase in retention rate in Oct, Nov 2010, and Nov 2011, we believe it may be related to the Black Friday events.
Special trend
A notable increase in the retention of the group after Jan 2011 can be observed from the cohort analysis.


# Data Cleaning and preprocessing
* Checked for missing data.Filled the null CustomerID values with 10 frequent values and equally distributed them.
* Removed duplicate data records.
* Data Transformation
* Performed Cohort analysis. Analyzed active customers for each cohort.
* Analyzed Retention Rate of the customers.
# Data Modelling
* Data modelling(RFM analysis)
Built an RFM (Recency Frequency Monetary) model(Period:1 year)
Calculated RFM metrics. Added them(as strings) get an RFM segment. Also, added the individual scores in order to get an RFM score.
Analyzed the RFM segments and commented on the findings.
* Data modelling(KMeans)
Prepared the data for the algorithm. If the data was asymmetrically distributed, managed the skewness with log transformation. Scaled the data using StandardScaler.
Found the optimal number of clusters(elbow method). Performed clustering using Kmeans.
Analysed the clusters and commented on the findings.
# Data visualization
Country-wise analysis to demonstrate average spend. Used a bar chart to show the monthly figures.
Made a Bar graph of top 15 products which were mostly ordered by the users to show the number of products sold
Made a Bar graph to show the count of orders vs. hours throughout the day
Plotted the distribution of RFM values using histogram
Visualized to compare the RFM score of the clusters using heatmap




