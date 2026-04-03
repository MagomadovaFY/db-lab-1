# Лабораторная работа №1
## Вариант 11

### Задание 1. Базовый поиск (Salespeople) – выполнено на основном сервере

**Условие:**  
10 последних отправленных писем (emails). Сортировка: дата отправления.

**SQL-запрос:**
```sql
SELECT *
FROM emails
ORDER BY sent_date DESC
LIMIT 10;
https://github.com/MagomadovaFY/db-lab-1/blob/main/%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B8.png?raw=true

