## Hotel booking

https://mouneshgouda.github.io/HotelBooking/index.html


### Project Structure

```text
├── src
│   ├── main
│   │   ├── java
│   │   │   ├──
│   │   │   ├── pages
│   │   │   │   ├── BookingPage.java
│   │   │   │   ├── HistoryPage.java
│   │   │   │   ├── HomePage.java
│   │   │   │   └── RoomsPage.java
│   │   │   └── tests
│   │   │       └── HotelTest.java




```
## Folder Cmds

```python
mkdir src\main\java\pages
mkdir src\main\java\tests


```

```python

type nul > src\main\java\pages\BookingPage.java
type nul > src\main\java\pages\HistoryPage.java
type nul > src\main\java\pages\HomePage.java
type nul > src\main\java\pages\RoomsPage.java
type nul > src\main\java\tests\HotelTest.java
```



## Mac Cmds

```python
mkdir -p src/main/java/pages
mkdir -p src/main/java/tests



```

```python

touch src/main/java/pages/BookingPage.java
touch src/main/java/pages/HistoryPage.java
touch src/main/java/pages/HomePage.java
touch src/main/java/pages/RoomsPage.java
touch src/main/java/tests/HotelTest.java
```
## HomePage

```python

package pages;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.By;

public class HomePage {
    WebDriver driver;
    public HomePage(WebDriver driver){
        this.driver=driver;
    }
    public void openWebpage(){
        driver.get("https://mouneshgouda.github.io/Hotel-Booking/");
    }
    public void searchRoom(String checkIn,String checkOut,String guests){
        driver.findElement(By.id("checkIn")).sendKeys(checkIn);
        driver.findElement(By.id("checkOut")).sendKeys(checkOut);
        driver.findElement(By.id("guests")).sendKeys(guests);
        driver.findElement(By.id("searchRooms")).click();
    }
}

```
