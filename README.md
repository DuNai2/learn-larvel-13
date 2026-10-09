## Установка Laravel(пустой проект)

Обновление пакетного менеджера Composer до последней стабильной версии.

```bash
composer self-update
```
Скачивание и установка чистого каркаса Laravel в текущую директорию

```bash
composer create-project laravel/laravel .
```

Настройка приложения для работы в качестве API, установка Laravel Sanctum для аунтефикации 

```bash
php artisan install:api 
```

Публикация файла конфигурации для настройки CORS (разрешение cross-origin запросов к вашему API с других доменов/ либо фронтенда)

```bash
php artisan config:publish cors 
```
Создание символической ссылки из публичной папки  **public/storage** в закрытую папку **storage/app/public**
это необходимо, чтобы загруженные файлы были доступны по прямой ссылке из браузера. 
```bash
php artisan storage:link 
```

Создание файла **htaccess** в корне проекта, чтобы перенаправить все запросы в папку **public**
```php
//Включает модуль mod_rewrite  в веб-сервере Apache 
RewriteEngine on
//Правило, которое берёт абсолютно любой запрошенный URL и незаметно для пользователя перенаправляет его в папку public/
RewriteRule ^(.*)$ public/$1 [L]
```
