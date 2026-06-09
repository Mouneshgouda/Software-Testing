# Software Testing & Automation (23CS502) - Course Notes

[cite_start]Comprehensive study notes for the 5th-semester Software Testing course[cite: 1], covering core manual testing concepts, advanced UI automation with Selenium WebDriver, TestNG execution management, and enterprise Hybrid Framework architectures.

---

## 📋 Table of Contents
1. [Unit 1: Introduction to Automation Testing with Selenium](#unit-1-introduction-to-automation-testing-with-selenium)
2. [Unit 2: Working with Selenium & TestNG](#unit-2-working-with-selenium--testng)
3. [Unit 3: Testing Framework Design & Architecture](#unit-3-testing-framework-design--architecture)

---

## Unit 1: Introduction to Automation Testing with Selenium

### 1. Core Testing Concepts
* [cite_start]**What is Software Testing?** The process of evaluating and verifying that a software application operates exactly as intended by identifying defects, gaps, or missing business requirements[cite: 14].
* [cite_start]**Why Software Testing?** * **Cost-Effectiveness:** Finding and resolving bugs early in the Software Development Life Cycle (SDLC) costs significantly less than post-production hotfixes[cite: 14].
  * [cite_start]**Security:** Detects vulnerabilities and ensures user data integrity[cite: 14].
  * [cite_start]**Reliability & Satisfaction:** Builds trust by delivering a flawless user experience[cite: 14].

### 2. Software Test Levels
Testing is executed in progressive stages across the development lifecycle:
* [cite_start]**Unit Testing:** Isolating and testing individual components or blocks of code (e.g., methods, classes), typically performed by developers[cite: 14].
* [cite_start]**Integration Testing:** Verifying the data communication and interfaces between combined modules[cite: 14].
* [cite_start]**System Testing:** Black-box testing of the complete, fully integrated software system against specified business requirements[cite: 14].
* [cite_start]**Acceptance Testing:** Validating whether the software meets end-user business needs to determine deployment readiness (e.g., UAT)[cite: 10, 14].

### 3. Software Test Types
* [cite_start]**Functional Testing:** Validates **what** the system does against functional specifications (e.g., logins, checkout flows)[cite: 8, 14].
* [cite_start]**Non-Functional Testing:** Validates **how** the system performs under constraints (e.g., performance, load, security, and usability)[cite: 8, 14].
* [cite_start]**Change-Related Testing:** Re-running existing tests after code modifications to ensure updates haven't introduced new regressions or broken existing stability[cite: 14].

### 4. Test Scenario & Test Case Design
* [cite_start]**Test Scenario:** A high-level classification of a testable requirement (e.g., "Verify user login functionality")[cite: 15].
  * [cite_start]*Business Critical Scenarios:* Core pathways vital to business revenue or operations (e.g., payment processing gateways)[cite: 15].
* [cite_start]**Test Case:** A detailed document containing specific inputs, conditions, and execution setups[cite: 16].
  * [cite_start]*Core Components:* Pre-requisites, Explicit Test Steps, and Expected Results[cite: 16].
  * [cite_start]*Positive Testing:* Verifying correct behavior using valid input sets[cite: 16].
  * [cite_start]*Negative Testing:* Verifying graceful error-handling using invalid inputs[cite: 16].
* [cite_start]**Optimization Techniques:** Minimizing test counts while maintaining maximum coverage using strategies like *Boundary Value Analysis (BVA)* and *Equivalence Partitioning (EP)*[cite: 16].

### 5. Metrics & Documentation
* [cite_start]**RTM (Requirements Traceability Matrix):** A mapping grid correlating business requirements to corresponding test cases to verify 100% test coverage[cite: 17].
* [cite_start]**DSR (Daily Status Report):** A summary dashboard shared daily highlighting test execution status, defects found, and overall team progress[cite: 17].

### 6. Java Foundations for Automation
[cite_start]Building clean automation architectures requires robust Object-Oriented Programming (OOP) patterns[cite: 17]:
* [cite_start]**Inheritance & Polymorphism:** Facilitates code reuse (e.g., extending a `BaseClass` to inherit driver settings) and method overriding for flexible behaviors[cite: 17].
* [cite_start]**Exception Handling:** Managing runtime issues (`try-catch-finally`) to prevent test suites from crashing on dynamic elements[cite: 17].
* [cite_start]**Collections (List):** Essential for capturing multiple matching elements, such as storing a dynamic row array using `List<WebElement>`[cite: 17].
* [cite_start]**JDBC (Java Database Connectivity):** Used to perform programmatic **CRUD operations** (Create, Read, Update, Delete) to inject or validate data records directly inside target databases[cite: 17].

---

## Unit 2: Working with Selenium & TestNG

### 1. WebDriver Configuration & Navigation
* [cite_start]**Maven Configuration:** Managed through the `pom.xml` file to automatically pull, download, and update dependencies like Selenium WebDriver and testing utilities[cite: 20].
* **Core Browser Commands:**
  * [cite_start]`driver.get("URL")` - Directs the browser to a target webpage[cite: 20].
  * [cite_start]`driver.quit()` - Safely destroys all open browser windows and ends the WebDriver instance[cite: 20].
* [cite_start]**Navigation Control:** Scripting explicit historical steps using `driver.navigate().back()`, `.forward()`, and `.refresh()`[cite: 20].

### 2. Selenium Locators
[cite_start]Locators are strategies used to find and interact with elements on a webpage[cite: 20]:
* [cite_start]**Basic Locators:** Fast and direct targeting using `id` and `name` attributes[cite: 20].
* **Advanced Locators:**
  * [cite_start]**XPath:** Navigates the HTML DOM tree[cite: 20]. 
    * [cite_start]*Absolute XPath* (`/html/body/...`) is highly fragile[cite: 20].
    * [cite_start]*Relative XPath* (`//input[@id='val']`) focuses on local anchor attributes and is highly stable[cite: 20].
  * [cite_start]**CSS Selectors:** Fast query matching using CSS rules (e.g., `div.class-name > input#id`)[cite: 20].

### 3. Dynamic Elements & Advanced UI Mechanics
* **Synchronization (Waits):**
  * [cite_start]*Implicit Wait:* A global default wait instructing the driver to poll the DOM for a set duration before throwing errors[cite: 21].
  * [cite_start]*Explicit Wait:* A target-specific pause that waits for a distinct condition (e.g., `elementToBeClickable`) to become true[cite: 21].
* [cite_start]**Exceptions Management:** Handling operational faults like `NoSuchElementException` (element missing from DOM) or `StaleElementReferenceException` (element no longer attached due to page refresh)[cite: 20].
* **Advanced Handling Actions:**
  * [cite_start]**Actions Class:** Handles complex interactions like hover states, drag-and-drops, and double clicks[cite: 20].
  * [cite_start]**Alerts & Iframes:** Handling JavaScript pop-ups with `driver.switchTo().alert()` and shifting focus into isolated HTML blocks with `driver.switchTo().frame()`[cite: 20].
  * [cite_start]**JavaScript Execution:** Using `JavascriptExecutor` to force interactions on hidden elements or bypass standard click hurdles[cite: 20].
  * [cite_start]**WebTables & Calendars:** Traversing through `<tr>` and `<td>` grids dynamically to read rows or select specific dates[cite: 20].

### 4. TestNG Execution Engine
[cite_start]TestNG coordinates execution order and configuration setups[cite: 21]:
* [cite_start]**Annotations Framework:** Controls the exact execution workflow[cite: 21]:
  * [cite_start]`@BeforeMethod` / `@AfterMethod` - Runs before and after every individual test method[cite: 21].
  * [cite_start]`@Test` - Marks a method as an executable test case[cite: 21].
* [cite_start]**Key Features:** Supports test case prioritization, test data separation, parameterization, parallel processing, and automatic test report generation[cite: 21].

---

## Unit 3: Testing Framework Design & Architecture

### 1. Framework Patterns
* [cite_start]**Data-Driven Testing (Apache POI):** A separation strategy where test logic remains in Java classes while inputs are stored in external Excel workbooks[cite: 24]. [cite_start]The **Apache POI** library reads these external spreadsheets and pipes inputs directly into tests[cite: 24].
* [cite_start]**Page Object Model (POM):** A design pattern where each web page is represented by its own class file[cite: 24]. [cite_start]Elements and operational actions are self-contained in the class, meaning UI updates only require modifications in one place rather than across the entire test suite[cite: 24].

### 2. Rich Reporting & Media Attachments
* [cite_start]**Extent Reports:** An external reporting tool used to generate clean, readable HTML test dashboards[cite: 25].
* [cite_start]**Screenshots:** Programmatically capturing screen layouts during step failures using the `TakesScreenshot` interface and attaching them directly to the HTML report for faster debugging[cite: 25].

### 3. Log4j Engine
[cite_start]Log4j tracks real-time script operations, providing detailed execution records during automated pipeline runs[cite: 26].
* [cite_start]**Configuration:** Managed via a `log4j.properties` file to set layout formats and designate output destinations (e.g., console vs. `.log` files)[cite: 26].
* **The 7 Levels of Logging:**
  1. [cite_start]`ALL`: Activates complete logging details[cite: 26, 38].
  2. [cite_start]`TRACE`: Captures highly granular diagnostic steps[cite: 26, 38].
  3. [cite_start]`DEBUG`: Logs helpful technical details used during development[cite: 26, 38].
  4. [cite_start]`INFO`: Highlights standard operational progress (e.g., "Browser launched successfully")[cite: 26, 38].
  5. [cite_start]`WARN`: Flags unusual conditions that do not halt execution[cite: 26, 38].
  6. [cite_start]`ERROR`: Logs standard step failures or assertion errors[cite: 26, 38].
  7. [cite_start]`FATAL`: Logs catastrophic system crashes that cause execution to abort[cite: 26, 38].

### 4. Hybrid Framework Implementation
[cite_start]A **Hybrid Framework** combines multiple architectural designs—blending **Data-Driven Testing** (Apache POI) for input management and the **Page Object Model (POM)** for clean element mapping, alongside Log4j and Extent Reports[cite: 24, 25, 26].

#### Folder Structure Blueprint
```text
HybridAutomationFramework/
│
├── src/main/java/              # Core structural engines
│   ├── com/qa/base/BaseClass.java   # Driver setups & teardowns
│   ├── com/qa/pages/           # POM Page Classes (Elements & Actions)
│   └── com/qa/utils/           # Utility engines (Excel Reader, Listeners)
│
├── src/test/java/              # Execution layer
│   └── com/qa/tests/           # TestNG Test Files (@Test)
│
├── src/test/resources/         # Configuration layer
│   ├── log4j.properties        # Logger properties
│   └── testdata.xlsx           # External Data Sheets
│
├── pom.xml                     # Maven dependency manager
└── testng.xml                  # Execution suite manager
