# Retail-data: Cohort and RFM Analysis

**Introduction**

Any retail store nowadays generates a vast amount of data. Amongst that information is data related to the sales generated by the company. Depending on the amount of information available on the customer and the products sold, this data can range from very detailed to quite basic. Nonetheless, even with a couple of fields there are interesting analysis that can be generated.

In this case, we have information from a retail store that has been gathered from https://archive.ics.uci.edu/ml/datasets/Online+Retail# and contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. In this dataset, we have an invoice number which identifies each unique cell, as well as fields like the quantities of product sold, unit price, and country of customer. Additionally, we have a customer ID field available.

The objective of this analysis will be two-fold. First, we will generate a cohort analysis of the customers in order to identify net dollar retention and user retention. Although this type of analysis is more common for SAAS companies, it is still a good exercise for understanding how to build cohort models. Additionally, we will build a basic RFM segmentation, with the objective of segmenting customers based on their purchase recency, purchase frequency, and the monetary value of their purchase. In the section below, we will explain in more detail the concepts to be analyzed.

**Cohort Analysis and RFM Analysis**

*Cohort Analysis:* 

Cohort analysis is a technique used for analyzing the behavior of a certain group of customers over time. This group of customers will have a common, shared attributed which allows their grouping. Commonly, this attribute is the first purchase or first login date, however attributes like channel, country, etc. can be used to group the customers. The cohort analysis will allow us to see the progression in time of a certain metric for the different groups of customers, helping us spot which groups might be better, where common patterns may occur, and to spot one-off events 

This cohort analysis can be done from a user or from a net dollar view, and it can represent the retention compared to the first period or the total values (ex. Total customers in period n)

*RFM Analysis:* 

RFM analysis is a common methodology used in industries where purchases are not recurrent. Contrary to what happens for SAAS businesses, retail and commerce businesses do not receive a predictable, consistent periodical payment from their customers. Instead, purchases are one-off, and the purchase frequency can vary significantly between customers. RFM analysis proposes a split between customers based on 3 different attributes calculated from their orders: Frequency, Recency and Monetary value. The recency refers to how much time passed since a customers' last order, while monetary value refers to the total value received from the customer in the studied period. Frequency is related to the total number of orders in the period studied for a specific customer.

Based on these three properties, customers are then split into different segments, where each segment can be analyzed separately . For example, customers with high monetary value but who purchased a long time ago might be good candidates for a promotional message, while users with high frequency and recency but low monetary value could be targeted with cross-selling initiatives. 

In most applications of RFM, customers are split into four bins for each of the three "features", therefore, there are 64 different buckets where a customer could be placed in this RFM "3D" space. In general, the split between the four buckets for each of the features is based on percentiles.

**Understanding the Dataset**

The dataset has around 500000 rows, which represent transactions between 01/12/2010 and 09/12/2011. Nonetheless, around 100k transactions have a null CustomerId. Each row in the dataset represents a product sold. Therefore, there can be multiple lines for each unique purchase if the purchase is composed of multiple items 

Fields:

InvoiceNo: Invoice number which is unique to each transaction.

StockCode: Product code which is unique to each product.

Description: Name of the product.

Quantity: The quantity of items sold per product.

InvoiceDate: The date and time in which the transaction occurred.

UnitPrice: Unit price for each of the units sold.

CustomerID: Unique number assigned to each customer.

Country: Name of the country where the customer resides.

**Approach:**

An explanation regarding the process for creating both the cohort analysis and the RFM analysis is available in the file called "Approach", while the queries used in the different analysis are in the folder "Queries" inside the RFM and Cohort analysis folders.

**Sources**:

Missing:
combined rfm score, name of the categories
https://en.digital/blog/analizando-recurrencia-compra-ecommerce-fidelizacion-rfm/1603
https://medium.com/@designbynattapong/customer-analytics-and-cohort-analysis-2fbbbba79783
https://medium.com/@ulasturker/customer-life-time-value-calculations-with-python-cltv-with-crm-analytics-2-in-data-science-7d39ca9ad2de
https://medium.com/@rafiqairwandi/rfm-analysis-using-postgresql-2e5c1fe42d6
https://joaocorreia.io/blog/rfm-analysis-increase-sales-by-segmenting-your-customers.html
https://towardsdatascience.com/who-is-your-golden-goose-cohort-analysis-50c9de5dbd31
https://towardsdatascience.com/how-to-design-real-time-cohort-analysis-in-python-sql-tableau-1df527c19b7e
https://rittmananalytics.com/blog/2021/6/20/rfm-analysis-and-customer-segmentation-using-looker-dbt-and-google-bigquery
https://www.r-bloggers.com/2019/07/customer-segmentation-using-rfm-analysis/
https://iglooanalytics.com/blog/cohort-analysis-in-tableau.html

Sources:


https://www.sciencedirect.com/science/article/pii/S1877050910003868

https://medium.com/swlh/customer-segmentation-in-online-retail-cohort-analysis-eb352085e64b

http://www.silota.com/docs/recipes/sql-recency-frequency-monetary-rfm-customer-analysis.html
