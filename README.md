# Install Nginx PHP Composer MariaDB and Laravel

### First read docker-compose.yaml

Default directories **src** at the root of the project local and **/var/www/laravel/** service container directory. 

Edit the nginx configuration file **docker/nginx/nginx.conf**

Setting mysql environment **docker/mysql/env/mysql.env**

default (setup your params):

>MYSQL_DATABASE=example_name
>MYSQL_USER=example_user
>MYSQL_PASSWORD=password
>MYSQL_ROOT_PASSWORD=password


if you need to download dump.sql uncomment the line **64** in docker-compose.yaml

and upload dump file: **docker/mysql/dump/you_dump.sql**

*Don't forget waiting when you dump upload

Each service has its own file. Example PHP:

**docker/php/Dockerfile** - change version PHP, add extensions if you needed. 

### Build images:

`docker compose build` 

### Run container:

`docker compose up nginx -d` - **Nginx** has dependencies when run.

check images: `docker-compose ps`

If something wrong check logs: 

`docker compose logs` - show all service logs.

Or: 

`docker compose logs nginx` - logs only nginx service.

### Install laravel:

`docker compose run --rm composer create-project laravel/laravel .` 

### Use artisan laravel:

`docker compose run --rm artisan list` 

laravel will be installed in the **src** directory.

Bonus install: **redis**, **supervisor**, **cron**.





