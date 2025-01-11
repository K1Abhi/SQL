# Case Study 1: Danny's Diner

## Solution

[View the complete code](https://github.com/YogeshOlla/8-Weeks-SQL-Challenge/blob/main/Case%20Study%201%20-%20Danny's%20Diner/SQL%20Code/Case%20Study%201%20-%20Danny's%20Diner.sql).

***

### 1. What is the total amount each customer spent at the restaurant?

````sql
Select S.customer_id, Sum(M.price) as Total_sales
From Menu m
Join Sales s
On m.product_id = s.product_id
Group by S.customer_id
````

#### Answer:
| Customer_id | Total_sales |
| ----------- | ----------- |
| A           | 76          |
| B           | 74          |
| C           | 36          |

- Customer A, B and C spent $76, $74 and $36 respectivly.

***