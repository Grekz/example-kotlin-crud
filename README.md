# Tutorial: Creating a REST api with Kotlin + SpringBoot + JPA + Flyway

## Setup

You need to have a mysql database running with a database named: 'kotlin_crud_db'
Let's run this command and you will have it:
```shell script
$ docker run --rm --name test-mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_DATABASE=kotlin_crud_db -d mysql:latest
```

## Running the app

```shell script
$ gradle bootRun 
```

## Manual testing

```shell script
## Get all tasks
$ curl --location --request GET 'localhost:8080/v1/api/tasks'

## Get task by id
$ curl --location --request GET 'localhost:8080/v1/api/tasks/1'

## Post task
$ curl --location --request POST 'localhost:8080/v1/api/tasks/' \
--header 'Content-Type: application/json' \
--data-raw '{
	"title": "new 2nd task", 
	"status": 1, 
	"priority": 1,
	"description":"2244 blah blah task"
}'

## Update task
$ curl --location --request PUT 'localhost:8080/v1/api/tasks/2' \
--header 'Content-Type: application/json' \
--data-raw '{
	"title": "blah blah new 2nd task", 
	"status": 1, 
	"priority": 1,
	"description":"2244 blah blah task"
}'

## Delete task
$ curl --location --request DELETE 'localhost:8080/v1/api/tasks/2'
```
