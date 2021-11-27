# Grocery List

This Repository is the main repository that contains 2 **git submodules** projects:

| Project                                                               | Description                                          | Build                                                                                                                                           |
| --------------------------------------------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| [**grocery-list-app**](https://github.com/joanpablo/grocery-list-app) | an [Angular](https://angular.io/) application        | ![GitHub Workflow Status (branch)](https://img.shields.io/github/workflow/status/joanpablo/grocery-list-app/grocery-list/master?style=flat)     |
| [**grocery-list-api**](https://github.com/joanpablo/grocery-list-api) | a [Spring Boot](https://spring.io/) Restful services | ![GitHub Workflow Status (branch)](https://img.shields.io/github/workflow/status/joanpablo/grocery-list-api/grocery-list-api/master?style=flat) |

Both projects are parts of the **Grocery List Application**: Frontend, and Backend.

## Steps to Run and Deploy locally

1. Clone the repository
2. Run docker-compose
3. Open the web browser

> As a requeriment you need to have installed [Docker](https://www.docker.com/products/docker-desktop) in your environment.

### 1. Clone repository

```shell
git clone https://github.com/joanpablo/grocery-list.git
```

Then enter the root folder:

```shell
cd grocery-list
```

### 2. Run **docker-compose**

You can run and deploy the project locally only with [Docker](https://www.docker.com/), nothing else is needed, not gradle, not nodejs, just Docker and _docker-compose_.

```shell script
docker-compose up
```

This command will deploy three docker containers:

- **grocery-list-app** (Nginx server hosting the Angular application listening at port **81**)
- **grocery-list-api** (A Java based container running the Spring Boot application listening at port **82**)
- **grocery-list-db** (The MySQL server listening at default port **3306**)

The file **_docker-compose.yml_** contains the configuration for deploy the containers.

The Angular app and the Spring Boot app are build and deploy within the containers using the multistage feature of Docker.
The docker files for each project are:

- Angular project in: **_/grocery-list-app/Dockerfile_**
- Spring Boot project in: **_/grocery-list-api/Dockerfile_**

### 3. Open the web browser

After running the command **docker-compose**, open a browser in the URL **_http://localhost:81_** to access the Grocery List Web Application.
