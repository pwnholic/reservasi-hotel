# Hotel Reservation Back-end

## Project outline

- Users -> book room from an hotel
- Admins -> going to check reservation/bookings
- Authentication and authorization -> JWT tokens
- Hotels -> CRUD API -> JSON
- Rooms -> CRUD API -> JSON
- Scripts -> database management -> seeding, migration

## Makefile

```Makefile
build:
	@go build -o bin/api

run: build
	@./bin/api

seed:
	@go run scripts/seed.go

docker:
	echo "building docker file"
	@docker build -t api .
	echo "running API inside Docker container"
	@docker run -p 3000:3000 api

test:
	@go test -v ./...
```

## Resources

### Mongodb driver

Documentation

```
https://mongodb.com/docs/drivers/go/current/quick-start
```

Installing mongodb client

```
go get go.mongodb.org/mongo-driver/mongo
```

### gofiber

Documentation

```
https://gofiber.io
```

Installing gofiber

```sh
go get -u github.com/gofiber/fiber/v2
```

## Docker

### Installing mongodb as a Docker container

```
docker run --name mongodb -d mongo:latest -p 27017:27017
```
