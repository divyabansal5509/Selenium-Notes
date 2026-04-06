## **INTRODUCTION FOR WEBDRIVER ARCHITECTURE:**

### 1️⃣ Introduction to WebDriver Architecture:

WebDriver Architecture describes how Selenium WebDriver communicates with browsers to execute automation scripts.

**Core Idea:**

Automation scripts interact with WebDriver API, which then communicates with the browser driver to control the browser.

**Basic Flow**

Test Script ->
Selenium WebDriver API ->
Browser Driver->
Browser
Key Components

1. Test Script:

- Written using languages like Java, Python, C#
Contains automation logic

2. WebDriver API:

- Provides methods and commands to interact with browsers

3. Browser Driver:

- Acts as bridge between WebDriver and browser

**Examples:**

- ChromeDriver

- GeckoDriver

- EdgeDriver

4. Browser:

Executes the commands sent by WebDriver.


### 2️⃣ Features of WebDriver

Major Features:

✔ Direct Browser Communication :

No intermediate server required.

✔ Cross-Browser Support:

Works with Chrome, Firefox, Edge, Safari.

✔ Multiple Language Support:

Supports Java, Python, C#, JavaScript, Ruby.

✔ Platform Independent:

Runs on Windows, Linux, and macOS.

✔ Real User Interaction:

Simulates actual browser behavior.

✔ Better Performance:

Faster compared to older Selenium tools.

### 3️⃣ Maven Project with Dependencies

Maven is a build automation and dependency management tool mainly used for Java projects.

In Selenium projects, Maven helps to:

Automatically download required libraries
Manage project dependencies
Maintain consistent project structure

**Advantages of Maven in Selenium:**

✔ Automatic dependency management

✔ Easy project configuration

✔ Simplified build process

✔ Integration with testing tools (TestNG, JUnit)


### 4️⃣ Overview of Maven Project Structure

A standard Maven project follows a predefined directory structure.

ProjectName
│
├── src
│   ├── main
│   │   └── java
│   │
│   └── test
│       └── java
│
├── pom.xml
│
└── target

**Important Folders:**

- src/main/java : Application source code

- src/test/javaTest : automation scripts

- pom.xml : Main configuration file

- target : Stores compiled files and build outputs

### 5️⃣ Maven Repository (3 Types)

A Maven Repository stores all project dependencies and libraries.

**1️) Local Repository:**
Located on developer's system
Stores downloaded dependencies locally

**Example path:**

C:\Users\Username\.m2\repository

**2️) Central Repository:**
Official Maven repository
Available online

**Example:**

https://mvnrepository.com

*Used to download:*

Selenium libraries
TestNG
Other dependencies

**3️) Remote Repository**
Hosted on company servers
Used in large organizations

**Purpose:**
Share project libraries across teams

### 6️⃣ Overview of pom.xml

- POM stands for Project Object Model.

- pom.xml is the main configuration file of a Maven project.

- Responsibilities
- Defines project information
- Manages dependencies
- Configures plugins
- Controls build process

All required libraries for Selenium are added in pom.xml.

### 7️⃣ pom.xml Components


**1️) Project Information**

Contains basic project details.

**Example:**

<groupId>com.selenium</groupId>
<artifactId>automation-project</artifactId>
<version>1.0</version>

**2️) Dependencies**

Defines external libraries needed for the project.

**Example:**

<dependencies>

<dependency>
<groupId>org.seleniumhq.selenium</groupId>
<artifactId>selenium-java</artifactId>
<version>4.20.0</version>
</dependency>

</dependencies>

Purpose:
Automatically download Selenium libraries.

**3️) Plugins**

Plugins are used to extend Maven functionality.

Example:

Compiler plugin
Test execution plugin
### 8️⃣ Demo: Create a Simple Maven Project (Selenium + TestNG)

**Step 1:** Create Maven Project

In IDE (Eclipse / IntelliJ):

File → New → Maven Project

Select quickstart archetype.

**Step 2:** Add Selenium Dependency

Add in pom.xml:

<dependency>
<groupId>org.seleniumhq.selenium</groupId>
<artifactId>selenium-java</artifactId>
<version>4.20.0</version>
</dependency>
**Step 3:**  Add TestNG Dependency
<dependency>
<groupId>org.testng</groupId>
<artifactId>testng</artifactId>
<version>7.9.0</version>
<scope>test</scope>
</dependency>
**Step 4:**  Update Maven Project

In IDE:

Right Click Project → Maven → Update Project

This downloads required libraries.

### 9️⃣ Steps for Software Configuration (Maven Project)
Required Software

1️) Java JDK

Install JDK
Set JAVA_HOME

2️) IDE

**Common IDEs:**

Eclipse
IntelliJ IDEA

3️) Maven

Install Maven
Configure Maven home

**Verify installation:**

mvn -version

4️) Browser Drivers

Download required drivers:

ChromeDriver

GeckoDriver

EdgeDriver

Add drivers to system path or project folder.

## 1️⃣ Web Automation with WebDriver and TestNG

- Web Automation refers to automatically performing actions on web applications using Selenium scripts.

- When combined with TestNG, Selenium provides a structured test execution framework.

**Role of WebDriver:**

- Automates browser interactions
- Executes test scripts
- Performs user actions (click, type, navigate)

**Role of TestNG**
- Test execution management
- Annotations for test control
- Test reporting
- Parallel execution support

**Basic Workflow:**
TestNG Test Script
       ->
Selenium WebDriver
       ->
Browser Driver
       ->
Browser Execution

## Example (TestNG + Selenium)
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class DemoTest {

@Test
public void openGoogle() {

WebDriver driver = new ChromeDriver();
driver.get("https://www.google.com");

}
}

## 2️⃣ Browser Control (Browser Instantiation)

Browser Instantiation means launching a browser using WebDriver driver classes.

Each browser requires its specific driver class.

### **Driver Classes**
**Browser**	**Driver Class**

Chrome	->    ChromeDriver

Firefox	->FirefoxDriver

Edge	      ->EdgeDriver

### Instantiating a Browser
WebDriver driver = new ChromeDriver();

This command:

- Creates a WebDriver object
Launches the Chrome browser

## 3️⃣ Demo: Executing Selenium Test Scripts in Different Browsers

Selenium allows running the same script on multiple browsers by changing the driver.

Chrome Browser:

WebDriver driver = new ChromeDriver();
driver.get("https://www.google.com");

Firefox Browser:

WebDriver driver = new FirefoxDriver();
driver.get("https://www.google.com");

Edge Browser:

WebDriver driver = new EdgeDriver();
driver.get("https://www.google.com");

**Important Concept:**

- Same automation logic → Different browsers

- Only the driver initialization changes.

- This enables Cross-Browser Testing.

## 4️⃣ Browser Utility Class

A Browser Utility Class is a custom helper class that contains reusable browser-related methods.

**Purpose:**

- Avoid writing the same browser setup code repeatedly
- Improve code reusability
- Simplify test scripts

**Common Methods in Browser Utility Class:**

- Launch browser
- Maximize window
- Open URL
- Close browser

**Example Browser Utility Class:**

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserUtility {

public static WebDriver launchBrowser() {

WebDriver driver = new ChromeDriver();
driver.manage().window().maximize();

return driver;

}

}

## 5️⃣ Use of Browser Utility Class

Instead of creating a driver object in every test class, we can **reuse the utility method.**

**Example Test Script**

import org.openqa.selenium.WebDriver;
import org.testng.annotations.Test;

public class TestExample {

@Test
public void openSite() {

WebDriver driver = BrowserUtility.launchBrowser();
driver.get("https://www.google.com");

}

}
### **Advantages:**

✔ Reduces duplicate code

✔ Improves maintainability

✔ Easier browser management

✔ Better framework structure

### **⚡ Quick Revision — Module 2 (WebDriver Architecture):**

**Web Automation with WebDriver + TestNG:**
- WebDriver → browser automation
- TestNG → test execution framework

**Browser Instantiation:**
- Launch browser using driver classes
- Example: ChromeDriver, FirefoxDriver, EdgeDriver

**Cross-Browser Execution:**
- Same script can run on different browsers
- Only driver initialization changes

**Browser Utility Class:**
- Custom class for reusable browser setup methods
- Improves code reuse and framework design

**Maven in Selenium:**
- Manages dependencies and project build
- Uses pom.xml configuration

**Maven Repositories:**
- Local repository
- Central repository
- Remote repository


