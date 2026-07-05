
## java 
```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class dd {
    public static void main(String[] args) {

        WebDriver driver = new ChromeDriver();

        driver.get("https://practicetestautomation.com/practice-test-login/");

        driver.findElement(By.id("username"))
                .sendKeys("student");

        driver.findElement(By.id("password"))
                .sendKeys("Password123");

        driver.findElement(By.id("submit"))
                .click();

        System.out.println("Title: " + driver.getTitle());

        driver.quit();
    }
}

```

### Pom.xml
``` java

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.example</groupId>
    <artifactId>untitled</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>26</maven.compiler.source>
        <maven.compiler.target>26</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>
    <dependencies>
        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-java</artifactId>
            <version>4.22.0</version>
        </dependency>
    </dependencies>
</project>



```

```python

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

public class DatePickerSimple {

    public static void main(String[] args) {

        WebDriver driver = new ChromeDriver();

        driver.get("https://demoqa.com/date-picker");

        driver.findElement(By.id("datePickerMonthYearInput")).click();

        new Select(driver.findElement(By.className("react-datepicker__month-select")))
                .selectByVisibleText("June");

        new Select(driver.findElement(By.className("react-datepicker__year-select")))
                .selectByVisibleText("2026");

        driver.findElement(By.xpath("//div[text()='21']")).click();

        driver.quit();
    }


```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

public class hi {

    public static void main(String[] args) throws InterruptedException {

        WebDriver driver = new ChromeDriver();
        driver.manage().window().maximize();

        driver.get("https://demoqa.com/buttons");
        

        Actions actions = new Actions(driver);

        // Double Click
        actions.doubleClick(driver.findElement(By.id("doubleClickBtn"))).perform();
        Thread.sleep(2000);

        // Right Click
        actions.contextClick(driver.findElement(By.id("rightClickBtn"))).perform();
        Thread.sleep(2000);

        // Normal Click
        driver.findElement(By.xpath("//button[text()='Click Me']")).click();
        Thread.sleep(2000);
        driver.quit();
    }
}

```
}


```

```python

   <dependency>
            <groupId>com.aventstack</groupId>
            <artifactId>extentreports</artifactId>
            <version>4.1.7</version>
        </dependency>

```


```python

import com.aventstack.extentreports.ExtentReports;
import com.aventstack.extentreports.ExtentTest;
import com.aventstack.extentreports.reporter.ExtentHtmlReporter;

public class hello {

    public static void main(String[] args) {

        ExtentHtmlReporter htmlReporter =
                new ExtentHtmlReporter("reports/report.html");

        ExtentReports extent = new ExtentReports();
        extent.attachReporter(htmlReporter);

        ExtentTest test = extent.createTest("Sample Test");

        test.pass("Application opened successfully");
        test.info("This is an information message");
        test.warning("This is a warning");
        test.fail("This is a sample failure");

        extent.flush();

        System.out.println("Report Generated!");
    }
}


```


```python

import com.aventstack.extentreports.ExtentReports;
import com.aventstack.extentreports.ExtentTest;
import com.aventstack.extentreports.reporter.ExtentHtmlReporter;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BookStoreReport {

    public static void main(String[] args) {

        ExtentHtmlReporter reporter =
                new ExtentHtmlReporter("reports/BookStoreReport.html");

        ExtentReports extent = new ExtentReports();
        extent.attachReporter(reporter);

        ExtentTest test = extent.createTest("Books To Scrape Test");

        WebDriver driver = new ChromeDriver();

        try {

            test.info("Launching Chrome");

            driver.manage().window().maximize();

            driver.get("https://books.toscrape.com/");

            test.pass("Website Opened Successfully");

            String title = driver.getTitle();
            test.info("Page Title : " + title);

            if(title.equals("All products | Books to Scrape - Sandbox")) {
                test.pass("Title Verified");
            } else {
                test.fail("Title Verification Failed");
            }

            String firstBook = driver.findElement(By.cssSelector("article.product_pod h3 a"))
                                     .getAttribute("title");

            test.info("First Book : " + firstBook);

            driver.findElement(By.cssSelector("article.product_pod h3 a")).click();

            test.pass("Clicked First Book");

            String price = driver.findElement(By.className("price_color")).getText();

            test.info("Book Price : " + price);

            test.pass("Price Retrieved Successfully");

        } catch (Exception e) {

            test.fail(e.getMessage());

        } finally {

            driver.quit();
            test.info("Browser Closed");

            extent.flush();
        }
    }
}


```
