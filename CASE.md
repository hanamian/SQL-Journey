# CASE

### 1. Triangle
Query untuk TRIANGLES table dengan 3 panjang sisinya A, B, dan C. Query harus menghasilkan output sesuai dengan kondisi berikut:
- Equilateral: segitiga dengan 3 sisinya sama panjang
- Isosceles: segitiga dengan 2 sisinya sama panjang
- Scalene: segitiga yang semua panjang sisinya berbeda
- Not A Triangle: sisi A, B, C tidak membentuk segitiga

```sql
SELECT CASE WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
            WHEN A = B AND B = C THEN 'Equilateral'
            WHEN A = B OR A = C OR B = C THEN 'Isosceles'
            ELSE 'Scalene'
        END
FROM TRIANGLES
```
---
### 2. 
