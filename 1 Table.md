# 1. Table
### 1. Replace 0, Ceil, Avg
- Tabel: employee
- Case : Samantha melakukan perhitungan rata-rata monthly salaries, tetapi ternyata keyboard tombol 0 nya rusak. Dia ingin melihat kesalahan perhitungannya dengan cara menghilangkan 0 dari angka-angkanya dan menghitung **(actual - miscalculated) average salary**. Hasilnya merupakan pembulatan ke atas.
```sql
SELECT ceil(avg(salary)- avg(replace(salary, '0', '')))
FROM employee;
```
---
### 2. 
- Tabel : employee
- Case  : Earnings = Monthly salary x Months. Output query adalah Earnings tertinggi dan jumlah orang yang mendapatkan Earnings tertinggi tersebut. Output dipisahkan dengan 2 spasi, contohnya "69952 1".

![image](https://user-images.githubusercontent.com/49611937/119297890-117d5c80-bc86-11eb-9e86-21c8df78c51d.png)

