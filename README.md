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

## Установка Laravel из репозитория 

Откройте консоль домашней директории сайтов.
Выполните клонирование репозитория в домашнюю директорию и установите все зависимости.

```bash
git clone https://github.com/DuNai2/learn-larvel-13
composer install
```

Скоприруем файл .env из файла .env.example
```bash
copy .env.example .env
```

Сгенерируем ключ шифрования
```bash
php artisan key:generate
```

Выполните миграцию 
```bash
php artisan migrate --seed
```

##Настройка подключения к БД

Настройте параметры подключения к ЬД (файл **.env**)

```php
DB_CONNECTION=mysql
DB_HOST=127.0.0.1 #MySQL-8.4
DB_PORT=3306
DB_DATABASE=learn-laravel-13
DB_USERNAME=root
DB_PASSWORD=

SESSION_DRIVER=file
```
