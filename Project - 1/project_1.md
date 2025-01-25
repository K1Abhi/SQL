# Project: Credit Card Transaction Analysis

The goal of this project is to analyze credit card transaction data to uncover key insights such as top spending cities, card-type trends, spending behavior across different timeframes, and gender-based contributions. By leveraging SQL queries, we will derive actionable insights that can help financial institutions understand customer spending patterns.

## Dataset Overview:
The project uses a dataset named CREDIT_CARD_TRANSCATIONS with the following columns:

```TEXT
INDEX (INTEGER):     Unique identifier for each transaction.
CITY (VARCHAR):      The city where the transaction took place.
DATE (TIMESTAMP):    The date and time of the transaction.
CARD_TYPE (VARCHAR): The type of credit card used (e.g., Gold, Silver, Platinum, etc.).
EXP_TYPE (VARCHAR):  The expense category (e.g., Fuel, Shopping, Dining, etc.).
GENDER (VARCHAR):    The gender of the cardholder.
AMOUNT (INTEGER):    The transaction amount.
```
![alt text](https://github.com/K1Abhi/SQL/blob/main/images/Table_1.png)


## Tools & Technologies:
- SQL for data querying and analysis.
- Snowflake ❄️ as the database.
- Visualization in Tableau .


## Deliverables:

### Top 5 Cities with Highest Credit Card Spends and Their Contribution

A credit card company wants to identify the top 5 cities where customers spend the most and how much they contribute to total revenue.
This analysis helps the company:
1. Focus marketing efforts on high-spending cities.
2. Allocate resources effectively.
3. Offer personalized promotions based on spending patterns.

```sql
select city, sum(amount), 
         ( sum(amount)/(select sum(amount) from credit_card_transcations ) )* 100 as percentage_contribution
from credit_card_transcations
group by city
order by 2 DESC
limit 5
;
```
<details>
  <summary>View the Table</summary>

| CITY               | SUM(AMOUNT) | PERCENTAGE_CONTRIBUTION |
|--------------------|-------------|-------------------------|
| Greater Mumbai, India | 576751476   | 14.154000                |
| Bengaluru, India      | 572326739   | 14.045400                |
| Ahmedabad, India      | 567794310   | 13.934200                |
| Delhi, India          | 556929212   | 13.667500                |
| Kolkata, India        | 115466943   | 2.833700                 |

</details>



## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
