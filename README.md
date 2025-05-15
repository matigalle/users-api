# User management microservice

REST API for creating and retrieving user information, using a relational database. It performs these operations through the endpoints described below.

**User creation**

- Endpoint: /sign-up  
- HTTP method: POST

Example:

Request body:
```json
{
  "name": "Julio Gonzalez",
  "email": "julio@testssw.cl",
  "password": "a2asfGfdfdf4",
  "phones": [
    {
      "number": 87650009,
      "citycode": 7,
      "contrycode": "25"
    }
  ]
}
```

Response body:
```json
{
  "id": "e5c6cf84-8860-4c00-91cd-22d3be28904e",
  "created": "Nov 16, 2021 12:51:43 PM",
  "lastLogin": "Nov 16, 2021 12:51:43 PM",
  "token": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJqdWxpb0B0ZXN0...",
  "isActive": true,
  "name": "Julio Gonzalez",
  "email": "julio@testssw.cl",
  "password": "a2asfGfdfdf4",
  "phones": [
    {
      "number": 87650009,
      "citycode": 7,
      "contrycode": "25"
    }
  ]
}
```

**User retrieval**

- Endpoint: /login
- HTTP method: GET

Example:

Request header:  
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJqdWxpb0B0ZXN0...

Response body:
```json
{
  "id": "e5c6cf84-8860-4c00-91cd-22d3be28904e",
  "created": "Nov 16, 2021 12:51:43 PM",
  "lastLogin": "Nov 16, 2021 12:51:43 PM",
  "token": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJqdWxpb0B0ZXN0...",
  "isActive": true,
  "name": "Julio Gonzalez",
  "email": "julio@testssw.cl",
  "password": "a2asfGfdfdf4",
  "phones": [
    {
      "number": 87650009,
      "citycode": 7,
      "contrycode": "25"
    }
  ]
}
```

## API usage instructions

It is necessary to have JDK 11 installed.

To run the app:
```
./gradlew bootRun
```

The API will be available at ```http://localhost:8080```.

To run the tests:
```
./gradlew test
```

## Technologies

- Java 11
- Gradle
- Spring Boot
- JUnit
- Mockito
- Lombok
- Spring Data JPA
- H2 database