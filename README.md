# Customer-Behavior-Analysis
[Danny's Diner](https://8weeksqlchallenge.com/case-study-1/) is a case study project. It focuses on examining patterns, trends, and factors influencing customer spending in order to gain insights into their preferences, purchasing habits, and potential areas for improvement in menu offerings or marketing strategies in a dining establishment.

# Customer Insights for Danny’s Diner
## Table of Contents
- [Introduction](https://github.com/samia-dola/Customer-Behavior-Analysis#1-introduction)
- [Problem Statement](https://github.com/samia-dola/Customer-Behavior-Analysis#2-problem-statement)
- [Datasets](https://github.com/samia-dola/Customer-Behavior-Analysis#3-datasets)
- [Entity Relationship Diagram](https://github.com/samia-dola/Customer-Behavior-Analysis#4-entity-relationship-diagram)
- [SQL Tool](https://github.com/samia-dola/Customer-Behavior-Analysis#5-sql-tool)
- [Applied SQL Functions](https://github.com/samia-dola/Customer-Behavior-Analysis#7-case-study-analysis)
- [Case Study Analysis](https://github.com/samia-dola/Customer-Behavior-Analysis#7-case-study-analysis)
  - [Database and Tables Creation](https://github.com/samia-dola/Customer-Behavior-Analysis#a-database-and-tables-creation)
  - [Case Study Questions](https://github.com/samia-dola/Customer-Behavior-Analysis#b-case-study-queries)
  - [Bonus Queries from Danny](https://github.com/samia-dola/Customer-Behavior-Analysis#c-bonus-queries-from-danny)
- [Insights from Case Study](https://github.com/samia-dola/Customer-Behavior-Analysis#8-insights-from-case-study)
- [Conclusion](https://github.com/samia-dola/Customer-Behavior-Analysis#9--conclusion)

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

![Entity Relationship Diagram](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/b8c3d2fc-d4c5-443d-8c32-c54d7342bd78)

## 5. SQL Tool
[Microsoft SQL Server](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16)

## 6. Applied SQL Functions
- Window 
- CTEs
- Aggregate 
- JOINs
- Write scripts to generate basic reports that can be run every period

## 7. Case Study Analysis

### a. [Database and Tables Creation]( https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/blob/main/Database%20%26%20Table%20Query.sql)
This section includes the "creation of database and tables" according to the information Danny has shared.

- #### Database
![Database](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/553d5c90-b58a-4a3e-b927-2bf834822ffd)

- #### Sales Table
  
![Sales Table](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/86f70669-fbe1-4c69-be31-f162dd478782)

- #### Menu Table
![menu table](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/b7ae1544-9e3e-4702-86c6-bca518b53339)

- #### Members Table
![Sales Table](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/assets/150064729/0d0a5e07-002d-46d6-b070-9b98c29c8038)

### b. [Case Study Queries](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/blob/main/Case%20Study%20Queries.sql)
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

### c. [Bonus Queries from Danny](https://github.com/samia-dola/Customer-Behavior-Analysis_MSSQL-Server/blob/main/Bonus%20Queries%20from%20Danny.sql)
Danny requires to create basic data tables that his team can use to quickly derive insights without needing to write SQL. 
I recreate the following tables output using the available data:

- #### Recreate a Comprehensive Customer Data Table:
Here we need to create a view. A view is a virtual table. A view does not save the table data. It saves the query so that you do not need to rewrite it every time you need to retrieve data. You can view it like a normal table while in the background the saved query is called. An important advantage of the view is that when the source table(s) updates, the view also updates to show us the most recent changes.

- #### Rank the products of member customers:
Danny also requires further information about the ranking of customer products, but he purposely does not need the ranking for non-member purchases so he expects null ranking values for the records when customers are not yet part of the loyalty program.

We are going to use the CASE statement to create another column that will substitute [null] for ’N’ then rank the other rows that have ‘Y’.

## 8. Insights from Case Study 
From the analysis, I discovered the following interesting insights that would be certainly useful for Danny:
- Customer B is the most frequent visitor with 6 visits in Jan 2021.
- Danny’s Diner’s most popular item is ramen, followed by curry and sushi.
- Customer A and C loves ramen whereas Customer B seems to enjoy sushi, curry and ramen equally.
- Customer A is the 1st member of Danny’s Diner and his first order is curry.
- The last item ordered by Customers A and B before they became members are sushi and curry. Does it mean both of these items are the deciding factor?
- Before they became members, Customer A and Customer B spent $25 and $40 respectively.
- Throughout Jan 2021, their points for Customer A: 860, Customer B: 940 and Customer C: 360.
- Assuming that members can earn 2x points a week from the day they became a member — not just sushi, Customer A has 1370 points and Customer B has 940 points by the end of Jan 2021.

## 9.  Conclusion
Now it can be said that Danny will be able to make the right decision for his business according to the outcomes from the case study.
