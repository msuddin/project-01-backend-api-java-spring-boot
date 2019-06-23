# project-01-backend-api-java-spring-boot

## Purpose

### Question:
What is the purpose of this project?

### Answer:
#### Main
* Main Application run's a Spring Application which picks up all rest controllers
* The HelloController (a RestController class) exposes one api's ('/hi/{id}')
* The AccountService (a Service class) uses a JpaRepository to perform CRUD operations
* The AccountService class uses the Account class as an Entity class
* The Account (an Entity class) matches each of it's member variables to a table, table must be named the same as the class
* The AccountRepository (a Repository interface) extends the JpaRepository interface and provides default CRUD operations
* The controllers need to allow cross origin requests in order to make calls to the API's
* Added a Logger to the Home Controller
* Serves as a backend api for a local react web app

#### Test
* Under main/resources, the application.properties looks for a local instance of postgres db
* Under src/test/java, two tests for service and controller
* The controller test uses TestRestTemplate to perform a get and assert on the content to the URL

## Dependencies
* This project assumes that postgresql://localhost:5432/db is available
* This project assumes that the docker container found at https://github.com/msuddin/project-01-db-postgress-docker-container is running locally

## Instructions
From the root directory of the project, run the command below to run the tests and build the jar:
```
./gradlew clean build
```
Now let's run the jar:
```
ava -jar build/libs/<jar_name>.jar
```
The application should now start-up.

## API Endpoints
### /hi{id}
You can curl to get one record at a time (1-3):
```
curl http://localhost:8080/hi/1
```
Output should be:
```
Hi batman
```
