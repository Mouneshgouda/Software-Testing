# Hybrid Framework in Selenium

A **Hybrid Framework** in Selenium is an automation design pattern that **combines two or more testing approaches**—most commonly:

* **Data-Driven Framework:** Keeps test data (like usernames, passwords, and URLs) in external files (Excel, CSV, JSON).
* **Keyword-Driven Framework:** Uses simple keywords (like `CLICK`, `TYPE`, `OPEN_BROWSER`) to represent actions.
* **Page Object Model (POM):** Stores web element addresses (XPath, ID, CSS Selectors) in central object repository classes.

By combining these approaches, the framework completely separates **Test Logic**, **Test Data**, **Element Locators**, and **Action Keywords**.

---

## 🏗️ Core Architecture & Components

A standard Hybrid Framework consists of 4 main layers:

### 1. Data Engine (Excel / CSV / JSON)
* Stores test execution steps, action keywords, and input data.
* Allows manual testers to create and update test cases without modifying code.

### 2. Driver Engine
* The core controller script.
* Reads the data file row by row, parses keywords and data, and triggers the corresponding action methods.

### 3. Object Repository (Page Object Model)
* Stores all web element locators in dedicated Page classes or `.properties` files.
* Prevents broken test scripts across the entire suite when UI elements change.

### 4. Reusable Action & Utility Library
* Contains modular methods for common Selenium operations (`clickElement`, `typeText`, `waitForElement`, `captureScreenshot`).
* Integrates reporting tools like ExtentReports or Log4j for automated status logging.

---

## 🔄 Step-by-Step Execution Flow

1. **Read Test Step:** Driver Engine reads a line from the Excel sheet (e.g., `Action = TYPE`, `Target = txt_Username`, `Value = admin@test.com`).
2. **Fetch Locator:** Engine looks up `txt_Username` in the Object Repository to get its locator (e.g., `By.id("user-email")`).
3. **Execute Action:** Engine calls the Action Library method to enter `admin@test.com` into `By.id("user-email")`.
4. **Log Result:** Status (`PASS` / `FAIL`) is logged in the test report along with timestamps and failure screenshots.

---

## 🌟 Key Benefits

* **Easy Maintenance:** UI locator changes are updated in **one central place**, preventing changes across multiple test scripts.
* **High Reusability:** Core action methods are written once and reused across hundreds of test cases.
* **Non-Coder Accessible:** Manual testers can build test scenarios by specifying keywords and data in Excel.
* **Rich Reporting:** Provides detailed execution reports with status traces and automatic failure screenshots.
