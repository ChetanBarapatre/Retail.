# Retail.

<img align="right" alt="coding" width="400" src="https://191-dev.s3.ap-southeast-1.amazonaws.com/wp-content/uploads/2021/02/22172404/SPF-Scam-CheckingOut.gif">


It is a critical requirement for business to understand the value derived from a customer. RFM is a method used for analyzing customer value.
Customer segmentation is the practice of segregating the customer base into groups of individuals based on some common characteristics such as age, gender, interests, and spending habits
Perform customer segmentation using RFM analysis. The resulting segments can be ordered from most valuable (highest recency, frequency, and value) to least valuable (lowest recency, frequency, and value).

Dashboard Link:https://public.tableau.com/app/profile/chetan.d.barapatre/viz/capstonepro3-d/Dashboard1


# Insight From Project

## understanding data 

This is a transnational data set which contains all the transactions that occurred between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique and all-occasion gifts.


I have about 8 columns in the dataset that is:

1) InvoiceNo  : Invoice number. Nominal, a six digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation

2) StockCode  : Product (item) code. Nominal, a five digit integral number uniquely assigned to each distinct product

3) Description	Product (item) name. Nominal

4) Quantity : The quantities of each product (item) per transaction. Numeric

5) InvoiceDate : Invoice Date and time. Numeric, the day and time when each transaction was generated

6) UnitPrice : Unit price. Numeric, product price per unit in sterling

7) CustomerID : Customer number. Nominal, a six digit integral number uniquely assigned to each customer

8) Country : Country name. Nominal, the name of the country where each customer resides

# Data Preprocessing

1)	In a dataset about 8 columns and 379336 rows in a training dataset and about 8 columns and 162573 rows in a testing dataset
	
2)	Approx 25% null values are available in the description column but we can’t replace that values with mean, median and mode because customerID is uniquely identified, so basically have to drop nan values rows
	
3)	2626 duplicated values are available in the training dataset and 468 in the testing datasets, so I drop that duplicate values.

# EDA 
### Data Transformation:


