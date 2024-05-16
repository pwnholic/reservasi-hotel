# Hotel Reservation Back-end

This project revolves around facilitating hotel room bookings for users while offering administrators a platform to manage reservations efficiently. It implements secure authentication and authorization through JWT tokens. The core functionalities include CRUD API for seamless handling of hotel and room data in JSON format. Additionally, the project provides essential scripts for database management, including tasks like seeding and migration.

## Project outline

- Users -> book room from an hotel
- Admins -> going to check reservation/bookings
- Authentication and authorization -> JWT tokens
- Hotels -> CRUD API -> JSON
- Rooms -> CRUD API -> JSON
- Scripts -> database management -> seeding, migration

## How it works

> [!Note]
> I didnt write too much code documentation so if you are curious, just read the test cases if you re wondering how the existing functionality works

1. **Clone this repo**

```sh
git clone https://github.com/pwnholic/reservasi-hotel.git
cd reservasi-hotel/
go get
```

2. **Set the Env file**

```env
HTTP_LISTEN_ADDRESS=:3333
JWT_SECRET=
MONGO_DB_NAME=hotel-reservation
MONGO_DB_URL=mongodb://localhost:27017
MONGO_DB_URL_TEST=mongodb://localhost:27017
```

- **Makefile**

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
