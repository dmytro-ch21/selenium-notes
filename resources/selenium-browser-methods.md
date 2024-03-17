# Browser Methods

We will begin with a simple idea of understanding how to automate the basic actions that a user can perform on the web browser.

### **1. `driver.get("http://google.com");`**

- **Description**: Navigates to the specified URL and waits for the page to fully load before moving on to the next command.
- **Example**: Navigating to Google's homepage.

### **2. `driver.navigate().to("http://google.com");`**

- **Description**: Also navigates to the specified URL. While it is generally similar to **`driver.get()`** in terms of loading the page, it is part of the **`navigate`** interface, which provides additional methods for browser navigation.
- **Example**: Navigating to Google's homepage.

### **3. `driver.navigate().refresh();`**

- **Description**: This method refreshes the current page, reloading all its content.
- **Example**: Refreshing the page to see updated content or changes.

### **4. `driver.navigate().back();`**

- **Description**: This method simulates clicking the browser's back button, navigating to the previous page in the browser's history.
- **Example**: Going back to the previous page after navigating to a new page.

### **5. `driver.navigate().forward();`**

- **Description**: This method simulates clicking the browser's forward button, navigating to the next page in the browser's history (if available).
- **Example**: Going forward to the next page after navigating back.

### **6. `driver.close();`**

- **Description**: This method closes the current browser window or tab. If it's the only window or tab open, it will also terminate the WebDriver session.
- **Example**: Closing the browser window after completing a test.

### **7. `driver.quit();`**

- **Description**: This method closes all browser windows and tabs and ends the WebDriver session.
- **Example**: Quitting the WebDriver and closing all associated browser windows at the end of the test suite.

### **8. `driver.getCurrentUrl();`**

- **Description**: This method returns the URL of the current page as a string.
- **Example**: Checking the URL to verify that the correct page has been loaded.

### **9. `driver.getTitle();`**

- **Description**: This method returns the title of the current page as a string.
- **Example**: Verifying the page title to ensure the correct page is displayed.

### **10. `driver.manage().window().maximize();`**

- **Description**: This method maximizes the browser window.
- **Example**: Maximizing the window to ensure that all elements are visible for interaction.

###### Click Here &rarr; [Go Back to Table of Contents](../README.md)
