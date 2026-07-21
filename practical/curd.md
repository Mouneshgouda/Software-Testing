```python

import java.sql.*;
import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;

public class hello {

    public static void main(String[] args) throws Exception {

        // Launch Chrome
        ChromeDriver driver = new ChromeDriver();
        driver.manage().window().maximize();

        // Open HTML file
        driver.get("file:///C:/Users/LENOVO/IdeaProjects/simple/reports/report.html");

        // Load PostgreSQL Driver
        Class.forName("org.postgresql.Driver");

        // PostgreSQL Connection
        Connection con = DriverManager.getConnection(
                "jdbc:postgresql://localhost:5432/seleniumcru",
                "postgres",
                "your_password"   // Replace with your PostgreSQL password
        );

        // ---------------- CREATE ----------------
        driver.findElement(By.id("name")).sendKeys("Guru");
        driver.findElement(By.id("email")).sendKeys("guru@gmail.com");

        PreparedStatement ps1 = con.prepareStatement(
                "INSERT INTO users(name,email) VALUES(?,?)");
        ps1.setString(1, "Guru");
        ps1.setString(2, "guru@gmail.com");
        ps1.executeUpdate();

        System.out.println("User Added");
        Thread.sleep(2000);

        // ---------------- READ ----------------
        showUsers(con);

        // ---------------- UPDATE ----------------
        driver.findElement(By.id("name")).clear();
        driver.findElement(By.id("email")).clear();

        driver.findElement(By.id("name")).sendKeys("Guru Updated");
        driver.findElement(By.id("email")).sendKeys("guru123@gmail.com");

        PreparedStatement ps2 = con.prepareStatement(
                "UPDATE users SET name=?, email=? WHERE id=?");
        ps2.setString(1, "Guru Updated");
        ps2.setString(2, "guru123@gmail.com");
        ps2.setInt(3, 1);
        ps2.executeUpdate();

        System.out.println("\nUser Updated");
        Thread.sleep(2000);

        // ---------------- DELETE ----------------
        PreparedStatement ps3 = con.prepareStatement(
                "DELETE FROM users WHERE id=?");
        ps3.setInt(1, 2);
        ps3.executeUpdate();

        System.out.println("\nUser Deleted");
        Thread.sleep(2000);

        // ---------------- READ AGAIN ----------------
        showUsers(con);

        con.close();
        driver.quit();
    }

    static void showUsers(Connection con) throws Exception {

        Statement st = con.createStatement();
        ResultSet rs = st.executeQuery("SELECT * FROM users");

        System.out.println("\n------ USERS ------");

        while (rs.next()) {
            System.out.println(
                    rs.getInt("id") + "  " +
                    rs.getString("name") + "  " +
                    rs.getString("email")
            );
        }

        rs.close();
        st.close();
    }
}

```


## Html

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


# create Database

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

## MAvenn Dependence

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






