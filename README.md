# 1251. Average Selling Price

### Problem Description : [ Average Selling Price](https://leetcode.com/problems/average-selling-price/description/?envType=study-plan-v2&envId=top-sql-50)

## Solution 
```sql
select p.product_id , ROUND(sum(p.Price*u.units)*1.0/sum(units),2)  average_price
from Prices p
  join unitsSold u 
on u.product_id=p.product_id 
where u.purchase_date >= p.start_date 
and u.purchase_date <=p.end_date
group by p.product_id

