# An Analysis of Order Ratings, Reviews, Sales, and Customer Relationship on a Brazilian E-Commerce Website <br />
Authors: Adam Foley, Mann Purohit, Nhat Pham, Sarvagna Shukla <br />
Data source: Brazilian e-commerce public dataset by Olist: https://www.kaggle.com/olistbr/brazilian-ecommerce

<h2>I/ Abstract: </h2>
<h2>Problem Introduction: </h2>

- In the past few years, the growth of online marketplaces and digital marketing has generated a high volume of data on consumer behaviors and e-commerce products. Analyzing this data would provide enterprises with insights into better business decisions. Here, we work with data from Olist, a Brazilian department store platform that connects small merchants to customers1. With Brazil being the largest e-commerce market in Latin America2 , our analysis attempts to help Olist leverage their data resources to raise their service quality, optimize business strategies, and attract more customers.<br />

- The datasets are provided by Olist on Kaggle.com. It contains anonymized records of 100k orders made on the platform from 2016 to 2018. Data is divided into eight tables, each with specific aspect like orders, products, sellers, and customers. As seen from the database schema (Figure 1), each observation on the main orders data table represents one order, and using other datasets, we can connect those orders to gain additional information on order status, product attributes, price, freight, type of payments, location of sellers and buyers, reviews written by customers, and much more.<br />

![Brazilian_ECommerce_Analysis_Proposal](https://user-images.githubusercontent.com/87089936/143927648-f652469f-7ab8-462a-bc5f-f0cc5a034e94.jpg)

- The project aims to develop a comprehensive, multi-level analysis that includes:<br />
(1) Machine learning models to explore different features of an order that would impact review scores<br />
(2) Forecast of monthly sales volumes by product category<br />
(3) Customer segmentation analysis based on churn probability, and machine learning models to classify customers into categories based on their buying behavior<br />
(4) Sentiment analysis of product reviews (textual data) to discern customer’s preferences, likes and dislikes<br />

<h2>Proposed plan: </h2>

- Data processing: Due to the nature of the data with eight tables composed of over 600k rows; we cleaned and loaded each table into an Amazon Web Services MySQL instance (Figure 1) to ensure the data is consistent among all members of the group during the project. Some tables provided were not in our desired format or tidy and therefore required pre-processing to ensure the accuracy of data loaded into our database.<br />

- Data visualization and modeling: We will use pandas and NumPy to tidy and preprocess the data, and scikit-learn to train a logistic model to predict a “negative” or “positive” review score given a variety of engineered features such as delivery time, freight value, price. We will find the most important feature by plotting input feature weights on bar plot using matplotlib and seaborn. For the sentiment analysis, we will use Natural Language Toolkit (NLTK) to preprocess the text data and perform predictive analysis using logistic regression. We will create bar plots using seaborn to visualize the impact of each word on the review score. For the customer segmentation analysis, we will quantitatively rank customers based on their Recency, Frequency, Monetary (RFM) values, and use K-Means Clustering to segment customers based on their purchasing habits.<br />

<h2>II/ Results</h2>

★ Customer Satisfaction Analysis <br />
- Surveys report that 93% of consumers are influenced by online reviews when making purchase decisions. By leveraging its order review data, Olist can gain insights into its customers’ wants and needs, and therefore enhance its services and products to provide better customer experience and attract more merchants to the platform. Through EDA and machine learning models for classification, we are interested in identifying key features that affect a good or bad review score, using information on reviews, orders, customers, sellers, products, and payments.<br />

- Classification model: <br />
+ Logistic regression
+ Random forest

![olist 1](https://user-images.githubusercontent.com/87089936/198896785-6af09e51-adf5-475a-93ef-3b94f0a8efaa.PNG)
![olist 2](https://user-images.githubusercontent.com/87089936/198896791-a83c72fa-1f86-446f-87c2-ad93fb131c1d.PNG)



