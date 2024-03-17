# **Working with Web Tables**

## **1. What is a Web Table?**

> A web table is an HTML element used to display data in a structured format, consisting of rows and columns. It's commonly used to present information like financial data, product details, or contact lists.

## **2. Understand the Structure**

Before diving into handling web tables, it's crucial to understand the basic structure of an HTML table:

- **`<table>`**: The container element for the table.
- **`<thead>`**: The table header, containing header rows (**`<tr>`**) and header cells (**`<th>`**).
- **`<tbody>`**: The table body, containing data rows (**`<tr>`**) and data cells (**`<td>`**).
- **`<tr>`**: A table row.
- **`<td>`**: A table data cell.
- **`<th>`**: A table header cell.

## **3. Build an HTML Table**

Here's an example of a simple HTML table:

```html
htmlCopy code
<table>
    <thead>
        <tr>
            <th>Number</th>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Address</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Omar</td>
            <td>Ramo</td>
            <td>123 Street</td>
        </tr>
        <tr>
            <td>2</td>
            <td>John</td>
            <td>Doe</td>
            <td>321 Street</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Jane</td>
            <td>Doe</td>
            <td>321 Street</td>
        </tr>
    </tbody>
</table>

```

## **4. Build XPath for Tables**

### **4.1 Locate a Single Cell**

To locate a specific cell, you can use the row and column indices in your XPath:

```shell
//table[@id='myTable']/tbody/tr[2]/td[3]
```

### **4.2 Locate a Row**

To locate a specific row, use the row index without specifying the table data cell:

```shell
//table[@id='myTable']/tbody/tr[2]
```

### **4.3 Locate a Full Column**

To locate all cells in a specific column, use the column index without specifying the tr index:

```shell
//table[@id='myTable']/tbody/tr/td[3]
or
//table[@id='myTable']/tbody//td[3]
```

### **4.4 Creating Reusable Functions**

You can create reusable functions to get data from a specific cell or row etc...

```java
public List<String> getColumnData(WebDriver driver, int rowIndex, int columnIndex) {
    WebElement cellData = 
            driver.findElement(By.xpath("//table[@id='myTable']/tbody/tr[" + rowIndex + "]/td[" + columnIndex + "]"));
    return cellData.getText();
}
```
In this example we will take a whole column and extract the text of the elements and add them to another List which we will return.

```java
import org.openqa.selenium.WebDriver;

import java.util.ArrayList;

public List<String> getColumnData(WebDriver driver, int columnIndex) {
    List<WebElement> columnElements = 
            driver.findElements(By.xpath("//table[@id='myTable']/tbody/tr/td[" + columnIndex + "]"));
    List<String> data = new ArrayList<>();
    for (WebElement element : columnElements) {
        data.add(element.getText());
    }
    return data;
}
```


### **4.5 Work with Tables That Don't Have Correct Semantics**

For tables that don't use **`<table>`**, **`<tr>`**, and **`<td>`** tags correctly, you can still use XPath to navigate through the structure, but you'll need to rely more on class names, IDs, or other attributes.

For example, if a table uses **`<div>`** elements instead of **`<tr>`** and **`<td>`**, your XPath might look like this:

```shell
//div[@class='table']/div[@class='row']/div[@class='cell']
```

## **Additional Tips**

- **Practice**: Try working with different tables on websites like [Test Automation Practice](https://testautomationpractice.blogspot.com/) or [OrangeHRM](https://opensource-demo.orangehrmlive.com/).
- **Be Flexible**: XPath is powerful, but sometimes CSS selectors might be simpler for certain tasks. Use the best tool for the job.
- **Debugging**: If your XPath isn't working as expected, break it down into smaller parts and test each part separately.
