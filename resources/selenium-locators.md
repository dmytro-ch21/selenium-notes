# Selenium Locators

>  While writing automation scripts we will often need to interact with web elements on a web page.  
> 
>  This will be possible with a selenium method `driver.findElement()` that will return you a WebElement.  
> 
>  However, we will need to provide a Locator to the `driver.findElement()` method to point out to a specific one.


## In selenium there are 8 locator strategies we can use:
- `By.id()`
- `By.name()`
- `By.tagName()`
- `By.className()`
- `By.linkText()`
- `By.partialLinkText()`
- `By.xpath()`
- `By.cssSelector()`

## Let's explore each in details:

### By.id()
> The `By.id()` is a locator strategy used to find a web element based on its id attribute. The id attribute is meant to be a unique identifier for each element on a web page, making By.id a fast and reliable way to locate elements.
- Here is a sample html block and we will need to locate the Item 2  
```html
<body>
    <div id="item1">Item 1</div>    
    <div id="item2">Item 2</div>    
    <div id="item3">Item 3</div>
</body>
```
- Using `By.id()` locator strategy we can easily locate the item by passing the value of the needed id as an argument to the method:
```java
WebElement secondItem = driver.findElement(By.id("item2"));
```
---

### By.name()
> The `By.name()` is a locator strategy used to find a web element based on its name attribute. The name attribute is commonly used in form elements like input fields, checkboxes, and radio buttons. It's not necessarily unique like the id attribute, so By.name() might return multiple elements if there are multiple elements with the same name.
- Here is a sample html block and we will need to locate submit button:
```html
<body>
    <form>
        <input type="text" name="username" placeholder="Username">
        <input type="password" name="password" placeholder="Password">
        <input type="submit" name="submit" value="Submit">
    </form>
</body>
```
- Using `By.name()` locator strategy we can locate the button:
```java
WebElement submitButton = driver.findElement(By.name("submit"));
```
---

### By.tagName()
> The `By.tagName()` locator in Selenium is used to find elements based on their HTML tag name. This locator can return a single element or a list of elements if multiple elements have the same tag name.
- Here is a sample html block and we will need to locate the paragraph:
```html
<body>
    <div>First Div Element</div>
    <div>Second Div Element</div>
    <p>Paragraph Element</p>
</body>
```
- Using `By.tagName()` locator strategy we can locate the paragraph:
```java
WebElement paragraph = driver.findElement(By.tagName("p"));
```
---

### By.className()
> The `By.className()` locator is used to find elements based on their CSS class name. Like By.tagName(), it can return a single element or a list of elements if multiple elements share the same class name.

- Here is a sample html block and we will need to locate the container div:
```html
<body>
    <div class="container">Container Div</div>
    <button class="btn primary">Primary Button</button>
    <button class="btn secondary">Secondary Button</button>
</body>
```
- Using `By.className()` locator strategy we can locate the element container:
```java
WebElement container = driver.findElement(By.className("container"));
```
---

### By.linkText()

> The By.linkText() locator in Selenium is used to find a hyperlink (anchor tag) based on its exact visible text. This is particularly useful when you want to interact with links on a webpage.

- Here is a sample html block and we will need to locate the link that has visible text 'Click Here':
```html
<body>
    <a href="https://example.com">Click Here</a>
    <a href="https://example.com/about">Learn More About Us</a>
</body>
```
- Using `By.linkText()` locator strategy we can locate the 'Click Here':
```java
WebElement clickHereLink = driver.findElement(By.linkText("Click Here"));
```
---

### By.partialLinkText()

> The By.partialLinkText() locator allows you to find a hyperlink with (anchor tag) based on a partial match of its visible text. This is useful when the full text of the link is dynamic or too long.

- Here is a sample html block and we will need to locate the link that has visible text 'Learn More About Us':
```html
<body>
    <a href="https://example.com">Click Here</a>
    <a href="https://example.com/about">Learn More About Us</a>
</body>
```
- Using `By.partialLinkText()` locator strategy we can locate the 'Learn More About Us' using just a part of it:
```java
WebElement clickHereLink = driver.findElement(By.partialLinkText("About"));
```

### By.xpath()

> The `By.xpath()` locator in Selenium is used to find elements based on an XPath expression. XPath is a powerful language for navigating through elements and attributes in an XML document, and it can be used to locate elements in an HTML document as well.

- Here is a sample HTML block, and we will need to locate the second list item:
```html
<body>
<ul>
  <li>List Item 1</li>
  <li>List Item 2</li>
  <li>List Item 3</li>
</ul>
</body>
```

- Using By.xpath() locator strategy, we can locate the second list item by its position:
```java
WebElement secondListItem = driver.findElement(By.xpath("//ul/li[2]"));
```

### By.cssSelector()

> The By.cssSelector() locator in Selenium is used to find elements based on a CSS selector. CSS selectors are patterns used to select elements based on their id, class, attributes, and more.

- Here is a sample HTML block, and we will need to locate the button with the class 'primary':
```html
<body>
    <button class="btn primary">Primary Button</button>
    <button class="btn secondary">Secondary Button</button>
</body>
```

- Using By.cssSelector() locator strategy, we can locate the primary button by its class:
```java
WebElement primaryButton = driver.findElement(By.cssSelector("button.primary"));
```

## Locating one element vs multiple elements
- So far we discussed how to locate one element. We used some techniques to make sure the locator we will use is unique. However, even if we would provide a locator to `findElement()` that returns multiple results it would pick the very first element.  
- There are cases that we are interested to access programmatically to multiple elements at the same time. For such cases we will use `findElements()` method. 

> While `driver.findElement()` returns you a single web element, the `driver.findElements()` will return you a List of web elements.

- Here is the sample html:
```html
<body>
    <a href="https://example.com" class="common-class">Example Link 1</a>
    <a href="https://example.com/about" class="common-class">Example Link 2</a>

    <input type="text" class="common-class" placeholder="Input Field 1">
    <input type="password" class="common-class" placeholder="Input Field 2">

    <p class="common-class">This is a paragraph 1.</p>
    <p class="common-class">This is a paragraph 2.</p>
</body>
```

- `findElement()`:
  - If we use `findElement(By.tagName("a"))` that returns us 2 elements, the `findElement()` method will pick only first one.
  - If there are no findings `findElement(By.tagName("img"))` this will throw you an exception ElementNotFound.
- `findElements()`:
  - If we use `findElements(By.tagName("a"))` where locator gives you 2 options, and the `findElements()` will return you a list of elements.
  - If we provide a locator that doesn't exist then findElements just returns a empty list. No exceptions are thrown.

```java
List<WebElement> links = driver.findElements(By.className("common-class"));
// option 1 - get access to each element directly
links.get(0).click();
links.get(1).click();
// option 2 - we can access the elements by looping through the list
for(WebElement link: links){
    links.click();
}
```

#### Use cases for findElements():
- There are cases that we are interested to access programmatically to multiple elements at the same time. For such cases we will use `findElements()` method.
  - **Search Results**
  - **Navigation Menu**
  - **Checking Checkbox Options**
  - **Table Data Validation**
  - **Handling Dynamic Lists**
  - **Dropdown Options Check**

###### Click Here &rarr; [Go Back to Table of Contents](../README.md)