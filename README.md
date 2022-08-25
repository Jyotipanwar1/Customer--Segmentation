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
 
* **Customer segments with RFM Model..** 
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

* In our case, the 80% of total revenue is not achieved by the 20% of TOP customers but approximately, it does, because they are less than our 20% TOP customers who achieve it. It would be interesting to study this group of customers because they are those who make our most revenue.

Applying RFM score formula
The simplest way to create customers segments from RFM Model is to use Quartiles. We assign a score from 1 to 4 to Recency, Frequency and Monetary. Four is the best/highest value, and one is the lowest/worst value. A final RFM score is calculated simply by combining individual RFM score numbers.

Note: Quintiles (score from 1-5) offer better granularity, in case the business needs that but it will be more challenging to create segments since we will have 555 possible combinations. So, we will use quartiles.
* Best Recency score = 4: most recently purchase. Best Frequency score = 4: most quantity purchase. Best Monetary score = 4: spent the most.

* Now that we knew our customers segments we can choose how to target or deal with each segment.

For example: Best Customers - Champions: Reward them. They can be early adopters to new products. Suggest them "Refer a friend".
At Risk: Send them personalized emails to encourage them to shop.
More ideas about what actions to perform in Ometria.
* Conclusion - perspective from this level of customer segmentation
To gain even further insight into customer behavior, we can dig deeper in the relationship between RFM variables.

* RFM model can be used in conjunction with certain predictive models like k-means clustering, Logistic Regression and Recommendation to produce better informative results on customer behavior.

* We will go for k-means since it has been widely used for Market Segmentation and it offers the advantage of being simple to implement, following Andrew Ng who advice in his Machine Learning course, start with a dirty and simple model then move to more complex models because simple implementation helps having a first glance at the data and know where/how to exploit it better.
# Data visualization
Country-wise analysis to demonstrate average spend. Used a bar chart to show the monthly figures.
Made a Bar graph of top 15 products which were mostly ordered by the users to show the number of products sold
Made a Bar graph to show the count of orders vs. hours throughout the day
Plotted the distribution of RFM values using histogram
Visualized to compare the RFM score of the clusters using heatmap
* On one hand, we have a negative correlation between:

Recency and Frequency
Recency and Monetary
On the other hand, the correlation between Monetary and Frequency is positive comparing to negative ones but still not that strong.

## K-means Implementation
A common challenge with k-means is that you must tell it how many clusters you expect. Figuring out how many clusters we need is not obvious from data, thus we will try different clusters numbers and check their silhouette coefficient. The silhouette coefficient for a data point measures how similar it is to its assigned cluster from -1 (dissimilar) to 1 (similar). The elbow method can be used to determine the number of clusters as well.

Note: K-means is sensitive to initializations because those initializations are critical to quality of optima found. Thus, we will use smart initialization called k-means++.
## Conclusion - Perspective after applying k-means clustering:

Unfortunately, we didn't obtain a clearly separated clusters. Clusters assignments are muddled. (It may be due to outliers who weren't removed).

Limitations of k-means clustering:

There is no assurance that it will lead to the global best solution.
Can't deal with different shapes(not circular) and consider one point's probability of belonging to more than one cluster.
These disadvantages of k-means mean that for many datasets (especially low-dimensional datasets) it may not perform as well as you might hope. Here comes Guassian Mixture Model (GMM) in help by providing greater flexibility due to clusters having unconstrained covariances and allowing probabilistic cluster assignment.

Reference Python Data Science Handbook by Jake VanderPlas.

Note- Further Explanation: A common practice before doing clustering: Principal Component Analysis (PCA). PCA calculates the dimensions which best maximize variance.It gives directions on how many components to consider for GMM. Basically, it does dimensionality reduction while keeping the most important features, characteristics (combinations of features best describe customers). But as we are not dealing with high dimension we won't do it for this case.

Conclusion - Perspectives
At this juncture, it makes sense to show interested stakeholders the cluster solutions and get their input. The decision should be based upon how the business plans to use the results, and the level of granularity they want to see in the clusters. What range of customer behavior from high-to-low value customers are the business stakeholders interested in exploring? And from the answer to that question various methods of clustering can be further exploited whether applied on RFM variables or directly on the transaction dataset available.



