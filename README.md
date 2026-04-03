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

https://github.com/MagomadovaFY/db-lab-1/blob/2b4ab518f57293eb6ef561dfc6523bcde3a1d4b6/10%20%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%BE%D0%B2.png
