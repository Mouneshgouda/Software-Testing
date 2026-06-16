# Selenium Automation: Understanding Similar Questions

## Question 1

### Create an automation script with Selenium to interact with specific web elements on a designed web page.

### Meaning

This question asks us to create a Selenium script that interacts with various web elements such as:

- Text boxes
- Buttons
- Radio buttons
- Checkboxes
- Dropdown lists
- File upload controls
- Text areas
- Links

---

## Question 2

### How to write automation scripts in Selenium to handle form elements on a given website?

### Meaning

This question specifically focuses on handling form elements such as:

- Text fields
- Password fields
- Radio buttons
- Checkboxes
- Dropdown menus
- Text areas
- File upload controls
- Submit buttons

---

# Are Both Questions the Same?

**Yes.**

The second question is a subset of the first because **form elements are themselves web elements**.

Therefore, a Selenium script that handles form elements also interacts with web elements.

import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;

public class hi {
    public static void main(String[] args) {

        WebDriver driver = new ChromeDriver();
        driver.get("https://demoqa.com/automation-practice-form");

        WebElement firstNameTxt = driver.findElement(By.id("firstName"));
        firstNameTxt.sendKeys("Mounesh");

        WebElement lastNameTxt = driver.findElement(By.id("lastName"));
        lastNameTxt.sendKeys("Patil");

        WebElement emailTxt = driver.findElement(By.id("userEmail"));
        emailTxt.sendKeys("hi@gmail.com");

        WebElement maleRadioBtn = driver.findElement(By.xpath("//label[text()='Male']"));
        maleRadioBtn.click();

        WebElement mobileNumberTxt = driver.findElement(By.id("userNumber"));
        mobileNumberTxt.sendKeys("1234567890");

        WebElement sportsCheckbox = driver.findElement(By.xpath("//label[text()='Sports']"));
        sportsCheckbox.click();

        WebElement uploadPictureBtn = driver.findElement(By.id("uploadPicture"));
        uploadPictureBtn.sendKeys(
                "C:\\Users\\gurup\\Downloads\\WhatsApp Image 2026-06-15 at 8.59.21 AM.jpeg");

        WebElement currentAddressTxt = driver.findElement(By.id("currentAddress"));
        currentAddressTxt.sendKeys("Bangalore, Karnataka");

    }
}

---
