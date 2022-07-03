# Dockerized Laravel Application

Dockerized your Laravel Application Easily with this premade docker-compose 

Supported platform
- am64
- arm64/v8

Services Includeed:
- Nginx
- PHP with nodejs
- MYSQL

## Setup Environment Variable

Copy the `.example.env`

```
cp .env.example .env
```

Edit .env file according to your needs

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
