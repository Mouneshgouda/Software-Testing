```python
# Selenium + JDBC CRUD Cheat Sheet

> ## Goal
> Perform CRUD operations using **Selenium + Java + MySQL**.

---

# Overall Flow

```
Start
  │
  ▼
Import Packages
  │
  ▼
Create Main Method
  │
  ▼
Launch Browser
  │
  ▼
Open HTML Page
  │
  ▼
Connect Database
  │
  ▼
CREATE
  │
  ▼
READ
  │
  ▼
UPDATE
  │
  ▼
DELETE
  │
  ▼
READ Again
  │
  ▼
Close Database
  │
  ▼
Quit Browser
```

---

# Step 1 – Import Packages

### Why?

Need Selenium classes and JDBC classes.

```java
import java.sql.*;
import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
```

### Remember

```
SQL
+
Selenium
```

---

# Step 2 – Main Method

### Why?

Program execution starts here.

```java
public class hello {

    public static void main(String[] args) throws Exception {

    }
}
```

Remember

```
Class
↓

main()
```

---

# Step 3 – Launch Browser

### Logic

Ask yourself:

> How will Selenium control Chrome?

Create ChromeDriver.

```java
ChromeDriver driver = new ChromeDriver();
```

Maximize window.

```java
driver.manage().window().maximize();
```

Open webpage.

```java
driver.get("file:///...");
```

### Memory

```
Create Driver
↓

Maximize
↓

Open Page
```

---

# Step 4 – Connect Database

### Logic

Ask yourself:

> Where will user data be stored?

Connect MySQL.

```java
Connection con =
DriverManager.getConnection(
url,
username,
password);
```

### Memory

```
Connection
↓

DriverManager
↓

getConnection()
```

---

# Step 5 – CREATE

### Logic

Ask yourself:

> How do I add a user?

1. Fill HTML form
2. Insert into database
3. Print confirmation

```java
driver.findElement(...).sendKeys();

INSERT INTO users...

executeUpdate();
```

### Memory

```
Type Data
↓

Insert Query
↓

executeUpdate()
↓

Print
```

---

# Step 6 – READ

### Logic

Ask yourself:

> How do I display users?

Call

```java
showUsers(con);
```

Inside method

```java
SELECT * FROM users
```

Store

```java
ResultSet rs
```

Loop

```java
while(rs.next())
```

Print

```java
System.out.println(...)
```

### Memory

```
SELECT
↓

ResultSet
↓

Loop
↓

Print
```

---

# Step 7 – UPDATE

### Logic

Ask yourself:

> How do I change existing data?

1. Clear fields
2. Enter new data
3. Update database

```java
clear()

sendKeys()

UPDATE users...

executeUpdate()
```

### Memory

```
Clear
↓

New Data
↓

Update Query
↓

Print
```

---

# Step 8 – DELETE

### Logic

Ask yourself:

> How do I remove a user?

```java
DELETE FROM users...
```

```java
executeUpdate();
```

### Memory

```
Delete Query
↓

executeUpdate()
```

---

# Step 9 – READ Again

Always verify changes.

```java
showUsers(con);
```

### Memory

```
Delete
↓

Check Database
```

---

# Step 10 – Close Resources

```java
con.close();

driver.quit();
```

### Memory

```
Close Database
↓

Close Browser
```

---

# showUsers() Logic

```
Need Data
↓

Run SELECT
↓

Store ResultSet
↓

Loop
↓

Print
```

Skeleton

```java
ResultSet rs =
con.createStatement()
.executeQuery("select * from users");

while(rs.next())
{
    System.out.println(...);
}
```

---

# Selenium Cheat Sheet

```
ChromeDriver
      ↓
maximize()
      ↓
get()
      ↓
findElement()
      ↓
sendKeys()
      ↓
clear()
      ↓
click() (if needed)
      ↓
quit()
```

---

# JDBC Cheat Sheet

```
Connection
      ↓
PreparedStatement
      ↓
executeUpdate()
      ↓
executeQuery()
      ↓
ResultSet
      ↓
while(rs.next())
```

---

# SQL Cheat Sheet

## CREATE

```sql
INSERT INTO users(...)
VALUES(...);
```

## READ

```sql
SELECT * FROM users;
```

## UPDATE

```sql
UPDATE users
SET ...
WHERE id=1;
```

## DELETE

```sql
DELETE FROM users
WHERE id=1;
```

---

# Complete Mental Flow

```
Imports
   ↓
main()
   ↓
ChromeDriver
   ↓
maximize()
   ↓
get()
   ↓
Connection
   ↓
CREATE
   ↓
READ
   ↓
UPDATE
   ↓
DELETE
   ↓
READ Again
   ↓
close()
   ↓
quit()
```

---

# 30-Second Revision

```
Browser
↓

HTML

↓

Database

↓

Create

↓

Read

↓

Update

↓

Delete

↓

Read

↓

Close
```

---

# Golden Rule

Whenever you forget the code, ask yourself:

### Browser?

```
ChromeDriver

maximize()

get()
```

### Form?

```
findElement()

sendKeys()

clear()
```

### Database?

```
Connection

PreparedStatement
```

### Add / Update / Delete?

```
executeUpdate()
```

### Read?

```
executeQuery()

↓

ResultSet

↓

while(rs.next())
```

### Finish?

```
con.close();

driver.quit();
```

---

# One-Line Memory Trick

```
Browser
→ HTML
→ Database
→ Create
→ Read
→ Update
→ Delete
→ Read
→ Close
```

Or simply remember:

> **B → H → D → C → R → U → D → R → C → Q**

- **B** = Browser
- **H** = HTML
- **D** = Database
- **C** = Create
- **R** = Read
- **U** = Update
- **D** = Delete
- **R** = Read Again
- **C** = Close Database
- **Q** = Quit Browser

```

```python
     <dependency>
            <groupId>com.mysql</groupId>
            <artifactId>mysql-connector-j</artifactId>
            <version>9.3.0</version>
        </dependency>

```
