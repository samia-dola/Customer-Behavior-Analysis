# Customer-Behavior-Analysis_MSSQL-Server
[Danny's Diner](https://8weeksqlchallenge.com/case-study-1/) is a case study project. It focuses on examining patterns, trends, and factors influencing customer spending in order to gain insights into their preferences, purchasing habits, and potential areas for improvement in menu offerings or marketing strategies in a dining establishment.

# Customer Insights for Danny’s Diner
## Table of Contents
- [Introduction](Introduction)
- [Problem Statement](Problem-Statement)
- [Datasets](Datasets)
- [Entity Relationship Diagram](Entity-Relationship-Diagram)
- [SQL Tool](SQL-Tool)
- [Applied SQL Functions](Applied-SQL-Functions)
- [Case Study Analysis](Case-Study-Analysis)
  - [Database and Tables Creation](Database-and-Tables-Creation)
  - [Case Study Questions](Case-Study-Questions)
  - [Extra Queries](Extra-Queries)
- [Case Study Insights](Case-Study-Insights)
- [Conclusion](Conclusion)

## 1. Introduction
In the bustling city, amidst the aroma of delectable Japanese cuisine, there lies a charming little restaurant known as Danny’s Diner. It is the brainchild of Danny, a passionate lover of Japanese food. He took a leap of faith and opened his doors to sushi, curry and ramen enthusiasts in early 2021. With a dream in his heart and an appetite for success, Danny’s Diner began its journey.

But like any aspiring entrepreneur, Danny soon realized that running a restaurant involves more than just serving mouthwatering dishes. It requires a deep understanding of customers, their preferences and their patterns of behavior. This realization led him to embark on a new venture – harnessing the power of data to elevate his customer’s dining experience.

## 2. Problem Statement
Danny is eager to leverage the data collected during the first few months of operation to unravel key insights about his customers. He yearns to uncover their visiting patterns, discover how much they spend and identify their favourite menu items. Armed with this knowledge, Danny believes he can deliver a personalized experience that will keep his loyal customers coming back for more.

Additionally, Danny wishes to utilize these insights to make informed decisions about expanding his existing customer loyalty program. However, there’s a challenge. Danny and his team lack the expertise to generate basic datasets and analyze the data without relying on complex SQL queries.

## 3. Datasets
To aid in this case study, Danny has graciously provided three vital datasets:

- Sales – this dataset holds valuable information about the transactions that take place at Danny’s Diner, including the customer ID, menu items ordered and the order date.
- Menu – It encompasses all the delightful culinary creations offered at the restaurant including curry, ramen and sushi. It contains details such as item names, and their prices.
- Members – This dataset holds information about when customers joined the beta version of Danny’s loyalty program.

## 4. Entity Relationship Diagram

![Entity Relationship Diagram](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/c5e42f5a-f30b-420d-9465-db6d4875910d)

## 5. SQL Tool
[Microsoft SQL Server](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16)

## 6. Applied SQL Functions
- Window 
- CTEs
- Aggregate 
- JOINs
- Write scripts to generate basic reports that can be run every period

## 7. Case Study Analysis

### a. [Database and Tables Creation]( Database-and-Tables-Creation)
This section includes the "creation of database and tables" according to the information Danny has shared.

- #### Database Creation
  
![image](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/d32a5ae1-eb97-4624-afb8-6f4d8e16abf9)

- #### Sales Table
  
![image](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/8086c165-a7f7-49f4-ae2d-2e3cf226d0e6)

- #### Menu Table
  
![image](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/0d9b2e0b-65ea-41ca-8c5a-bbc819015ec6)

- #### Members Table
  
![image](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/51094731-2f21-466f-8c2f-41def68d58e5)


### b. Case Study Queries
1. What is the total amount each customer spent at the restaurant?
2. How many days has each customer visited the restaurant?
3. What was the first item from the menu purchased by each customer?
4. What is the most purchased item on the menu and how many times was it purchased by all customers?
5. Which item was the most popular for each customer?
6. Which item was purchased first by the customer after they became a member?
7. Which item was purchased just before the customer became a member?
8. What is the total items and amount spent for each member before they became a member?
9. If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?
10. In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi - how many points do customer A and B have at the end of January?

### c. Extra Queries 
Danny requires to create basic data tables that his team can use to quickly derive insights without needing to write SQL. 
I recreate the following tables output using the available data:

- #### Making A Comprehensive Customer Data Table
Here we need to create a view. A view is a virtual table. A view does not save the table data. It saves the query so that you do not need to rewrite it every time you need to retrieve data. You can view it like a normal table while in the background the saved query is called. An important advantage of the view is that when the source table(s) updates, the view also updates to show us the most recent changes.

- #### Ranking Member Customer Products:
Danny also requires further information about the ranking of customer products, but he purposely does not need the ranking for non-member purchases so he expects null ranking values for the records when customers are not yet part of the loyalty program.

We are going to use the CASE statement to create another column that will substitute [null] for ’N’ then rank the other rows that have ‘Y’.

## 8. Case Study Insights
- Customer B is the most frequent visitor with 6 visits in Jan 2021.
- Danny’s Diner’s most popular item is ramen, followed by curry and sushi.
- Customer A loves ramen, Customer C loves only ramen whereas Customer B seems to enjoy sushi, curry and ramen equally.
- The last item ordered by Customers A and B before they became members are sushi and curry. Does it mean both of these items are the deciding factor?

## 9.  Conclusion
Now we can say that dann
