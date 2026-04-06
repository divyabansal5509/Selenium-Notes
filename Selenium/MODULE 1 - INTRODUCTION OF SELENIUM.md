1️⃣ Introduction to Selenium Suite
Selenium is an open-source automation testing framework used to automate web applications for testing purposes.

🔹 Purpose
Automates repetitive browser actions

Helps perform functional testing

Enables cross-browser testing

Reduces manual testing effort

🔹 What Selenium Can Do
Open web pages

Click buttons and links

Enter text into input fields

Validate expected results

Navigate between pages

⚠️ Important: Selenium is mainly used for web application testing, not desktop applications.


2️⃣ What is Selenium?

Selenium is a suite of tools that allows testers to automate browser interactions.

⭐ Key Characteristics
Open Source → Free to use
Cross Browser Testing → Run tests on different browsers
Multi-Language Support → Write scripts in different languages
Cross Platform → Works on multiple operating systems
Highly Extensible → Integrates with tools like TestNG, Maven, Jenkins
🧠 Simple Example

Instead of manually testing login:

Manual Steps:

Open website
Enter username
Enter password
Click login
Verify dashboard

Selenium can automatically perform all these steps using scripts.

3️⃣ Components of Selenium Suite

The Selenium Suite consists of four main tools.

3.1 Selenium IDE (Integrated Development Environment)

Selenium IDE is a browser extension used for recording and playback of tests.

🔹 Features
Record user actions in browser
Playback recorded tests
No programming required
Useful for beginners and quick testing
🔹 Supported Browsers
Chrome
Firefox

⚠️ Limitation:
Not suitable for complex automation frameworks.

3.2 Selenium WebDriver

Selenium WebDriver is the core component of Selenium used for automation scripting.

It directly communicates with the browser using browser drivers.

🔹 Features
Supports multiple programming languages
Works with modern browsers
Faster than Selenium RC
Allows advanced automation
🔹 Supported Languages
Java
Python
C#
JavaScript
Ruby
PHP
🔹 Example (Java)
WebDriver driver = new ChromeDriver();
driver.get("https://www.google.com");

This script opens Google in Chrome browser.

3.3 Selenium Grid

Selenium Grid is used to execute tests on multiple machines and browsers simultaneously.

🔹 Purpose
Perform parallel testing
Run tests on different browsers
Reduce test execution time
🔹 Example

Test the same website on:

Chrome (Windows)
Firefox (Linux)
Safari (Mac)

All at the same time.

3.4 Selenium RC (Remote Control)

Selenium RC was the earlier Selenium automation tool before WebDriver.

🔹 How it Worked
Used a Selenium server
Injected JavaScript into browser
🔹 Limitations
Slow performance
Complex architecture
Less stable

⚠️ Note: Selenium RC was deprecated and replaced by WebDriver.

4️⃣ Evolution of Selenium (Selenium 1 → Selenium 4)

Selenium has evolved significantly to improve speed, compatibility, and functionality.

Selenium 1 (Selenium RC)

📅 Released: 2004

Features
First Selenium automation tool
Used JavaScript injection
Required Selenium server
Limitations
Slow execution
Browser security restrictions
Selenium 2 (WebDriver)

📅 Released: 2011

Major Improvement
Introduction of WebDriver
Features
Direct browser communication
Faster execution
Better stability
Supports modern browsers
Selenium 3

📅 Released: 2016

Improvements
Selenium RC completely removed
WebDriver became the main API
Better browser driver support
Architecture
Test Script → WebDriver → Browser Driver → Browser

Examples of Browser Drivers:

ChromeDriver
GeckoDriver
EdgeDriver
Selenium 4

📅 Released: 2021

Latest Selenium version with major improvements.

Key Features

✔ W3C Standard Protocol

Standard communication between browsers and Selenium.

✔ Improved Selenium Grid

New UI
Easier configuration

✔ Relative Locators

Locate elements based on their position.

Example:

driver.findElement(with(By.tagName("input")).above(password));

✔ Better DevTools Integration

Capture network logs
Monitor browser performance

✔ Improved Selenium IDE

5️⃣ Features of Selenium

Selenium provides several powerful features for automation testing.

5.1 Platform Support

Selenium supports multiple operating systems.

Supported Platforms
Windows
Linux
macOS

This allows tests to run across different environments.

5.2 Browser Support

Selenium supports most major web browsers.

Supported Browsers
Google Chrome
Mozilla Firefox
Microsoft Edge
Safari
Opera

This enables cross-browser testing.

5.3 Scripting Language Support

Selenium allows automation scripts in multiple programming languages.

Supported Languages
Java
Python
C#
JavaScript
Ruby
PHP

Example:

driver.findElement(By.id("username")).sendKeys("Divya");
5.4 Mobile Testing Support

Selenium can test mobile web applications.

However, for full mobile automation it works with:

➡ Appium

Supported Mobile Browsers
Chrome (Android)
Safari (iOS)
⚡ Quick Revision Summary

✔ Selenium = Open-source web automation framework
✔ Used for web application testing
✔ Selenium Suite Components:

Selenium IDE
Selenium WebDriver
Selenium Grid
Selenium RC (deprecated)

✔ Evolution:

Selenium 1 → RC
Selenium 2 → WebDriver
Selenium 3 → RC removed
Selenium 4 → W3C standard + new features

✔ Major Features:

Cross platform
Cross browser
Multi-language support
Mobile web testing with Appium



6️⃣ Selenium WebDriver

Selenium WebDriver is the main automation tool in the Selenium suite used to control web browsers through programming languages.

Key Points
Replaced Selenium RC
Interacts with browsers via browser drivers
Executes automation scripts
Supports real user-like browser interactions
Browser Drivers
Browser	Driver
Chrome	ChromeDriver
Firefox	GeckoDriver
Edge	EdgeDriver
Safari	SafariDriver
Basic Workflow
Test Script → WebDriver → Browser Driver → Browser
Example (Java)
WebDriver driver = new ChromeDriver();
driver.get("https://www.google.com");
7️⃣ Selenium Library (WebDriver API)

The Selenium Library (also called WebDriver API) is a collection of classes and methods used to write automation scripts.

It acts as the programming interface between the test script and browser.

Purpose
Control browser actions
Locate web elements
Perform interactions with elements
Manage browser sessions
Common WebDriver Methods
Method	Function
get()	Opens a webpage
findElement()	Locates a web element
click()	Clicks on element
sendKeys()	Enters text
close()	Closes current window
quit()	Ends browser session
8️⃣ Selenium Grid

Selenium Grid allows running test cases on multiple machines and browsers simultaneously.

It enables distributed test execution.

Key Idea

Execute tests in parallel across different environments.

Example environments:

Chrome on Windows
Firefox on Linux
Safari on macOS
Main Use Cases
Cross-browser testing
Cross-platform testing
Large test suite execution
9️⃣ Benefits of Selenium Grid

✔ Parallel Test Execution
Multiple test cases run at the same time.

✔ Reduced Testing Time
Parallel execution speeds up automation testing.

✔ Cross Browser Testing
Test application behavior across browsers.

✔ Cross Platform Testing
Run tests on different operating systems.

✔ Efficient Resource Usage
Multiple machines share test execution.

🔟 Grid (Hub–Node Architecture)

Selenium Grid follows a Hub–Node architecture.

Hub

The Hub is the central server that:

Receives test requests
Controls test distribution
Assigns tests to available nodes
Node

A Node is a machine connected to the Hub where tests are executed.

Each node can have:

Different browsers
Different operating systems
Execution Flow
Test Script
     │
     ▼
    Hub
     │
 ┌───┼─────────┐
 │   │         │
Node Node     Node
Chrome Firefox Edge
1️⃣1️⃣ Selenium IDE

Selenium IDE (Integrated Development Environment) is a browser extension used for recording and replaying test cases.

It is mainly used for basic automation and learning Selenium.

Key Features

✔ Record & Playback
Records browser actions automatically.

✔ Easy Test Creation
Quick automation without coding.

✔ Script Export
Recorded tests can be exported to programming languages.

✔ Debugging Support
Helps identify failures in recorded steps.

Supported Browsers
Chrome
Firefox
Basic Workflow
Install Selenium IDE extension
Start recording
Perform actions on website
IDE records steps
Replay the test case
Limitations
Not suitable for complex automation frameworks
Limited flexibility compared to WebDriver
⚡ **Quick Revision (Module 1 – Part 2)**

Selenium WebDriver

Core automation component
Controls browsers via drivers

Selenium Library

Collection of WebDriver classes and methods
Used to write automation scripts

Selenium Grid

Enables parallel and distributed test execution

Grid Architecture

Hub → central controller
Nodes → machines executing tests

Selenium IDE

Record and playback tool
Useful for beginners