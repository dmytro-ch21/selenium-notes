# Introduction

> In automated testing with Selenium, verifying the presence, visibility, and attributes of web elements is crucial for ensuring the correct functioning of a web application. 
> This guide covers essential techniques for element verification, including checking for element presence, visibility, text content, and attribute values.

## Verifying Element Presence
To verify the presence of an element on a web page, use the findElements() method. This method returns a list of web elements matching the specified locator. If the list is empty, the element is not present.
```java
List<WebElement> logoElements = driver.findElements(By.cssSelector("img[src *= 'logo']"));

if (logoElements.size() > 0) {
    System.out.println("Logo is present on the page.");
} else {
    System.out.println("Logo is not present on the page.");
}
```

## Checking Element Visibility
The isDisplayed() method checks if an element is visible to the user. It returns true if the element is visible, otherwise false.
```java
WebElement loginButton = driver.findElement(By.id("loginButton"));

if (loginButton.isDisplayed()) {
    System.out.println("Login button is visible.");
} else {
    System.out.println("Login button is not visible.");
}
```

## Retrieving Text from an Element
Use the getText() method to retrieve the visible text of an element. This is useful for verifying text content such as titles, headers, and error messages.

```java
WebElement pageTitle = driver.findElement(By.tagName("h1"));

String titleText = pageTitle.getText();
System.out.

println("Page title: "+titleText);

// Also you can have a list of web elements where you can extract the text from each of them
// Here we will simply print the values in the console

List<WebElemenst> list = driver.findElemnts(By.xpath("//some[xpath that returns multiple elements]"));

for(WebElement element : list){
    System.out.println(element.getText());
}

```

## Checking if an Element is Enabled
The isEnabled() method checks if an element is enabled and can be interacted with. It returns true if the element is enabled.

```java
WebElement searchButton = driver.findElement(By.id("searchButton"));

if (searchButton.isEnabled()) {
    System.out.println("Search button is enabled.");
} else {
    System.out.println("Search button is disabled.");
}
```

## Getting Attribute Values
The getAttribute() method retrieves the value of a specified attribute of an element. This is useful for getting properties such as placeholder, value, or custom attributes.
```java
WebElement emailInput = driver.findElement(By.id("email"));

String placeholderText = emailInput.getAttribute("placeholder");
System.out.println("Email input placeholder: " + placeholderText);
```

## Retrieving CSS Property Values
The getCssValue() method returns the value of a specified CSS property. This can be used to verify styling properties like color, font-size, or background-color.
```java
WebElement submitButton = driver.findElement(By.id("submitButton"));

String backgroundColor = submitButton.getCssValue("background-color");
System.out.println("Submit button background color: " + backgroundColor);
```

### Conclusion
In Selenium automated testing, verifying web elements is a fundamental step to ensure the correct behavior and appearance of a web application. By utilizing methods such as `isDisplayed()`, `isEnabled()`, `getText()`, `getAttribute()`, and `getCssValue()`, testers can effectively validate various aspects of web elements, contributing to thorough and reliable test coverage.

| Method            | Explanation                                                                                         |
|-------------------|-----------------------------------------------------------------------------------------------------|
| `findElements()`  | Returns a list of web elements matching the specified locator. Used to verify element presence.     |
| `isDisplayed()`   | Checks if an element is visible to the user. Returns `true` if visible, `false` if not.             |
| `getText()`       | Retrieves the visible text of an element. Useful for verifying text content.                        |
| `isEnabled()`     | Checks if an element is enabled and can be interacted with. Returns `true` if enabled.              |
| `getAttribute()`  | Retrieves the value of a specified attribute of an element. Used for getting properties.            |
| `getCssValue()`   | Returns the value of a specified CSS property. Used to verify styling properties.                   |


###### Click Here &rarr; [Go Back to Table of Contents](../README.md)