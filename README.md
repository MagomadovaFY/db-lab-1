# Лабораторная работа №1

## Вариант 11

---

## Задание 1. SELECT (основной сервер)

**Условие:**  
10 последних отправленных писем (emails). Сортировка: дата отправления.

**SQL-запрос:**

```sql
SELECT *
FROM emails
ORDER BY sent_date DESC
LIMIT 10;
```markdown

```
**https://github.com/MagomadovaFY/db-lab-1/blob/04d67e3d4c2de44e987c93f00181410cd8f8fed3/%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B8.png**
```
```
### Задание 2. SELECT (основной сервер)

**Условие:**
Продажи (sales) НЕ через канал 'dealership' (т.е. 'internet' и др.).

**SQL-запрос:**
```sql
SELECT *
FROM sales
WHERE channel != 'dealership';
```
**https://github.com/MagomadovaFY/db-lab-1/blob/e841ab1f7ec95aec5ed54c83f6422c0b59c7d16d/%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B8.png**
```
```
### могло быть задание 3. (мак не дает доступ...)
**1. Создать таблицу ny_sales**
```sql
CREATE TABLE ny_sales AS
SELECT *
FROM sales
WHERE dealership_id = 15;
```
**2. Уменьшить сумму на 10%**
```sql
UPDATE ny_sales
SET sales_amount = sales_amount * 0.9;
```
**3. Удалить продажи 2010 года**
```sql
DELETE FROM ny_sales
WHERE EXTRACT(YEAR FROM sales_transaction_date) = 2010;
```
**4. Проверить результат**
```sql
SELECT * FROM ny_sales;
