# Dockerized Laravel Application

Dockerized your Laravel Application Easily with this premade docker-compose.

Author: [Rey Jhon](https://github.com/yourjhay)


Supported platform
- amd64
- arm64/v8

Services Includeed:
- Nginx
- PHP with nodejs
- MYSQL

## Requirements
- docker
- docker-compose
- a laravel project of course -_-

## Clone this repo

```
git clone https://github.com/yourjhay/dockerized-laravel.git
```

```
cd dockerized-laravel
```


## Next: Setup Environment Variable

Copy the `.example.env`

```
cp .env.example .env
```

Edit `.env` file according to your configuration need.

# Create and Run Container 

```
docker-compose up
```

## Run in Background

```
docker-compose up -d 
```

You can now visit your laravel app in your browser using your localhost or Host IP Address and `APP_PORT` in your .env

EG:
[http://127.0.0.1:8101](http://127.0.0.1:8101)

127.0.0.1 is the Localhost IP of the machine running docker.
#
#

# Running command in your application container

You must only run all commands related to your app like `php artisan` or `npm` on the application container.

You Container Names will be:
- *<you_app_name>***-app** - This is were you can run command like `php artisan`
- *<you_app_name>***-nginx** - You Can access your app in the browser here
- *<you_app_name>***-mysql** - Your app database

You can list containers using the following command:
```
docker container ls
```
It will show the list of containers in docker

You can  run command into container by attaching to container console without(< >):
```
docker exec -it <container-name> sh
```

For root:
```
docker exec -it <container-name> bash
```


# Laravel Environment (.env) Updates

Update your Laravel Project .env

`DB_HOST` this should be the service name of our mysql service in `docker-composer.yml` file. Or you might get connection refuse error when communicating with MYSQL server.
The service name is **database**

```
DB_HOST=database
DB_HOST=afms-db
DB_PORT=3306
DB_DATABASE=dbname
DB_USERNAME=dbuser
DB_PASSWORD=password
```

Note: Update the above environment variables in your laravel project relevant to your `.env` in dockerized-laravel.

## Redis
 Redis is Included. Just remove it in docker-compose.yml if you don't need it.
 
#
## PHP INI

php.ini is located at `./docker/php/php.ini`

#
PHP Dockerfiles from [sprintcube/docker-compose-lamp](https://github.com/sprintcube/docker-compose-lamp). Salamat ha! Kinopya ko lang naman yung variables lol.

# PHP versions
- 5.4
- 5.6
- 7.1
- 7.2 - tested tested on laravel 7.0
- 7.3
- 7.4 - tested tested on laravel 7.0
- 8.0 
- 8.1 - tested on laravel 9.11

## PILIPINAS LANG MALAKAS!
