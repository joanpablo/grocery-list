# grocery-list

This is a repository that combines Frontend and Backend implementations of the Grocery List App

### Build & Deploy with Docker

You can run and deploy the project locally only with Docker. Nothing else is needed, not gradle, not nodejs, just Docker and _docker-compose_.
In the root folder run the command:

```shell script
docker-compose up
```

This command will deploy three docker containers:

- **grocery-list-app** (Nginx server hosting the Angular application through port **81**)
- **grocery-list-api** (A Java based container running the Spring Boot application and listening through port **82**)
- **grocery-list-db** (The MySQL server)

The file **_docker-compose.yml_** contains the configuration for deploy the containers.

After run the command line docker-compose open a browser in URL **_http://localhost:81_**

The Angular app and the Spring Boot app are build and deploy within the containers using the multistage feature of Docker.
The docker files for each project are:

- Angular project in: **_/grocery-list-app/Dockerfile_**
- Spring Boot project in: **_/grocery-list-api/Dockerfile_**
