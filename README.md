# Internshala Automation

A Selenium-based Java automation project for testing the Internshala login and internship workflow using Maven, TestNG, and ChromeDriver.

## Overview

This project automates common user actions on Internshala, such as:

- Opening the Internshala website
- Logging in as a student
- Navigating to internships
- Searching for internship categories
- Applying to an internship (when enabled)
- Logging out of the account

## Tech Stack

- Java 17
- Maven
- Selenium WebDriver 4
- TestNG
- Chrome Browser

## Project Structure

- `BaseTest.java` — browser setup and teardown
- `Basepage.java` — common page object base logic
- `LoginPage.java` — login page interactions
- `DashboardPage.java` — dashboard and internship search flows
- `InternshipPage.java` — internship application flow
- `LogoutPage.java` — logout flow
- `InternshipTest.java` — main test class
- `pom.xml` — Maven dependencies and build configuration
- `testng.xml` — TestNG suite configuration

## Prerequisites

Before running the project, make sure you have:

- JDK 17 installed
- Maven installed
- Google Chrome installed
- Access to the Internshala website

## Configuration

Update the login credentials in `InternshipTest.java` before running the tests:

```java
login.Studentlogin("your_email@example.com", "your_password");
```

If the website changes its selectors or login flow, you may need to update the page object classes accordingly.

## Running the Tests

From the project root, run:

```bash
mvn test
```

Or run the TestNG suite explicitly:

```bash
mvn test -DsuiteXmlFile=testng.xml
```

## Notes

- Some test methods in `InternshipTest.java` are currently disabled using `@Test(enabled = false)`.
- You can enable them when you want to test those flows.
- The project uses Chrome options such as `--no-sandbox` and `--disable-dev-shm-usage` for stability in containerized or CI environments.

## Example Test Flow

```java
@Test(priority = 1)
public void Teststudentlogin() {
    LoginPage login = new LoginPage(driver);
    login.Studentlogin("your_email@example.com", "your_password");
}
```

## License

This project is for educational and automation testing purposes.
