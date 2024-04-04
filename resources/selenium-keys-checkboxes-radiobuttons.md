# Keys - Checkboxes - Radio buttons

## Introduction to Keys Class in Selenium
> The Keys class in Selenium WebDriver is a powerful tool that allows you to simulate keyboard actions in automated tests. 
> This class provides a set of predefined keyboard keys that can be used to interact with web elements, navigate through forms, and perform various keyboard operations.

### Use Cases:

##### The Keys class is commonly used in scenarios such as:
- __Form Navigation__: Moving between input fields in a form using the TAB key.
- __Text Manipulation__: Selecting, copying, pasting, or deleting text in input fields.
- __Keyboard Shortcuts__: Executing keyboard shortcuts like CTRL + A to select all text.
- __Dropdown Navigation__: Navigating through dropdown options using the ARROW keys.
- __Submitting Forms__: Submitting a form by simulating the ENTER key.

### Navigating Between Input Fields
```java
WebElement firstNameInput = driver.findElement(By.id("firstName"));
WebElement lastNameInput = driver.findElement(By.id("lastName"));

// Move from the first name field to the last name field using TAB
firstNameInput.sendKeys("John");
firstNameInput.sendKeys(Keys.TAB);
lastNameInput.sendKeys("Doe");
```

### Selecting and Deleting Text
```java
WebElement inputField = driver.findElement(By.id("inputField"));

// Enter text, select all using CTRL + A, and delete using BACKSPACE
inputField.sendKeys("Some text");
inputField.sendKeys(Keys.CONTROL + "a");
inputField.sendKeys(Keys.BACKSPACE);
```

### Using Keyboard Shortcuts
```java
WebElement inputField = driver.findElement(By.id("inputField"));

// Copy and paste text using CTRL + C and CTRL + V
inputField.sendKeys("Text to copy");
inputField.sendKeys(Keys.CONTROL + "a");
inputField.sendKeys(Keys.CONTROL + "c");
inputField.sendKeys(Keys.TAB);
inputField.sendKeys(Keys.CONTROL + "v");

// The Keys.chord() method in Selenium WebDriver is used to simulate a combination of keyboard keys in a single action. 
// It's particularly useful for executing keyboard shortcuts or performing multiple key presses simultaneously. 
// Here are some additional examples:
inputField.sendKeys(Keys.chord(Keys.CONTROL, "a")); // Select all text
inputField.sendKeys(Keys.chord(Keys.CONTROL, "c")); // Copy text
inputField.sendKeys(Keys.chord(Keys.CONTROL, "v")); // Paste text
```
### Navigating Through Dropdown Options
```java
WebElement dropdown = driver.findElement(By.id("dropdown"));

// Open the dropdown and navigate through options using ARROW keys
dropdown.sendKeys(Keys.ENTER);
dropdown.sendKeys(Keys.ARROW_DOWN);
dropdown.sendKeys(Keys.ARROW_DOWN);
dropdown.sendKeys(Keys.ENTER);
```

### Submitting a Form or search input
```java
WebElement submitButton = driver.findElement(By.id("submitButton"));

// Submit the form by simulating the ENTER key on the submit button
submitButton.sendKeys(Keys.ENTER);
```

## Introduction to Checkboxes
> Checkboxes are a common element in web forms, allowing users to select one or more options from a set of choices. 
> In Selenium WebDriver, handling checkboxes involves interacting with the `<input>` element of type "checkbox."

### Understanding Checkboxes
Checkboxes are used for the following purposes:

- __Multiple Selections__: Unlike radio buttons, checkboxes allow users to select multiple options.
- __Boolean Input__: Each checkbox represents a binary choice (e.g., yes/no, true/false).
- __Form Data__: Checkboxes contribute to the data submitted with a form.

### Methods for Interacting with Checkboxes

1. __Clicking a Checkbox: Use the `click()` method to toggle the state of a checkbox.__
   ```java
   WebElement checkbox = driver.findElement(By.id("checkboxId"));
   checkbox.click(); // Toggle the checkbox state
   ```
2. __Checking if a Checkbox is Selected: Use the `isSelected()` method to determine if a checkbox is currently selected `(checked)`.__
   ```java
   boolean isChecked = checkbox.isSelected();
   if (isChecked) {
      System.out.println("The checkbox is selected.");
   } else {
      System.out.println("The checkbox is not selected.");
   }
   ```
3. __Setting a Checkbox to a Specific State: Use a combination of `click()` and `isSelected()` to ensure a checkbox is in the desired state.__  
    ```java
    // Ensure the checkbox is selected
    if (!checkbox.isSelected()) {
       checkbox.click();
    }

    // Ensure the checkbox is not selected
    if (checkbox.isSelected()) {
        checkbox.click();
    }
    ```
4. __Selecting Multiple Checkboxes__ - Assuming you have a form with multiple checkboxes with the same class name:
   ```java
   List<WebElement> checkboxes = driver.findElements(By.className("optionCheckbox"));

   // Select all checkboxes
   for (WebElement checkbox : checkboxes) {
       if (!checkbox.isSelected()) {
           checkbox.click();
       }
   }
   ```
5. __Deselecting All Checkboxes__ 
   ```java
   // Deselect all checkboxes
   for (WebElement checkbox : checkboxes) {
       if (checkbox.isSelected()) {
           checkbox.click();
      }
   }
   ```

### Conclusion
Checkboxes are a crucial part of many web forms, and Selenium WebDriver provides straightforward methods to interact with them. By using the click() and isSelected() methods, you can easily automate the process of selecting, deselecting, and verifying the state of checkboxes in your automated tests.

## Radio Buttons Introduction
> Radio buttons are a common element in web forms, allowing users to select one option from a group of choices. 
> In Selenium WebDriver, handling radio buttons involves interacting with the `<input>` element of type "radio."

### Understanding Radio Buttons
Radio buttons are used for the following purposes:

- __Single Selection__: Users can select only one option from a group of radio buttons.
- __Mutual Exclusivity__: Selecting one radio button automatically deselects any other selected radio button in the group.
- __Form Data__: The selected radio button contributes to the data submitted with a form.

### Methods for Interacting with Radio Buttons

1. __Clicking a Radio Button: Use the `click()` method to select a radio button.__
    ```java
    WebElement radioButton = driver.findElement(By.id("radioButtonId"));
    radioButton.click(); // Select the radio button
    ```

2. __Checking if a Radio Button is Selected: Use the `isSelected()` method to determine if a radio button is currently selected.__
    ```java
    boolean isSelected = radioButton.isSelected();
    if (isSelected) {
        System.out.println("The radio button is selected.");
    } else {
        System.out.println("The radio button is not selected.");
    }
    ```

3. __Selecting a Single Radio Button__
    ```java
    WebElement genderMaleRadioButton = driver.findElement(By.id("genderMale"));
    genderMaleRadioButton.click(); // Select the 'Male' radio button
    ```

4. __Working with a Group of Radio Buttons__
Assuming you have a form with a group of radio buttons for selecting a color:

    ```java
    List<WebElement> colorRadioButtons = driver.findElements(By.name("color"));

    // Select the radio button with the value 'Red'
    for (WebElement radioButton : colorRadioButtons) {
        String color = radioButton.getAttribute("value");
        if ("Red".equals(color)) {
            radioButton.click();
            break;
        }
    }
    ```

5. __Checking Which Radio Button is Selected__
    ```java
    String selectedColor = null;
    for (WebElement radioButton : colorRadioButtons) {
        if (radioButton.isSelected()) {
            selectedColor = radioButton.getAttribute("value");
            break;
        }
    }
   System.out.println("Selected color: " + selectedColor);
   ```



## Conclusion
Radio buttons are an essential part of many web forms, and Selenium WebDriver provides straightforward methods to interact with them. 
By using the click() and isSelected() methods, you can easily automate the process of selecting and verifying the state of radio buttons in your automated tests.