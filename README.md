# Optimizing-the-Flipkart-warehouse-storage-using-Supervised-Classification-Models

### PROBLEM STATEMENT
These days e-commerce domain is a rapid and emerging domain. Similarly, there are lot many other competitors emerging with better strategies. To give a strong competition Flipkart comes up with the strategy of Flipkart advantage, which means it is a service provided by Flipkart for their sellers. The service is warehouse space, logistics, packaging. The major advantage here is that Flipkart can provide customers with faster delivery and quality assurance. This is given by the tag Flipkart Advantage. There are filters on the search page that will help customers to select from these products. Flipkart Assured enables customers to enjoy a higher standard of shopping and faster, hassle-free shipping. 
The problem here faced by Flipkart is the storage of the products sent by sellers. Not all the products in the warehouse sell better. Not every seller is a good seller. Not every product is a good product. So, an algorithm needs to be built that predict is the product is eligible for the Flipkart advantage tag or not so that the product can be stored in the warehouse. Analyzing the dataset that contains the information like sales, pricing, brand and product specifications and predicting the products which fall under Flipkart Advantage Tag.

### PROJECT OUTCOME
The outcome of our project is to build a robust machine learning algorithm that helps the business client incorrectly classifying a given product as Flipkart Advantage or not, that computes an array of data inputs including sales, pricing, brand value, product specifications etc.

This is a pre-crawled dataset, taken as subset of a bigger dataset (more than 5.8 million products) that was created by extracting data from Flipkart.com, a leading Indian eCommerce store. The dataset has 20000 rows with 15 features. Refer to the below-detailed structure of the dataset.

### Variables Description
product URL -- The data consists of the web address to the Products

Unique ID -- A unique ID will be given by the website

ProductName -- The data consists of Names of the Products

crawl timestamp -- The time of the crawl

Pid -- roduct ID

Product category tree -- The data will show the category of which the Product belongs to

retail price -- The data shows the Retail Prices of the Products

discounted price -- The data shows the Discounted Prices of the Products

image -- The data shows the images of the Products

isFKAdvantage_product -- The data helps to represent whether the product is an advantage to Flipkart

description -- The data describes the product details

product rating -- The data talks about the rating of the product

overall rating -- The data talks about the overall rating of the product

brand -- The data represents the Brand to which the Product belongs to

product specifications -- The data represents the product specifications

### PRE-PROCESSING DATA ANALYSIS

#### Missing/Null Values:
Impute or drop features with missing values based on the percentage of missing values and relevance for model building.
In the dataset retail price, discounted price, description features have null values less than 10%. So, we have dropped the rows. The null values of brand features are imputed by product name. Since the brand feature has null values of around 30%.
The product rating and overall rating features have null values of more than 90%. So, we have dropped both features.

### BUSINESS JUSTIFICATION:
•	The main motive is to improve the performance of the model. As per the business scenario, the model is predicting the product is an advantage but in reality, it is not an advantage. In this scenario, the customer is betrayed and will lose the customer. This is a type 2 error.
•	In the second scenario if the model is predicted the product is not an advantage but in reality, the product is an advantage. In this scenario, a customer might not choose the product which is also a loss to the company. This is a type 1 error.
•	However, both the errors are costly but type 2 error is costlier than type 1. Here we need to reduce the false positives as minimum as possible. So, we choose precision as a performance metric.
•	From the above model comparison table, the Random Forest model has good precision compared to other models. So, we are considering the Random Forest as a base model. 

#### Inference:

By the best parameters from the grid search method, we have got the above scores. However, the FP increased to 409 from 47 which is not acceptable as per the business problem. The model didn’t perform well by considering the hyperparameters obtain from the Grid Search method. Hence boosting algorithms are considered to improve the performance of the model.

### Conclusion:

Hyper tuning the parameters of the Random Forest model, the model has not given better results compared to the base model. Since the main requirement is to maximize the precision so consider the random forest base model as final model.
The Random Forest model provides better results (precision=0.74) with an accuracy of 0.97 as per our business scenario.




