```python
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class hi {

    public static void main(String[] args) throws InterruptedException {

        WebDriver driver = new ChromeDriver();
        driver.manage().window().maximize();

        driver.get("https://demoqa.com/automation-practice-form");

        // First Name
        driver.findElement(By.id("firstName")).sendKeys("Mounesh");

        // Last Name
        driver.findElement(By.id("lastName")).sendKeys("Patil");

        // Email
        driver.findElement(By.id("userEmail")).sendKeys("hi@gmail.com");

        // Gender
        driver.findElement(By.xpath("//label[text()='Male']")).click();

        // Mobile Number
        driver.findElement(By.id("userNumber")).sendKeys("1234567890");

        // Hobby
        driver.findElement(By.xpath("//label[text()='Sports']")).click();

        // Address
        driver.findElement(By.id("currentAddress"))
                .sendKeys("Bangalore, Karnataka");

        // Upload Picture
        driver.findElement(By.id("uploadPicture"))
                .sendKeys("C:\\Users\\gurup\\Downloads\\WhatsApp Image 2026-06-15 at 8.59.21 AM.jpeg");

        Thread.sleep(2000);

        // Move focus and submit
        driver.findElement(By.tagName("body"))
                .sendKeys(Keys.END);

        Thread.sleep(1000);

        driver.findElement(By.id("submit"))
                .sendKeys(Keys.ENTER);

        Thread.sleep(5000);

        driver.quit();
    }
}
```





https://practicetestautomation.com/practice-test-login/


## Programe 1

``` java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LoginAutomation {

    public static void main(String[] args) {

        // Launch Chrome Browser
        WebDriver driver = new ChromeDriver();

        // Open Website
        driver.get("https://practicetestautomation.com/practice-test-login/");

        // Maximize Window
        driver.manage().window().maximize();

        // Enter Username
        WebElement username =
                driver.findElement(By.id("username"));
        username.sendKeys("student");

        // Enter Password
        WebElement password =
                driver.findElement(By.id("password"));
        password.sendKeys("Password123");

        // Click Login Button
        WebElement loginBtn =
                driver.findElement(By.id("submit"));
        loginBtn.click();

        // Verify Login
        String title = driver.getTitle();
        System.out.println("Page Title: " + title);

        // Close Browser
        driver.quit();
    }
}
```



## Google

```java

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class SeleniumTest {

    public static void main(String[] args) {

        WebDriver driver = new ChromeDriver();

        driver.get("https://www.google.com");

        System.out.println("Page Title: " + driver.getTitle());

        driver.quit();
    }
}

```

## pom.xml

```python

<dependencies>
    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>4.33.0</version>
    </dependency>
</dependencies>

```

```python

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;


public class hi {

    public static void main(String[] args) {

        WebDriver driver = new ChromeDriver();

        driver.get("https://www.google.com");

        WebElement searchBox = driver.findElement(By.name("q"));
        searchBox.sendKeys(("what is java"));
        searchBox.submit();


        System.out.println("Page Title: " + driver.getTitle());

        driver.quit();
    }
}


```



