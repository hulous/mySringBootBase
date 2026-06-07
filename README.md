# mySringBootBase

Spring Boot base project with:

- Spring Web MVC
- Spring Security
- Spring Data JPA
- Liquibase
- PostgreSQL
- OpenAPI UI (springdoc)

## Prerequisites

- Java 21+
- Maven 3.8+
- PostgreSQL running locally or reachable from this app

## Project Structure

- Application entry point: src/main/java/com/hulous/base/BaseApplication.java
- Main config: src/main/resources/application.yaml
- Environment values: src/main/resources/env.properties
- Example environment values: .env.sample.properties

## Environment Configuration

The app imports env values from src/main/resources/env.properties.

1. Copy the sample file:

```bash
cp .env.sample.properties src/main/resources/env.properties
```

2. Update values in src/main/resources/env.properties.

Required keys:

- DB_NAME
- DB_HOST
- DB_PORT
- DB_USER
- DB_PASSWORD
- JWT_SECRET_TOKEN
- MAIN_APP_PORT

Notes:

- Use a strong random value for JWT_SECRET_TOKEN.
- MAIN_APP_PORT controls the HTTP port used by Spring Boot.

## Run the Application

Start with Maven:

```bash
mvn spring-boot:run
```

Build a jar:

```bash
mvn clean package
```

Run tests:

```bash
mvn test
```

## API Docs

Once the app is running, OpenAPI UI is available at:

- http://localhost:${MAIN_APP_PORT}/swagger-ui/index.html

## Database Migrations

Liquibase dependency is included. Add changelogs under:

- src/main/resources/db/changelog

## Important Note About Maven Wrapper

This repository currently has mvnw/mvnw.cmd scripts but is missing wrapper metadata in .mvn/wrapper.
Because of that, ./mvnw does not work at the moment.

Use system Maven commands (mvn ...) until wrapper files are restored.
