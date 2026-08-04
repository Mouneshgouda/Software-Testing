# 🚌 Bus Booking Automation Framework

This project demonstrates a **Hybrid Selenium Automation Framework** using **Java, Maven, TestNG, and Page Object Model (POM)** to automate a bus booking application.

---

## 📥 Download Source Code

Click below to download the original bus booking website source code:

[Demo url] (https://james-muriithi.github.io/bus/index.html)




[Download ZIP](https://github.com/james-muriithi/bus)

# 📁 Project Structure

```text
BusBookingAutomation
│
├── pom.xml
│
├── src
│   │
│   ├── main
│   │   └── java
│   │       │
│   │       ├── base  (create Package)
│   │       │    └── BaseTest.java
│   │       │
│   │       ├── pages  ( (create Package)
│   │       │    ├── HomePage.java
│   │       │    ├── BusPage.java
│   │       │    ├── SeatPage.java
│   │       │    ├── PassengerPage.java
│   │       │    └── PaymentPage.java
│   │       │
│   │       └── utils  (create Package)
│   │            └── ConfigReader.java
│   │
│   └── test
│       │
│       ├── java
│       │    └── tests  (create Package)
│       │         └── BookingTest.java  
│       │
│       └── resources  (create Directory)
│            └── config.properties
```

---

# 📂 Create Project Folders

## 🪟 Windows

```bat
mkdir src\main\java\base
mkdir src\main\java\pages
mkdir src\test\java\tests
mkdir src\main\java\utils
mkdir src\test\resources
```

## 🍎 macOS / 🐧 Linux

```bash
mkdir -p src/main/java/base
mkdir -p src/main/java/pages
mkdir -p src/test/java/tests
mkdir -p src/main/java/utils
mkdir -p src/test/resources
```

---

# 📄 Create Project Files

## 🪟 Windows

```bat
type nul > src\main\java\base\BaseTest.java

type nul > src\main\java\pages\HomePage.java
type nul > src\main\java\pages\BusPage.java
type nul > src\main\java\pages\SeatPage.java
type nul > src\main\java\pages\PassengerPage.java
type nul > src\main\java\pages\PaymentPage.java

type nul > src\test\java\tests\BookingTest.java

type nul > src\main\java\utils\ConfigReader.java

type nul > src\test\resources\config.properties
```

## 🍎 macOS / 🐧 Linux

```bash
touch src/main/java/base/BaseTest.java

touch src/main/java/pages/HomePage.java
touch src/main/java/pages/BusPage.java
touch src/main/java/pages/SeatPage.java
touch src/main/java/pages/PassengerPage.java
touch src/main/java/pages/PaymentPage.java

touch src/test/java/tests/BookingTest.java

touch src/main/java/utils/ConfigReader.java

touch src/test/resources/config.properties
```

## Config.Properties
```python

url=file:///C:/Users/LENOVO/Downloads/bus-CU/bus-CU/index.html

fromLocation=1
travelDate=2026-08-15

name=Guru Patil
idNumber=12345678
phone=0712345678
email=guru@gmail.com
```


## ConfigRedaer


```python
package utils;

import java.io.FileInputStream;
import java.util.Properties;

public class ConfigReader {

    static Properties p=new Properties();

    static  {
        try{
            p.load(new FileInputStream("src\\main\\resources\\config.properties"));
        }
        catch (Exception e){
            e.printStackTrace();

        }
    }
    public static  String get(String key){
        return p.getProperty(key);
    }

    }

```


## base/BaseTest.java

```python
package base;


import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import utils.ConfigReader;


public class BaseTest {


    protected WebDriver driver;



    public void setup(){


        driver = new ChromeDriver();


        driver.manage()
                .window()
                .maximize();



        driver.get(
                ConfigReader.get("url")
        );


    }



    public void close(){

        driver.quit();

    }


}

```
