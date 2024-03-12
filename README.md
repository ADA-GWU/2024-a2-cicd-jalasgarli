# WebTest Project

## Introduction

This project contains tests for a web application using Selenium WebDriver.

## Test Cases

### Test Case 1: Submit Form Functionality Test

#### Purpose

This test verifies the functionality of submitting a form on the web application.

#### Steps

1. **Open Web Browser**: Launch a web browser (Chrome).
2. **Navigate to Form Submission Page**: Access the form submission page (http://localhost:8080/student/new).
3. **Fill First Name Field**: Enter the value "Nihat" into the first name input field.
4. **Fill Last Name Field**: Enter the value "Ahmedov" into the last name input field.
5. **Submit Form**: Click the submit button to submit the form.
6. **Verify Success Message**: Check if a success message is displayed after submitting the form.

#### Expected Outcome

The test expects the form submission to be successful, indicated by the display of a success message after submission.

### Test Case 2: Find Students By Last Name Functionality Test

#### Purpose

This test verifies the functionality of finding students by their last name using a mocked repository.

#### Steps

1. **Mock Repository**: Mock the `findByLastNameIgnoreCase` method of the student repository to return a list of mocked students.
2. **Call Repository Method**: Call the mocked repository method with a specific last name.
3. **Verify Results**: Verify that the returned list contains one student with the specified last name.

#### Expected Outcome

The test expects the repository to correctly return a list of students with the specified last name, ensuring that the finding functionality works as expected.

## SeleniumConfig Class

The `SeleniumConfig` class is a Spring configuration class responsible for configuring the Selenium WebDriver bean used in the application's tests. This class is annotated with `@Configuration`, indicating that it provides bean definitions for the application context.

### webDriver Bean

The `webDriver` bean is defined within the `SeleniumConfig` class. This bean method is annotated with `@Bean`, indicating that it produces a bean to be managed by the Spring container.

### WebDriver Configuration

#### Chrome WebDriver Configuration

- The `WebDriverManager.chromedriver().setup()` line uses WebDriverManager to dynamically download and configure the ChromeDriver executable. This ensures that the appropriate version of ChromeDriver is used based on the version of the Chrome browser installed on the system.
- `ChromeOptions` allows for configuring the behavior of the Chrome WebDriver instance. Currently, the options are commented out, but typically, options like `--headless` can be added to run Chrome in headless mode, which means it runs without opening a visible browser window.

#### Firefox WebDriver Configuration (Commented Out)

Alternatively, you can switch to using Firefox by uncommenting the `FirefoxDriver` instantiation and related options. The `WebDriverManager.firefoxdriver().setup()` line would be used to set up the Firefox WebDriver.

### WebDriver Bean Creation

The `webDriver` bean method returns an instance of WebDriver, which is the Selenium interface representing a web browser's driver. This driver is used to automate interactions with web elements on web pages during tests.

#### ChromeDriver vs. FirefoxDriver

Currently, the `webDriver` bean is configured to use ChromeDriver. However, by uncommenting the relevant lines and commenting out the Chrome-related lines, you can switch to using FirefoxDriver.

## Conclusion

In summary, the `SeleniumConfig` class provides the necessary configuration for setting up the Selenium WebDriver bean used in the application's tests. The `webDriver` bean is configured to use ChromeDriver by default but can be easily switched to FirefoxDriver if needed. This configuration allows for flexible and consistent testing of web applications across different browsers.

