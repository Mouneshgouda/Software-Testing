## config.propertes

```python
browser=chrome

url=https://mouneshgouda.github.io/busBooking/

from=Bangalore
to=Mumbai
date=08/10/2026

bus=Green Line Travels

name=Mounesh
age=25
phone=9876543210
seat=A1

```
## utils/ConfigReader
```python

package utils;

import java.io.FileInputStream;
import java.util.Properties;

public class ConfigReader {
    static Properties p = new Properties();
    static {
        try {
            p.load(new FileInputStream(
                    "src/test/resources/config.properties"));
        }
        catch(Exception e){
            e.printStackTrace();
        }
    }
    public static String get(String key){

        return p.getProperty(key);

    }

}

```

## base/BaseTest

```python

package base;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import utils.ConfigReader;
public class BaseTest {
    public static WebDriver driver;
    public void setup() throws Exception {
        driver = new ChromeDriver();
        driver.manage().window().maximize();
        Thread.sleep(2000);
        driver.get(ConfigReader.get("url"));
        Thread.sleep(3000);
    }
    public void close(){
        driver.quit();

    }
}


```

## pages

### BusPage

```python

package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class BusPage {

    WebDriver driver;

    public BusPage(WebDriver driver) {
        this.driver = driver;
    }

    public void selectBus(String busName) {

        driver.findElement(
                By.xpath("//tr[td='" + busName + "']//button")
        ).click();

    }
}

```

### ConfirmationPage

```python
package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class ConfirmationPage {

    WebDriver driver;

    public ConfirmationPage(WebDriver driver) {
        this.driver = driver;
    }

    public boolean verifyBooking(){

        return driver.findElement(
                By.xpath("//h1[contains(text(),'Booking Confirmed')]")
        ).isDisplayed();

    }

    }


```

### HomePage

```python
package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.support.ui.Select;

public class HomePage {

    WebDriver driver;

    public HomePage(WebDriver driver) {
        this.driver = driver;
    }


    public void searchBus(String from, String to, String date) {

        Select fromSelect = new Select(driver.findElement(By.id("from")));
        fromSelect.selectByVisibleText(from);

        Select toSelect = new Select(driver.findElement(By.id("to")));

        toSelect.selectByVisibleText(to);

        driver.findElement(By.id("date")).sendKeys(date);

        // Click search button
        driver.findElement(
                By.xpath("//button[contains(text(),'Search Bus')]")
        ).click();


    }

}

```

### PassengerPage

```python
package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class PassengerPage {

    WebDriver driver;

    public PassengerPage(WebDriver driver) {
        this.driver = driver;
    }

    public void enterDetails(String name, String age, String phone, String seat) {

        driver.findElement(By.id("name")).sendKeys(name);
        driver.findElement(By.id("age")).sendKeys(age);
        driver.findElement(By.id("phone")).sendKeys(phone);
        driver.findElement(By.id("seat")).sendKeys(seat);

    }


    public void confirmBooking() {

        driver.findElement(
                By.xpath("//button[contains(text(),'Book')]")
        ).click();

    }
}

```

## tests 
### BaseTest


```python
package tests;

import org.testng.Assert;
import org.testng.annotations.*;

import base.BaseTest;
import pages.*;
import utils.ConfigReader;

public class BookingTest extends BaseTest {

    @BeforeMethod
    public void start() throws Exception {
        setup();
    }

    @Test
    public void bookingTest() {

        // Step 1: Search Bus
        HomePage home = new HomePage(driver);

        home.searchBus(
                ConfigReader.get("from"),
                ConfigReader.get("to"),
                ConfigReader.get("date")
        );

        // Step 2: Select Bus
        BusPage bus = new BusPage(driver);

        bus.selectBus(
                ConfigReader.get("bus")
        );
        // Step 3: Enter Passenger Details
        PassengerPage passenger = new PassengerPage(driver);

        passenger.enterDetails(
                ConfigReader.get("name"),
                ConfigReader.get("age"),
                ConfigReader.get("phone"),
                ConfigReader.get("seat")
        );

        // Step 4: Click Book/Confirm Button
        passenger.confirmBooking();
    }


    @AfterMethod
    public void end() {
        close();
    }
}
```




