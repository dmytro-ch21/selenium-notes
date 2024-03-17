# Selenium Useful Methods


### Selenium WebDriver

> Selenium WebDriver is an interface that defines a set of methods for interacting with web browsers. Below are the WebDriver classes that implement the WebDriver interface for different browsers:
> - **ChromeDriver**: For Google Chrome
> - **FirefoxDriver**: For Mozilla Firefox
> - **InternetExplorerDriver**: For Internet Explorer
> - **EdgeDriver**: For Microsoft Edge
> - **SafariDriver**: For Apple Safari
> - **OperaDriver**: For Opera

## Common WebDriver Methods

| Method                | Return Type        | Description                                         |
|-----------------------|--------------------|-----------------------------------------------------|
| `get(String url)`     | `void`             | Navigates to a URL.                                 |
| `findElement(By by)`  | `WebElement`       | Finds the first element matching the given locator. |
| `findElements(By by)` | `List<WebElement>` | Finds all elements matching the given locator.      |
| `getTitle()`          | `String`           | Returns the title of the current page.              |
| `getCurrentUrl()`     | `String`           | Returns the URL of the current page.                |
| `close()`             | `void`             | Closes the current window.                          |
| `quit()`              | `void`             | Closes all windows and ends the WebDriver session.  |

## WebElement

WebElement is an interface that represents an element on the web page. Here are some useful methods provided by the WebElement interface:

| Method                                 | Return Type | Description                                   |
|----------------------------------------|-------------|-----------------------------------------------|
| `click()`                              | `void`      | Clicks on the element.                        |
| `sendKeys(CharSequence... keysToSend)` | `void`      | Types into the element.                       |
| `getText()`                            | `String`    | Gets the visible text of the element.         |
| `getAttribute(String attributeName)`   | `String`    | Gets the value of the given attribute.        |
| `isDisplayed()`                        | `boolean`   | Checks if the element is visible on the page. |
| `isEnabled()`                          | `boolean`   | Checks if the element is enabled.             |
| `isSelected()`                         | `boolean`   | Checks if the element is selected.            |

###### Click Here &rarr; [Go Back to Table of Contents](../README.md)
