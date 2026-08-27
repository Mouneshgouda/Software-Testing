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
package base;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BaseTest {

    protected WebDriver driver;

    public void setup() {

        driver = new ChromeDriver();

        driver.manage().window().maximize();

        driver.get(
                "file:///C:/Users/gurup/OneDrive/Documents/insurence/index.html"
        );
    }

    public void tearDown() {

        driver.quit();
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

    public HomePage(WebDriver driver) {
        this.driver = driver;
    }

    public void clickGetQuote() throws InterruptedException {

        Thread.sleep(1000);

        driver.findElement(By.className("primary-btn")).click();

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
## InsurancePage
```python
package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class InsurancePage {

    WebDriver driver;

    public InsurancePage(WebDriver driver) {
        this.driver = driver;
    }

    public void selectCar() throws InterruptedException {

        driver.findElement(
                By.cssSelector(".insurance[data-type='Car']")
        ).click();

        Thread.sleep(500);
    }

    public void clickNext() throws InterruptedException {

        driver.findElement(By.id("nextBtn")).click();

        Thread.sleep(1000);
    }
}

```
## PlanPage

```python

package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class PlanPage {

    WebDriver driver;

    public PlanPage(WebDriver driver) {
        this.driver = driver;
    }

    public void selectStandard() throws InterruptedException {

        driver.findElement(
                By.cssSelector(".plan[data-plan='Standard']")
        ).click();

        Thread.sleep(500);
    }

    public void clickNext() throws InterruptedException {

        driver.findElement(By.id("nextBtn")).click();

        Thread.sleep(1000);
    }
}

```
## DetailsPage

```python
package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class DetailsPage {

    WebDriver driver;

    public DetailsPage(WebDriver driver) {
        this.driver = driver;
    }

    public void enterDetails() throws InterruptedException {

        driver.findElement(By.id("firstName")).sendKeys("John");
        driver.findElement(By.id("lastName")).sendKeys("Smith");
        driver.findElement(By.id("email")).sendKeys("john@gmail.com");
        driver.findElement(By.id("age")).sendKeys("30");

        Thread.sleep(500);
    }

    public void clickNext() throws InterruptedException {

        driver.findElement(By.id("nextBtn")).click();

        Thread.sleep(1000);
    }
}

```

## ConfirmationPage


```python

package pages;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class ConfirmationPage {

    WebDriver driver;

    public ConfirmationPage(WebDriver driver) {
        this.driver = driver;
    }

    public void clickConfirm() throws InterruptedException {
        driver.findElement(By.id("nextBtn")).click();
        Thread.sleep(1000);
    }

    public String getSuccessMessage() {
        return driver.findElement(By.cssSelector(".success h2")).getText();
    }
}
```
