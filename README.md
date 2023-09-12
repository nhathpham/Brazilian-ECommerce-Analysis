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

### 1. Customer Satisfaction Analysis <br />
- Surveys report that 93% of consumers are influenced by online reviews when making purchase decisions. By leveraging its order review data, Olist can gain insights into its customers’ wants and needs, and therefore enhance its services and products to provide better customer experience and attract more merchants to the platform. Through EDA and machine learning models for classification, we are interested in identifying key features that affect a good or bad review score, using information on reviews, orders, customers, sellers, products, and payments.<br />

- Classification model:
+ Logistic regression
+ Random forest
![olist 1](https://user-images.githubusercontent.com/87089936/198896785-6af09e51-adf5-475a-93ef-3b94f0a8efaa.PNG)
![olist 2](https://user-images.githubusercontent.com/87089936/198896791-a83c72fa-1f86-446f-87c2-ad93fb131c1d.PNG)

<br />
### 2. Sales Analysis <br /> An EDA on sales trend and seasonality

![olist 3](https://user-images.githubusercontent.com/87089936/198896905-735c574b-2747-4faf-a177-22a9f2ab035c.PNG)
![olist 4](https://user-images.githubusercontent.com/87089936/198896908-91b38e22-b3ec-41f2-a1d6-d912d722f12d.PNG)
![olist 5](https://user-images.githubusercontent.com/87089936/198896913-b2499208-207b-407a-8c9c-532e8eca66cc.PNG)

<br />
### 3. Customer Segmentation <br />
- We set out to cluster customers based on similarities in key features such as sales,  delivery times, and review scores. The goal is to use these clusters to provide a better customer experience through enhanced product suggestions and understand customer pain points
- Feature collection:
  - Orders: Order count, Days since last order, Product count, Sales
  - Delivery: Early and Late order count 
  - Payments: Average payment installments
  - Reviews: Review count and Average review score 
<br />

### 4. Review Sentiment Analysis <br />
- We have a corpus of text data, where each review text is a customer’s message for the purchased product. We then transformed the score from 1 to 5 to: 
  - Negative sentiment = Score of 3 and Below
  - Positive sentiment = Score of 4 and Above
- We then extract the most frequently occuring words within each category. The goal is to predict a review’s sentiment given the textual message using Machine Learning Models

![image](https://user-images.githubusercontent.com/87089936/198897223-eb507031-0bd9-4bc6-a7bc-12d796f2420a.png)

- Classification model accuracy:
  - Logistic regression: 86.98%
  - Random forest: 76.55%
  - Recurrent neural network: 88.9%
  <br />
