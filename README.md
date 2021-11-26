# Grocery List

This Repository is the main repository that contains 2 **git submodules** projects:

- **grocery-list-app**: an [Angular](https://angular.io/) application
- **grocery-list-api**: a [Spring Boot](https://spring.io/) Restful services

Both projects comforms the **Grocery List Application**: Frontend, and Backend.

## Build & Deploy with Docker

You can run and deploy the project locally only with [Docker](https://www.docker.com/), nothing else is needed, not gradle, not nodejs, just Docker and _docker-compose_.

### Clone repository

First clone the repository:

```shell
git clone https://github.com/joanpablo/grocery-list.git
```

Then enter the root folder:

```shell
cd grocery-list
```

### Execute Docker Compose

And execute the following command:

```shell script
docker-compose up
```

> As a requeriment you need to have installed [Docker](https://www.docker.com/products/docker-desktop) in your environment.

This command will deploy three docker containers:

- **grocery-list-app** (Nginx server hosting the Angular application listening at port **81**)
- **grocery-list-api** (A Java based container running the Spring Boot application listening at port **82**)
- **grocery-list-db** (The MySQL server listening at default port **3306**)

The file **_docker-compose.yml_** contains the configuration for deploy the containers.

The Angular app and the Spring Boot app are build and deploy within the containers using the multistage feature of Docker.
The docker files for each project are:

- Angular project in: **_/grocery-list-app/Dockerfile_**
- Spring Boot project in: **_/grocery-list-api/Dockerfile_**

## Open Web Browser

After running the command **docker-compose**, open a browser in the URL **_http://localhost:81_** to access the Grocery List Web Application.
