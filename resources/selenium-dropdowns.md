# Introduction
> Dropdowns are a common element in web applications, used to provide users with a list of options to choose from. 
> Selenium WebDriver offers tools to interact with dropdowns, making it easier to automate their selection process in your tests.

## Select Dropdown
Select dropdowns are typically implemented with the `<select>` tag in HTML. Selenium provides the Select class to interact with these dropdowns.
```java
WebDriver driver = new ChromeDriver();
driver.get("https://demo.automationtesting.in/Register.html");

WebElement skillsDropdown = driver.findElement(By.id("Skills"));
Select dropdown = new Select(skillsDropdown);

// Select an option by index
dropdown.selectByIndex(1);

// Select by visible text
dropdown.selectByVisibleText("C++");

// Select by value attribute
dropdown.selectByValue("Java");
```

#### Methods:
- `selectByIndex(int index)`: Selects an option based on its index.
- `selectByVisibleText(String text)`: Selects an option by the text displayed.
- `selectByValue(String value)`: Selects an option by its value attribute.

## Multi-Select Dropdowns
Some dropdowns allow multiple selections. Selenium's Select class provides methods to handle these as well.

See example of multi-select dropdowns [here](https://dmytro-ch21.github.io/)
```java
WebElement multiSelectDropdown = driver.findElement(By.id("multiSelect"));
Select multiDropdown = new Select(multiSelectDropdown);

multiDropdown.selectByVisibleText("Option 1");
multiDropdown.selectByVisibleText("Option 2");

// Deselect options
multiDropdown.deselectAll();
```
---
###### Here are all the methods of Select class that can be applied to multiselect dropdowns

| Method                           | Description                                                        |
|----------------------------------|--------------------------------------------------------------------|
| `selectByIndex(int index)`       | Selects an option based on its index position in the dropdown.    |
| `selectByValue(String value)`    | Selects an option based on its `value` attribute.                  |
| `selectByVisibleText(String text)` | Selects an option based on the visible text.                      |
| `deselectByIndex(int index)`     | Deselects an option based on its index position in the dropdown.  |
| `deselectByValue(String value)`  | Deselects an option based on its `value` attribute.                |
| `deselectByVisibleText(String text)` | Deselects an option based on the visible text.                  |
| `getAllSelectedOptions()`        | Returns a list of all selected options in the dropdown.           |
| `getFirstSelectedOption()`       | Returns the first selected option in the dropdown.                |
| `deselectAll()`                  | Deselects all selected options in the dropdown.                    |

## Custom Dropdowns
Custom dropdowns might not use the `<select>` tag and can be more complex. Interacting with them usually involves clicking the dropdown to reveal options and then selecting the desired option with `click()` method.

Example Code:
```java
WebElement dropdownButton = driver.findElement(By.cssSelector(".dropdown-button"));
dropdownButton.click();

WebElement option = driver.findElement(By.xpath("//li[text()='Option 1']"));
option.click();
```


