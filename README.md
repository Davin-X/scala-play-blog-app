# Scala Play Blog App

A sample blog/user API built with [Play Framework](https://www.playframework.com/) (Scala 2.13) +
Slick + PostgreSQL. Covers controllers, services, JSON validation, and tests with
`scalatestplus-play`.

## Stack

- Scala 2.13.14, Play 3.x (`PlayScala` plugin), Guice
- Slick 3.4 + HikariCP, PostgreSQL 42.6 driver
- Tests: `scalatestplus-play`

## Requirements

- JDK 11+ and [sbt](https://www.scala-sbt.org/)
- PostgreSQL running locally (see `conf/application.conf` for the JDBC URL)

## Run

```bash
sbt run
# dev server on http://localhost:9000
```

## Test

```bash
sbt test
```

## API

| Method | Path              | Description              |
|--------|-------------------|--------------------------|
| GET    | `/`               | Sample home page         |
| POST   | `/api/user`       | Create a single user     |
| POST   | `/api/users`      | Create multiple users    |
| GET    | `/api/users`      | List all users           |
| GET    | `/api/user/:id`   | Get user by id           |
| PUT    | `/api/user/:id`   | Update user by id        |
| DELETE | `/api/user/:id`   | Delete user by id        |

Layout: `app/controllers/` → `app/services/` → `app/entities/`, routes in
`conf/routes`, evolving schemas via `play-slick-evolutions`, specs under `test/`.
