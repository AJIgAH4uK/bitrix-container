# Инструкция по установке окружения

## Начало работы

- Файл .env.example скопировать рядом и переименовать в .env это переменные окружения. Для обычной 
локальной установки там можно ничего не менять

- В консоли для запуска контейнеров вводим:
```
docker compose -f "docker-compose.yml" up -d --build
```

## Решение проблем с установкой Bitrix

#### Uncaught mysqli_sql_exception: Unknown database
- В restore.php на строке 1735 в начале функции Connect() добавить строку: mysqli_report(MYSQLI_REPORT_OFF);
- Причина: https://blog.softdev.online/index.php?controller=post&action=view&id_post=28

#### IP адрес клиента изменился, продолжение невозможно
- В restore.php установить
```php
define('IP_LIMIT', '#IP_LIMIT_PLACEHOLDER#');
define('INIT_TIMESTAMP', '#INIT_TIMESTAMP#');
```
