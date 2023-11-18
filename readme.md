# Laravel Framework development environment

[Documentation in Russian](https://github.com/avxman/docker/blob/master/readme-ru.md)

**Using Docker, we raise the server for development. We use the bunch:**
* Nginx
* Php-fpm
* MySql
* Redis

## Installation
1. We open the terminal and go to the root folder of the development environment
2. We launch the command: `docker compose up composer`. We wait for the container to stop
3. We launch the command: `docker compose up composer-update`. We wait for the container to stop

***Installation completed***

## Launch
1. We open the terminal and go to the root folder of the development environment
2. We launch the command: `docker composer up nginx`. We expect the launch of 4 containers
   (nginx, php, db, redis)

***The development environment has been launched***

## Stop
1. We open the terminal and go to the root folder of the development environment
2. We launch the command: `docker compose stop`. We expect a stop of all containers

***The development environment is stopped***

## Completion
1. We open the terminal and go to the root folder of the development environment
2. We launch the command: `docker compose down`. We expect to remove all containers

***The development environment is completed***

### Additional Information
* It issues an error related to access rights to folders and files.
* 1. You need to go to the neglected container php `docker exec -it server-php`
* 2. Launch the command:
```shell
chmod -R 777 /var/www/html/storage \
    && chmod -R 666 $(find /var/www/html/storage -type f) \
    && chmod -R 777 /var/www/html/bootstrap/cache \
    && chmod -R 666 $(find /var/www/html/bootstrap/cache -type f) \
    && chown -R www-data:www-data /var/www/html/storage \
    && chown -R www-data:www-data /var/www/html/bootstrap/cache
```
* 3. To leave the container indicating the key combination in the terminal: `ctrl+d`
     or console command: `logout`

### Links to the site:
1. https://localhost
2. http://localhost
