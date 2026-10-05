# Spring JDBC CRUD Challenge

Project completed as part of a Spring Boot and JDBC exercise.

## Objective

The goal of this project is to implement a complete CRUD for magic schools using Spring Boot, JDBC and a generic DAO interface.

## Technologies Used

- Java
- Spring Boot
- JDBC
- MySQL
- Thymeleaf
- HTML
- Maven

## CRUD Operations

The application supports the four main database operations:

- Create
- Read
- Update
- Delete

## DAO

The project uses a generic DAO interface:

```java
public interface CrudDao<T> {

    T save(T entity);

    T findById(Long id);

    List<T> findAll();

    T update(T entity);

    void deleteById(Long id);
}
```

## Features

- Display all schools
- Display one school by ID
- Create a new school
- Update an existing school
- Delete a school
- Use a generic DAO interface
- Use JDBC with `PreapredStatement`
- Map SQL results to java objects

## JDBC Operations

# Create 
INSERT INTO school (name, capacity, country) <br>
VALUES (?, ?, ?);

# Read
SELECT * FROM school; <br>
SELECT * FROM school WHERE id = ?;

# Update
Update school <br>
SET name = ?, capacity = ?, country = ? <br>
WHERE id = ?;

# Delete
DELETE FROM school <br>
WHERE id = ?;

## How It Works 
- The controller receives HTTP requests.
- The controller calls `SchoolRespository`.
- `SchoolRepository` implements `CrudDao<School>`.
- JDBC executes SQL queries against the MySQL database.
- Database rows are mapped to `School` objects.
- Thymeleaf displays the data in HTML pages.
