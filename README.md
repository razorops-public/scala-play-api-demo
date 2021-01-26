## Razorops CI/CD pipeline demo with Play Framework

This is an example code to demonstrate how to create [Scala](https://docs.docker.com/compose/) based pipeline on [Razorops](https://docs.razorops.com/) platform.

This application consists of REST APIs to perform CRUD operations using PlayFramework, Scala and Elasticsearch(v6.x) as database.

### Local Setup

#### Prerequisite
* [sbt](https://www.scala-sbt.org/)
* [Docker](https://www.docker.com/)
* [docker-compose](https://docs.docker.com/compose/)

Once you have above software installed. Download/checkout the project and jump to project directory. Then run below commands to run the application:

```bash
docker-compose up
```
This will start elasticsearch in docker. You can check the status of elasticsearch from your browser by hitting the URL: <http://localhost:9200/>

Once your elasticsearch is up and running. It's time to start the application.

Run below command to start the application:

```bash
sbt run
```

Play will start up on the HTTP port at <http://localhost:9000/>.   You don't need to deploy or reload anything -- changing any source code while the server is running will automatically recompile and hot-reload the application on the next HTTP request.

#### Testing 
* To execute tests:
```
sbt test
```

#### Swagger
* Swagger documentation of REST APIs can be found at <http://localhost:9000/docs/>

### CI/CD pipeline

If you're new to Razorops, feel free to fork this repository and use it to [create a project](https://docs.razorops.com/getting_started/).

`.razorops.yaml` contains the pipeline code to build and execute the tests for this project. To know more about how to write and customize, refer to the [documentation](https://docs.razorops.com).

It uses Docker-Compose commands to bootstrap the containers and exec into web container to run the tests. Here is the link of [the pipeline](https://dashboard.razorops.com/apps/weathered-glade-4304/workflows) workflows page.

### License

The code is inspired from [scala-play-rest-example](https://github.com/tarangbhalodia/scala-play-rest-example) and adjusted to incorporated few changes required. 
