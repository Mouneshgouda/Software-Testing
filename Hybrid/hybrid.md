# Selenium Framework Types (POM, Data-Driven, Keyword-Driven & Hybrid)

## Introduction

When learning Selenium, you'll often hear about these framework types:

- **Page Object Model (POM)**
- **Data-Driven Framework**
- **Keyword-Driven Framework**
- **Hybrid Framework**

These are **not different Selenium tools**. They are simply different ways of organizing your automation project so it is easier to maintain.

---

# 1. Page Object Model (POM)

## Purpose

POM keeps all **web element locators and page actions** in one class.

Instead of writing Selenium code in every test, we create a page class.

---

## Without POM

Every test repeats the same code.

```java
driver.findElement(By.id("username")).sendKeys("admin");
driver.findElement(By.id("password")).sendKeys("1234");
driver.findElement(By.id("login")).click();
```

Imagine you have **50 tests** using the Login page.

If

```java
By.id("username")
```

changes to

```java
By.name("user")
```

you must update all 50 tests.

---

## With POM

### LoginPage.java

```java
public class LoginPage {

    WebDriver driver;

    public LoginPage(WebDriver driver) {
        this.driver = driver;
    }

    public void login(String username, String password) {

        driver.findElement(By.id("username"))
              .sendKeys(username);

        driver.findElement(By.id("password"))
              .sendKeys(password);

        driver.findElement(By.id("login"))
              .click();
    }
}
```

### Test Class

```java
LoginPage page = new LoginPage(driver);

page.login("admin", "1234");
```

Now if the locator changes, you only update **LoginPage.java**.

### Summary

✅ POM stores:

- Web element locators
- Page actions

---

# 2. Data-Driven Framework

## Purpose

Data-Driven Framework keeps **test data outside Java code**.

Examples:

- Excel
- CSV
- JSON
- Properties file

---

## Without Data-Driven

```java
page.login("admin","1234");

page.login("john","abcd");

page.login("alice","xyz");
```

Every time new test data is needed, Java code must change.

---

## With Data-Driven

### Excel

| Username | Password |
|-----------|----------|
| admin | 1234 |
| john | abcd |
| alice | xyz |

Java simply reads one row at a time.

```java
page.login(username, password);
```

Tomorrow someone adds

| Username | Password |
|-----------|----------|
| manager | test123 |

No Java code changes.

Only Excel changes.

### Summary

✅ Data-Driven stores:

- Username
- Password
- URL
- Search text
- Expected values

outside the Java code.

---

# 3. Keyword-Driven Framework

## Purpose

Instead of writing Java code, we write simple **keywords**.

Examples:

- OPEN_BROWSER
- OPEN_URL
- CLICK
- TYPE
- VERIFY

---
