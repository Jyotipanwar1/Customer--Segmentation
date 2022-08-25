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

# Goal
The goal of the first part of this project is to create segments of wholesale customers and then try to characterize those segments based on their content. For the clusters-segments to be created multiple clustering methods were used.

# data preparation
As customer clusters may vary by geography, I’ll restrict the data to only United Kingdom customers, which contains most of our customers historical data.
# RFM analysis
RFM Analysis
RFM (Recency, Frequency, Monetary) analysis is a customer segmentation technique that uses past purchase behavior to divide customers into groups.
RFM helps divide customers into various categories or clusters to identify customers who are more likely to respond to promotions and also for future personalization services.

RECENCY (R): Days since last purchase
FREQUENCY (F): Total number of purchases
MONETARY VALUE (M): Total money this customer spent.
We will create those 3 customer attributes for each customer.

Recency
To calculate recency, we need to choose a date point from which we evaluate how many days ago was the customer's last purchase.

# Meaningful Finding
* Special Group of 2009 Dec, have a high retention rate, keep remaining around 20 - 40 %
* Group of 2010 Dec, have a relatively low retention rate that keeping under 12 % afterward
Special period
* All groups have a significant increase in retention rate in Oct, Nov 2010, and Nov 2011, we believe it may be related to the Black Friday events.
Special trend
* A notable increase in the retention of the group after Jan 2011 can be observed from the cohort analysis.
 *  Scatterplots display various insights: 1.low recency has high frequency and few customers has low recency and high frequency 2.low recency has high monetary value and few customers has high recency and high monetary value. These one two are very seldom buyers but induce more wealth 3.Some with low frequeny and high monetary values.
* Skewness and Kurtosis shows that frequency and monetary value are columns with thick tails and high skewness due to extreme outliers.
** Customer segments with RFM Model**
Before moving to customer segments, Let's see the application of Pareto Principle – commonly referred to as the 80-20 rule on our dataset by applying it to our RFM variables.

Pareto’s rule says 80% of the results come from 20% of the causes.

Similarly, 20% customers contribute to 80% of your total revenue. Let's verify that because that will help us know which customers to focus on when marketing new products.

Applying 80-20 rule
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




