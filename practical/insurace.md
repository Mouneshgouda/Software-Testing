```python
untitled3
└── src
    └── main
        └── java
            ├── base
            │   └── BaseTest.java
            ├── pages
            │   ├── HomePage.java
            │   ├── InsurancePage.java
            │   ├── PlanPage.java
            │   ├── DetailsPage.java
            │   └── ConfirmationPage.java
            └── tests
                └── InsuranceTest.java


```



## windown cmds
```python

mkdir src\main\java\base
mkdir src\main\java\pages
mkdir src\main\java\tests

type nul > src\main\java\base\BaseTest.java
type nul > src\main\java\pages\HomePage.java
type nul > src\main\java\pages\InsurancePage.java
type nul > src\main\java\pages\PlanPage.java
type nul > src\main\java\pages\DetailsPage.java
type nul > src\main\java\pages\ConfirmationPage.java
type nul > src\main\java\tests\InsuranceTest.java


```

## mac
```python

mkdir src\main\java\base
mkdir src\main\java\pages
mkdir src\main\java\tests

New-Item src\main\java\base\BaseTest.java -ItemType File
New-Item src\main\java\pages\HomePage.java -ItemType File
New-Item src\main\java\pages\InsurancePage.java -ItemType File
New-Item src\main\java\pages\PlanPage.java -ItemType File
New-Item src\main\java\pages\DetailsPage.java -ItemType File
New-Item src\main\java\pages\ConfirmationPage.java -ItemType File
New-Item src\main\java\tests\InsuranceTest.java -ItemType File



```


## BaseTest.java
```python

package tests;

import base.BaseTest;
import pages.ConfirmationPage;
import pages.DetailsPage;
import pages.HomePage;
import pages.InsurancePage;
import pages.PlanPage;

import org.testng.Assert;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;

public class InsuranceTest extends BaseTest {

    // Before Test
    @BeforeMethod
    public void beforeTest() {
        setup();
        System.out.println("Browser opened");
    }

    // Test Case
    @Test
    public void getCarInsuranceQuote() throws InterruptedException {

        System.out.println("Test Case: Verify Car Insurance Quote");

        // Create Page Objects
        HomePage homePage = new HomePage(driver);
        InsurancePage insurancePage = new InsurancePage(driver);
        PlanPage planPage = new PlanPage(driver);
        DetailsPage detailsPage = new DetailsPage(driver);
        ConfirmationPage confirmationPage =
                new ConfirmationPage(driver);

        // Step 1: Get Quote
        homePage.clickGetQuote();
        homePage.scrollDown();

        // Step 2: Select Car Insurance
        insurancePage.selectCar();
        insurancePage.clickNext();

        // Step 3: Select Standard Plan
        planPage.selectStandard();
        planPage.clickNext();

        // Step 4: Enter Details
        detailsPage.enterDetails();
        detailsPage.clickNext();

        // Step 5: Confirm
        confirmationPage.clickConfirm();

        // Step 6: Verify Success Message
        String message =
                confirmationPage.getSuccessMessage();

        System.out.println("Message: " + message);


    }

    // After Test
    @AfterMethod
    public void afterTest() {
        tearDown();
        System.out.println("Browser closed");
    }
}



```


## pages/Homepage
```python
package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;

public class HomePage {

    WebDriver driver;

    By getQuoteButton = By.className("primary-btn");

    public HomePage(WebDriver driver) {
        this.driver = driver;
    }

    public void clickGetQuote() throws InterruptedException {

        Thread.sleep(1000);

        driver.findElement(getQuoteButton).click();

        Thread.sleep(1000);
    }

    public void scrollDown() throws InterruptedException {

        ((JavascriptExecutor) driver).executeScript(
                "window.scrollTo(0, 500);"
        );

        Thread.sleep(500);
    }
}



```
