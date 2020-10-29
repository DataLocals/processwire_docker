# Docker + Processwire + phpMyAdmin

This image serves as a starting point for Processwire projects.

## Quick Start

Get an Processwire application running the fastes way.

```shell
$ git clone https://github.com/DataLocals/processwire_docker
$ cd processwire_docker
$ docker-compose up
```

## Run your existing application

If you want to run your exisisting project you need to pull and configure it before you start the docker container.

### 1. Pull the current repo

```shell
$ git clone https://github.com/DataLocals/processwire_docker
$ cd processwire_docker
$ git clone <url-of-your-project>
$ mv <name-of-your-projekt> html
```

> Or you could also just add the repo of your existing project into the `init.sh` git clone part instead of the pull from the Processwire repo.


### 2. Create the database with phpmyadmin

You can simply use phpmyadmin to import your existing database.
Visit `http://localhost:8080` to get to phpmyadmin.

> Username: root  
> Password: root  

### 3. Configure your application

Now you need to configure your application to use the databases that is running inside docker.

To do so you need to manipulate the credentials of your application normally located under `/html/site/config.php`.

```php
$config->dbHost = 'db';  
$config->dbName = 'name-of-your-database';  
$config->dbUser = 'root';  
$config->dbPass = 'root';  
$config->dbPort = '3306';  
$config->dbEngine = 'name-of-your-db-engine';  
```

### 4. Fire up docker

In the root folder of this application you now can start up docker.

```shell
$ docker-compose up
```

### 5. Access the application

The application now should be available via `http://localhost:80`
