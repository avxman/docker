# Среда разработки для фреймворка Laravel

[Documentation in English](https://github.com/avxman/docker/blob/master/readme.md)

**С помощью docker подымаем сервер для разработки. Используваем связку:**
* Nginx
* Php-fpm
* MySql
* Redis

## Установка
1. Открываем терминал и переходим в корневую папку среды разработки
2. Запускаем команду: `docker compose up composer`. Дожидаемся остановки контейнера
3. Запускаем команду: `docker compose up composer-update`. Дожидаемся остановки контейнера

***Установка завершена***

## Запуск
1. Открываем терминал и переходим в корневую папку среды разработки
2. Запускаем команду: `docker composer up nginx`. Ожидаем запуск 4-х контейнеров
   (nginx, php, db, redis)

***Среда разработки запущена***

## Остановка
1. Открываем терминал и переходим в корневую папку среды разработки
2. Запускаем команду: `docker compose stop`. Ожидаем остановку всех контейнеров

***Среда разработки остановлена***

## Завершение
1. Открываем терминал и переходим в корневую папку среды разработки
2. Запускаем команду: `docker compose down`. Ожидаем удаление всех контейнеров

***Среда разработки завершена***

### Дополнительная информация
* Выдает ошибку связана с правами доступов к папкам и файлам.
* 1. Нужно зайти в запущенный контейнер php `docker exec -it server-php`
* 2. Запустить команду:
```shell
chmod -R 777 /var/www/html/storage \
    && chmod -R 666 $(find /var/www/html/storage -type f) \
    && chmod -R 777 /var/www/html/bootstrap/cache \
    && chmod -R 666 $(find /var/www/html/bootstrap/cache -type f) \
    && chown -R www-data:www-data /var/www/html/storage \
    && chown -R www-data:www-data /var/www/html/bootstrap/cache
```
* 3. Выйти из контейнера указав комбинацию клавиш в терминале: `ctrl+d`
     или консольной командой: `logout`

### Ссылки на сайт:
1. https://localhost
2. http://localhost
