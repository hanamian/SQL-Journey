# Basic
### 1. LIKE
```sql
select name 
from students
where name LIKE "%Joshua%";

select name
from students
where name LIKE "Joshua%";

select name 
from students
where name LIKE "%Joshua";
```
### 2. NOT and NOT LIKE
```sql
select name 
from students
where NOT name = "Joshua";

select name
from students
where NOT name LIKE "Joshua%";
```
### 3. IS NULL and IS NOT NULL
```sql
SELECT *
FROM purchases
where price is NULL;

SELECT *
FROM purchases
where price is NOT NULL;
```
### 4. AND and OR
```sql
SELECT *
FROM purchases
where price = 5000 and purchased_at='2018-10-01';

SELECT *
FROM purchases
where price = 5000 or price= 10000;
```
### 5. ASC and DESC
```sql
SELECT *
FROM purchases
ORDER BY price DESC;

SELECT *
FROM purchases
ORDER BY price ASC;
```
### 6. LIMIT
```sql
SELECT *
FROM purchases
ORDER BY price DESC;

SELECT *
FROM purchases
ORDER BY price ASC;
```
### 7. DISTINCT
```sql
SELECT DISTINCT(name)
FROM purchases;
```
### 8. GROUP BY, SUM, COUNT
```sql
SELECT count(*), sum(price), purchased_at, character_name
FROM purchases
GROUP BY purchased_at, character_name;
```
###
