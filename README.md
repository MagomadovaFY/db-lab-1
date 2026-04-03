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

```
### Задание 2. SELECT (основной сервер)

**Условие:**
Продажи (sales) НЕ через канал 'dealership' (т.е. 'internet' и др.).

**SQL-запрос:**
```sql
SELECT *
FROM sales
WHERE channel != 'dealership';
