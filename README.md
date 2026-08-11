```python
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class hello {

    public static void main(String[] args) throws Exception {

        WebDriver driver = new ChromeDriver();

        // Change this to your HTML file location
        driver.get("https://mouneshgouda.github.io/Hospital-Appointment/");

        driver.manage().window().maximize();

        // 1. Select Cardiology
        driver.findElement(
                By.cssSelector(
                        ".department[data-dept='Cardiology']"
                )
        ).click();

        Thread.sleep(1000);

        // 2. Select doctor
        WebElement doctor = driver.findElement(
                By.xpath(
                        "//h4[normalize-space()='Dr. Ananya Rao']"
                )
        );

        doctor.findElement(
                By.xpath(
                        "./ancestor::div[contains(@class,'doctor')]"
                )
        ).click();

        Thread.sleep(500);

        // 3. Continue
        driver.findElement(
                By.id("doctorNext")
        ).click();

        Thread.sleep(500);

        // 4. Select first available date
        driver.findElement(
                By.cssSelector(".date")
        ).click();

        // 5. Select first available time
        driver.findElement(
                By.cssSelector(".time:not(.booked)")
        ).click();

        // 6. Continue
        driver.findElement(
                By.id("dateNext")
        ).click();

        // 7. Patient name
        driver.findElement(
                By.id("patientName")
        ).sendKeys("Rahul Kumar");

        // 8. Phone
        driver.findElement(
                By.id("phone")
        ).sendKeys("9876543210");

        // 9. Email
        driver.findElement(
                By.id("email")
        ).sendKeys("rahul@gmail.com");

        // 10. Date of birth
        driver.findElement(
                By.id("dob")
        ).sendKeys("05/15/1995");

        // 11. Gender
        driver.findElement(
                By.id("gender")
        ).sendKeys("Male");

        // 12. Patient type
        driver.findElement(
                By.id("patientType")
        ).sendKeys("New patient");

        // 13. Reason
        driver.findElement(
                By.id("reason")
        ).sendKeys("Regular consultation");

        // 14. Review
        driver.findElement(
                By.id("patientNext")
        ).click();

        Thread.sleep(1000);

        // 15. Confirm appointment
        driver.findElement(
                By.id("confirmButton")
        ).click();

        Thread.sleep(1000);

        // 16. Print appointment ID
        String appointmentId =
                driver.findElement(
                        By.id("bookingId")
                ).getText();

        System.out.println(
                "Appointment booked successfully!"
        );

        System.out.println(
                "Appointment ID: " + appointmentId
        );

        // Keep browser open for 5 seconds
        Thread.sleep(5000);

        driver.quit();
    }
}

```




```python
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;

public class hi {
    public static void main (String[] args) {
        WebDriver driver=new ChromeDriver();
        driver.get("https://demoqa.com/automation-practice-form");

        driver.findElement(By.id("firstName")).sendKeys("Mounesh");
        driver.findElement(By.id("lastName")).sendKeys("patil");
        driver.findElement(By.id("userEmail")).sendKeys("hi@gmail.com");
        driver.findElement(By.xpath("//label[text()='Male']")).click();
        driver.findElement(By.id("userNumber")).sendKeys("1234567890");
        driver.findElement(By.xpath("//label[text()='Sports']")).click();
        driver.findElement(By.id("uploadPicture")).sendKeys("C:\\Users\\gurup\\Downloads\\WhatsApp Image 2026-06-15 at 8.59.21 AM.jpeg");
        driver.findElement(By.id("currentAddress")).sendKeys("banglure,Karnatak");
        driver.findElement(By.tagName("body")).sendKeys(Keys.END);
        driver.findElement(By.id("submit")).sendKeys(Keys.ENTER);


    }
}

```




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


```python
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.apache.commons.io.FileUtils;

import java.io.File;

public class hi {

    public static void main(String[] args) throws Exception {

        WebDriver driver = new ChromeDriver();

        driver.get("https://www.google.com");

        // Take screenshot
        File src = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);

        // Save file
        FileUtils.copyFile(src, new File("C:\\Screenshots\\google.png"));

        System.out.println("Screenshot taken");

        driver.quit();
    }
}


```


```python

 <dependency>
            <groupId>commons-io</groupId>
            <artifactId>commons-io</artifactId>
            <version>2.16.1</version>
        </dependency>
```


