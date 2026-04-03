# Лабораторная работа №1


### Задание 1.1. Базовый поиск (Salespeople)

**Условие:**  
Вывести username первых 10 нанятых женщин-продавцов, отсортированных по дате найма от самой ранней к поздней. Аналогично для мужчин.

**SQL-запросы:**

```sql
-- Женщины
SELECT username
FROM salespeople
WHERE gender = 'Female'
ORDER BY hire_date ASC
LIMIT 10;

-- Мужчины
SELECT username
FROM salespeople
WHERE gender = 'Male'
ORDER BY hire_date ASC
LIMIT 10;
```
### Задание 1.2. Работа с клиентами (Customers) ###
**Условия:**

Все email клиентов из штата Флорида (FL), отсортированные по алфавиту.

Имена, фамилии и email клиентов из New York City, NY, отсортированные по фамилии, затем по имени.

Все клиенты с телефонами, отсортированные по дате добавления.

**SQL-запросы:**
```sql
-- Email из FL
SELECT email
FROM customers
WHERE state = 'FL'
ORDER BY email ASC;

-- Клиенты из NYC
SELECT first_name, last_name, email
FROM customers
WHERE city = 'New York City' AND state = 'NY'
ORDER BY last_name, first_name;

-- Клиенты с телефонами
SELECT *
FROM customers
WHERE phone IS NOT NULL
ORDER BY date_added;

```
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
### могло быть задание 3. (не получилось подключить бд к маку...)
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
