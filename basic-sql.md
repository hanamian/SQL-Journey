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
### 9. WHERE HAVING
```sql
SELECT price, character_name
FROM purchases
WHERE price > 5000
GROUP BY purchased_at;

SELECT price, character_name
FROM purchases
GROUP BY purchased_at
HAVING price > 5000;
```
### 10. SELECT IN SELECT (SUBQUERY)
```sql
SELECT name
FROM players
WHERE goals > ( SELECT goals
                FROM players
                WHERE name= "Hana");

SELECT name,goals
FROM players
WHERE goals > (SELECT avg(goals) 
               FROM players);
```
### 11. AS
```sql
SELECT name as '180 cm atau lebih'
FROM players
where height >= 190;
```
### 12. JOIN, LEFT JOIN
```sql
SELECT *
FROM students
JOIN school
ON students.students_id = school.id;

SELECT players.name as 'nama pemain', teams.name as 'tim (tahun lalu)'
FROM players
LEFT JOIN teams
ON players.previous_team_id=teams.id;

```
### 13. JOIN 3 TABLES
```sql
SELECT *
FROM players
JOIN countries
ON players.country_id = countries.id
LEFT JOIN teams
ON players.previous_team_id=teams.id;
```
### 14. 
```sql
select name, price-cost, avg(price-cost)
from items
order by price-cost desc
limit 5;

select name, price-cost
from items
where price <= 70 and price-cost > (select price-cost 
                                    from items 
                                    where name = 'hoodie abu-abu');
```
### 15. 
```sql
select users.id, users.name, count(*) as 'jumlah'
from users
join sales_records
on users.id= sales_records.user_id
group by users.id
having count(*) >= 10
order by users.id asc;
```
```sql
select users.id, users.name
from users
join sales_records
on users.id=sales_records.user_id
join items
on sales_records.item_id=items.id
where items.name ='sandal'
group by users.name
order by users.id asc;
```
```sql
select purchased_at, sum(price) as 'total penjualan'
from sales_records
join items
on sales_records.item_id = items.id
group by purchased_at 
order by purchased_at asc;
```
```sql
select items.id, items.name, sum(price)
from items
join sales_records
on items.id=sales_records.item_id
group by items.id
having sum(price) > (select sum(price) 
                     from items 
                     join sales_records 
                     on items.id=sales_records.item_id 
                     where items.name='hoodie abu-abu' )
order by items.id asc;
```
### 16. INSERT INTO
Menambah data ke tables
```sql
INSERT INTO students(name, course)
VALUES('Hana', 'Go')
```
### 17. UPDATE
```sql
UPDATE students
SET name='Jordan', course='SQL'
WHERE id=6
```
### 18. DELETE
```sql
DELETE from students
WHERE id=9;
```

