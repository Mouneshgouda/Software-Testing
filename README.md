## Mysql Install

https://medium.com/@mouneshpatil001/git-integration-with-pycharm-ide-7c40b71a8166?source=user_profile_page---------21-------------c0a81552e44e----------------------

## jdbc connection mysql


```html

<!DOCTYPE html>
<html>
<head>
    <title>Simple CRUD</title>
</head>
<body>

<h2>User Form</h2>

Name:
<input type="text" id="name"><br><br>

Email:
<input type="text" id="email"><br><br>

<button id="add">Add</button>
<button id="update">Update</button>
<button id="delete">Delete</button>
<button id="read">Read</button>

</body>
</html>


```
# MySQL Root Password Update

Use the following SQL commands to change the password for the MySQL `root` user.

## For MySQL 8.0+

```sql
ALTER USER 'root'@'localhost' IDENTIFIED BY 'newpassword';
FLUSH PRIVILEGES;
```

```python
        Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/databasename",
                "username",
                "password");

```


## Drag and drop
https://demo.automationtesting.in/Dynamic.html

```python

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

public class hello {

    public static void main(String[] args) {

        ChromeDriver driver = new ChromeDriver();

        driver.manage().window().maximize();

        driver.get("https://demo.automationtesting.in/Dynamic.html");

        // Get all draggable images
        List<WebElement> images = driver.findElements(By.xpath("//img"));

        // Get drop area
        WebElement dropArea = driver.findElement(By.id("droparea"));

        // Actions class
        Actions act = new Actions(driver);

        // Drag each image
        for (WebElement image : images) {

            act.dragAndDrop(image, dropArea).perform();
        }

        driver.quit();
    }
}


```

## Webtable 
https://the-internet.herokuapp.com/tables


```python

import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
import java.util.List;

public class hello {
    public static void main(String[] args){
        WebDriver driver =new ChromeDriver();
        driver.get("https://the-internet.herokuapp.com/tables");
        WebElement table1=driver.findElement(By.id("table1"));
        List<WebElement> rows=table1.findElements(By.xpath(".//tbody/tr"));
        for(int i=1;i<=rows.size();i++){
            List<WebElement> columns=table1.findElements(
                    By.xpath(".//tbody/tr["+i+"]/td"));
            for(int j=1;j<= columns.size();j++){
                String value=driver.findElement(
                        By.xpath(".//tbody/tr["+i+"]/td["+j+"]")).getText();
                System.out.print(value+"\t");
            }
            System.out.println();
        }
        driver.quit();
    }
}

```

## Alerat
https://the-internet.herokuapp.com/javascript_alerts

## Frame
https://demo.automationtesting.in/Frames.html

## Orange page

https://opensource-demo.orangehrmlive.com/web/index.php/auth/login

```python
import com.aventstack.extentreports.*;
import com.aventstack.extentreports.reporter.ExtentSparkReporter;
import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;

import java.io.File;
import java.nio.file.Files;
import java.nio.file.StandardCopyOption;

public class hi {

    public static void main(String[] args) throws Exception {

        // Create reports folder
        new File("6Experiment").mkdir();

        // Extent Report
        ExtentReports extentReports = new ExtentReports();
        extentReports.attachReporter(new ExtentSparkReporter("6Experiment/multi.html"));
        ExtentTest test = extentReports.createTest("OrangeHRM Automation Test");
        WebDriver driver=new ChromeDriver();
        driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");




    }


}
```

    



#  Mouse
https://demoqa.com/buttons




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


```python

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

public class hi {
    public static void main(String[] args){
        WebDriver driver=new ChromeDriver();
        driver.get("https://demoqa.com/date-picker");
        driver.findElement(By.id("datePickerMonthYearInput")).click();
        new Select(driver.findElement(By.className("react-datepicker__month-select"))).selectByVisibleText("May");
        new Select(driver.findElement(By.className("react-datepicker__year-select"))).selectByValue("2001");
        driver.findElement(By.xpath("//div[text()='20']")).click();


    }
}

```


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



