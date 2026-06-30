
```python
import org.testng.annotations.Test;

public class hi{

    @Test
    public void loginTest() {
        System.out.println("Login Successful");
    }
}
```

## order 

```python
import org.testng.annotations.Test;

public class hi {

    @Test
    public void login() {
        System.out.println("Login Successful");
    }

    @Test(dependsOnMethods = "login")
    public void orderProduct() {
        System.out.println("Product Ordered");
    }
}
```

```python


import org.testng.Assert;
import org.testng.annotations.Test;

public class hello {

    @Test(priority = 1)
    public void testAddition() {

        int result = 10 + 20;

        Assert.assertEquals(result, 30);

        System.out.println("Addition Test Passed");
    }

    @Test(priority = 2)
    public void testSubtraction() {

        int result = 20 - 10;

        Assert.assertEquals(result, 10);

        System.out.println("Subtraction Test Passed");
    }
}


```
# xml Test

```python
 <dependencies>

        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-java</artifactId>
            <version>4.33.0</version>
        </dependency>

        <dependency>
            <groupId>org.testng</groupId>
            <artifactId>testng</artifactId>
            <version>7.11.0</version>
        </dependency>

    </dependencies>


```


## Assert

```python

import org.testng.Assert;
import org.testng.annotations.Test;

public class AssertDemo {

    @Test
    public void verifyTitle() {

        String actual = "Google";
        String expected = "Google";

        Assert.assertEquals(actual, expected);
    }
}

```

## TestNg selunium
https://www.saucedemo.com/?utm_source=chatgpt.com

```python
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.Test;

public class hi {

    @Test
    public void login() {

        WebDriver driver = new ChromeDriver();

        driver.get("https://www.saucedemo.com");

        driver.findElement(By.id("user-name"))
                .sendKeys("standard_user");

        driver.findElement(By.id("password"))
                .sendKeys("secret_se");

        driver.findElement(By.id("login-button"))
                .click();

        String currentUrl = driver.getCurrentUrl();

        Assert.assertTrue(currentUrl.contains("inventory"),
                "Login failed!");

        System.out.println("Login Successful");

        driver.quit();
    }
}
```


```python

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.Test;

public class hi {

    @Test
    public void completeOrderTest() throws InterruptedException {

        WebDriver driver = new ChromeDriver();

        driver.get("https://www.saucedemo.com/");
        Thread.sleep(2000);

        // Login
        driver.findElement(By.id("user-name")).sendKeys("standard_user");
        driver.findElement(By.id("password")).sendKeys("secret_sauce");
        driver.findElement(By.id("login-button")).click();
        Thread.sleep(2000);

        // Add to cart
        driver.findElement(By.id("add-to-cart-sauce-labs-backpack")).click();
        Thread.sleep(2000);

        // Go to cart
        driver.findElement(By.className("shopping_cart_link")).click();
        Thread.sleep(2000);

        // Checkout
        driver.findElement(By.id("checkout")).click();
        Thread.sleep(2000);

        // Details
        driver.findElement(By.id("first-name")).sendKeys("John");
        driver.findElement(By.id("last-name")).sendKeys("Doe");
        driver.findElement(By.id("postal-code")).sendKeys("600001");
        Thread.sleep(2000);

        driver.findElement(By.id("continue")).click();
        Thread.sleep(2000);

        // Finish
        driver.findElement(By.id("finish")).click();
        Thread.sleep(2000);

        // Validate
        String msg = driver.findElement(By.className("complete-header")).getText();

        Assert.assertEquals(msg, "Thank you for your order!");

        System.out.println("Order Placed Successfully");

        driver.quit();
    }
}
```

# practical 5
``` python
import org.apache.logging.log4j.core.config.Configurator;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;
import org.apache.logging.log4j.Level;
import org.apache.logging.log4j.Logger;
import org.apache.logging.log4j.LogManager;

public class hello {

    static Logger log = LogManager.getLogger(hello.class);

    @Test
    public void game() throws InterruptedException {

        log.info("opening web");
        WebDriver driver = new ChromeDriver();

        driver.get("https://play2048.co");

        // Wait for page to load
        Thread.sleep(2000);

        log.debug("starting game interaction");

        log.trace("moving up");
        driver.findElement(By.tagName("body")).sendKeys(Keys.ARROW_UP);
        Thread.sleep(1000);

        log.trace("moving left");
        driver.findElement(By.tagName("body")).sendKeys(Keys.ARROW_LEFT);
        Thread.sleep(1000);

        log.trace("moving right");
        driver.findElement(By.tagName("body")).sendKeys(Keys.ARROW_RIGHT);
        Thread.sleep(1000);

        log.trace("moving down");
        driver.findElement(By.tagName("body")).sendKeys(Keys.ARROW_DOWN);
        Thread.sleep(1000);

        log.warn("here is some warning");
        log.fatal("major issues");
        log.error("small issues");

        Thread.sleep(3000); // Keep browser open for 3 seconds

        Configurator.setRootLevel(Level.OFF);
        driver.quit();
    }
}
```
