# Grocery List

This Repository is the main repository that contains 2 **git submodules** projects:

| Project                                                               | Description                                          | Build                                                                                                                                           |
| --------------------------------------------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| [**grocery-list-app**](https://github.com/joanpablo/grocery-list-app) | an [Angular](https://angular.io/) application        | ![GitHub Workflow Status (branch)](https://img.shields.io/github/workflow/status/joanpablo/grocery-list-app/grocery-list/master?style=flat)     |
| [**grocery-list-api**](https://github.com/joanpablo/grocery-list-api) | a [Spring Boot](https://spring.io/) Restful services | ![GitHub Workflow Status (branch)](https://img.shields.io/github/workflow/status/joanpablo/grocery-list-api/grocery-list-api/master?style=flat) |

Both projects are parts of the **Grocery List Application**: Frontend, and Backend. You can go to each project repository to get a deep insight of how they are implemented.

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

# How to improve this simple solution?

1. Autocomplete of products while typing the product name.
2. Support for multiple languages (i18n).
3. Deploy on the Cloud.
4. Social Media Authentication.
5. Contract first approach.
6. Enhances UI.

### 1. Autocomplete of products while typing the product name

One way of enhancing the user experience is to suggest the product name while the user is typing it. This way the user will not need to write full words and will just select the best match to the product it is looking for.

Out there is a lot of third-party APIs that return a list of products with images. I can mention:

- [BigOven Recipe REST API](https://api2.bigoven.com/)
- [Kroger REST API](https://developer.kroger.com/)

### 2. Support for multiple languages (i18n)

If the application becomes popular and is used in several regions of the globe is always a smart decision to have the application in several languages.

In all my Angular applications I have always used the library [ngx-translate](http://www.ngx-translate.com/). It is a really easy and great way to add internationalization to your projects.

### 3. Deploy on the Cloud

The first thing you want to do if your application starts growing in users is to start using Cloud Computing.

Deploy the solution in AWS or Google Cloud, or Azure will bring several benefits:

- Go global in minutes (easily deploy the app in multiple regions around the world)
- Stop guessing capacity (resources can scale in or out depending upon demand)
- Increase speed and agility (new IT resources like more storage, and more RAM are only a click away)

In the Cloud, the solution can scale horizontally (more instances of the app) or vertically (more resources) depending on the demand. For example, a simple first approach could be to scale the Angular and Spring Boot app with multiple instances and use the [AWS RDS](https://aws.amazon.com/rds/) (Relational Database Service) with MySQL will help to scale the database.

Also, the Cloud brings a huge range of features and services to help solve common problems, such as:

- Load balancing ([AWS ELB](https://aws.amazon.com/elasticloadbalancing/))
- Autoscaling ([AWS Auto Scaling](https://aws.amazon.com/autoscaling/))

### 4. Social Media Authentication

If you plan to have millions of users is always a good idea to include authentication and authorization in your solution. One of the simplest ways for common users to authenticate is the use of social media accounts.

Letting a user authenticate in the application using his Google or Facebook account is a very nice and simple feature you can include in your application.

The design of the Database will evolve a bit because right now we will need to create a cart for each user, but is a very simple solution.

### 5. Contract first approach

When you are working in Teams, it is always a good practice to have a **Contract First Approach**. This means that you first create the contract of your services and then the UI Team and the Backend teams implement the solution based on that contract previously defined.

The use of [Swagger](https://swagger.io/) tools to describe the services and then generate the Backend interfaces based on that description is a recommended practice.

In projects with Spring Boot, I have always used [OpenAPI Generator](https://openapi-generator.tech/) to generate the backend interfaces with great results.

### 6. Enhances UI

Having a nice and attractive design is a great way to make users experience a pleasant feeling when using the application.

A simple [Internet](https://dribbble.com/tags/grocery_list) search will turn up very pretty designs that I would have liked to use for the grocery app.
