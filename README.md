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

1)	I did a month-wise analysis ie how much active customers in each month. To do a monthly analysis of active customers. I made a new column Invoice_month by extracting the year and month values from the InvoiceDate column.

2)	To understand the active customer I made a new column ie Type in that customer who is active are represented by ‘A’ and customers who cancelled transactions are denoted by ‘C’

3)	Plot count plot by grouping by Invoice month and customerID and InvoiceNo and graph we observed that the count of customer and invoice keeps on increasing in every month(From the graph, we easily depict monthly active customer)


![image](https://user-images.githubusercontent.com/117656346/217812260-fef6b622-1e6a-4165-9a92-fd8ee16dcb5d.png)

4)  Now I have to check how many customers keep on purchasing(Retention rate) for that I created a new column by the name CohortMonth and in that group by CustomerID and Invoice_month and transform it to minimum

df_train['CohortMonth']=df_train.groupby('CustomerID')['Invoice_month'].transform('min')
df_test['CohortMonth']=df_test.groupby('CustomerID')['Invoice_month'].transform('min')

With the help of these, I understand when the first invoice is generated for a particular customer fo eg

![image](https://user-images.githubusercontent.com/117656346/218047789-c76e2886-5257-4028-9b5a-2b1755099b21.png)

Customer 16126 become active on site from 2011-02


cohort index is created for each row. The cohort index is the month difference between invoice month and cohort month for each row. By doing the deduction, I am able to know the month lapse between that specific transaction and the first transaction that user made on the website. This helps to check the user retention

To understand graphically I plot pivot table to understand 

![image](https://user-images.githubusercontent.com/117656346/218056783-1cada95c-6edf-41c8-8402-5c7363b7f46e.png)


cohort_count.plot(figsize = (15,7))
plt.show()

![image](https://user-images.githubusercontent.com/117656346/218060516-8a5fb8b8-5142-4215-b64b-f1bf9263cb4a.png)




























