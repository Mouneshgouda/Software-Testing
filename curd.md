```python

CREATE DATABASE seleniumcru;


CREATE TABLE users
(
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100)
);

INSERT INTO users(name,email)
VALUES
('John','john@gmail.com'),
('Alice','alice@gmail.com');

SELECT * FROM users;

```

## post

```python

<dependencies>

    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>4.34.0</version>
    </dependency>

    <dependency>
        <groupId>org.postgresql</groupId>
        <artifactId>postgresql</artifactId>
        <version>42.7.7</version>
    </dependency>

</dependencies>

```

```python
        Connection con = DriverManager.getConnection(
                "jdbc:postgresql://localhost:5432/seleniumcru",
                "postgres",
                "your_password"
        );

```
