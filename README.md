---
# Домашнє завдання до Теми 3. Завантаження даних та основи SQL. DQL команди 
---
## 1. Напишіть SQL команду, за допомогою якої можна:
 - вибрати всі стовпчики (За допомогою wildcard “*”) з таблиці products;
 - вибрати тільки стовпчики name, phone з таблиці shippers
~~~~sql
USE db_hw;

SELECT * FROM products;
SELECT name, phone FROM shippers;
~~~~

## 2. Напишіть SQL команду, за допомогою якої можна знайти середнє, максимальне та мінімальне значення стовпчика price таблички products, та перевірте правильність її виконання в MySQL Workbench.
```
SELECT AVG(price) avg_price, MAX(price) max_price, MIN(price) min_price FROM products;
```

## 3. Напишіть SQL команду, за допомогою якої можна обрати унікальні значення колонок category_id та price таблиці products.
- Оберіть порядок виведення на екран за спаданням значення price та виберіть тільки 10 рядків. Перевірте правильність виконання команди в MySQL Workbench.
```
SELECT DISTINCT category_id, price FROM products ORDER BY price DESC LIMIT 10;
```

## 4. Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків), які знаходиться в цінових межах від 20 до 100, та перевірте правильність її виконання в MySQL Workbench.
```
SELECT * FROM products WHERE price >= 20 AND price <= 100;
SELECT * FROM products WHERE price BETWEEN 20 AND 100;
```


## 5. Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків) та середню ціну (price) у кожного постачальника (supplier_id), та перевірте правильність її виконання в MySQL Workbench.
```
SELECT supplier_id, COUNT(*) quantity_products, AVG(price) avg_price FROM products GROUP BY supplier_id;
```
