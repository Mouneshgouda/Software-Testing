```python

import java.sql.*;
import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;

public class Hello {
    public static void main(String[] args) throws Exception {

        ChromeDriver driver = new ChromeDriver();
        driver.get("file:///C:/Users/LENOVO/IdeaProjects/simple/reports/report.html");

        Connection con = DriverManager.getConnection(
                "jdbc:postgresql://localhost:5432/seleniumcru",
                "postgres",
                "your_password"
        );

        // Create
        driver.findElement(By.id("name")).sendKeys("Guru");
        driver.findElement(By.id("email")).sendKeys("guru@gmail.com");
        con.createStatement().executeUpdate(
                "INSERT INTO users(name,email) VALUES('Guru','guru@gmail.com')");

        show(con);

        // Update
        con.createStatement().executeUpdate(
                "UPDATE users SET name='Guru Updated', email='guru123@gmail.com' WHERE id=1");

        // Delete
        con.createStatement().executeUpdate(
                "DELETE FROM users WHERE id=2");

        show(con);

        con.close();
        driver.quit();
    }

    static void show(Connection con) throws Exception {
        ResultSet rs = con.createStatement().executeQuery("SELECT * FROM users");
        while (rs.next())
            System.out.println(rs.getInt(1) + " " + rs.getString(2) + " " + rs.getString(3));
    }
}

```
## html

```python


<!DOCTYPE html>
<html>
<head>
    <title>Simple CRUD</title>
</head>

<body>

<h2>User Form</h2>

<label>Name:</label>
<input type="text" id="name">

<br><br>

<label>Email:</label>
<input type="text" id="email">

<br><br>

<button id="add">Add</button>
<button id="update">Update</button>
<button id="delete">Delete</button>
<button id="read">Read</button>

</body>
</html>


```


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




