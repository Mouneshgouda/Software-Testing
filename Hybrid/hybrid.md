# Hybrid Framework in Selenium

A **Hybrid Framework** in Selenium is an automation design pattern that **combines two or more testing approaches**—most commonly:

* **Data-Driven Framework:** Keeps test data (like usernames, passwords, and URLs) in external files (Excel, CSV, JSON).
* **Keyword-Driven Framework:** Uses simple keywords (like `CLICK`, `TYPE`, `OPEN_BROWSER`) to represent actions.
* **Page Object Model (POM):** Stores web element addresses (XPath, ID, CSS Selectors) in central object repository classes.

By combining these approaches, the framework completely separates **Test Logic**, **Test Data**, **Element Locators**, and **Action Keywords**.

---
## 🌟 Key Benefits

* **Easy Maintenance:** UI locator changes are updated in **one central place**, preventing changes across multiple test scripts.
* **High Reusability:** Core action methods are written once and reused across hundreds of test cases.
* **Non-Coder Accessible:** Manual testers can build test scenarios by specifying keywords and data in Excel.
* **Rich Reporting:** Provides detailed execution reports with status traces and automatic failure screenshots.
