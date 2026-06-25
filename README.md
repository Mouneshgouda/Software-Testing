# saucedemo
https://www.saucedemo.com/


```python
import org.testng.annotations.Test;
import org.testng.Assert;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.WebElement;
public class multi {
    @Test
    public void login(){
        WebDriver driver=new ChromeDriver();
        driver.get("https://www.saucedemo.com/");
        driver.findElement(By.id("user-name")).sendKeys("standard_user");
        driver.findElement(By.id("password")).sendKeys("secret_sauce");
        driver.findElement(By.id("login-button")).click();
        String currenturl=driver.getCurrentUrl();
        Assert.assertTrue(currenturl.contains("inventory"),"login failed!");
        System.out.println("login success");
    }
}


```

# Calendera
https://demoqa.com/date-picker

# 2 And 3 Lab

https://demoqa.com/automation-practice-form



https://practicetestautomation.com/practice-test-login/


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



