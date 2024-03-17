# HTML and CSS Quick Overview

## 1. Introduction to HTML

HTML (HyperText Markup Language) is like the skeleton of a webpage. It's used to create and organize content on the web, such as text, images, and links.

### Details About HTML:
- **What It Stands For**: HTML stands for Hypertext Markup Language. It's the standard language for creating web pages.
- **Not a Programming Language**: Unlike programming languages, HTML doesn't have logic or calculations. It's all about structuring and presenting content.
- **For Static Content**: HTML is great for organizing and formatting content, but it can't create dynamic interactions by itself.
- **Tags Are Key**: HTML uses tags (like `<h1>`, `<p>`, and `<a>`) to mark up different elements on a page.
- **Browsers Bring It to Life**: When you write HTML, web browsers read it and display it in a formatted and colorful way to users.
- **Part of a Trio**: For modern web applications, HTML is usually used alongside CSS for styling and JavaScript for interactivity.

## 2. HTML Tags and Content

HTML documents are built with tags and content. Tags are keywords wrapped in angle brackets (like `<tag>` and `</tag>`) that define the structure of the content.

## 3. The Tree Structure of HTML

HTML documents have a tree-like structure, with nested tags creating a hierarchy. This allows for complex layouts, like a list (`<ul>`) containing list items (`<li>`).

## 4. The Basic Structure of an HTML Document

Every HTML document starts with a `<!DOCTYPE html>` declaration, followed by the root `<html>` tag. Inside, there are two main sections:

- `<head>`: Contains metadata, like the page title and links to stylesheets.
- `<body>`: Holds the visible content, such as text and images.

## 5. Common HTML Tags

- **Text Elements**: `<h1>` to `<h6>` for headings, `<p>` for paragraphs, `<b>` and `<strong>` for bold text, `<i>` for italic text.
- **Links**: `<a>` for hyperlinks.
- **Lists**: `<ul>` for unordered lists, `<ol>` for ordered lists, `<li>` for list items.
- **Forms**: `<form>` for forms, `<input>` for input fields, `<button>` for buttons.

## 6. Creating a Basic HTML Page
You can create in your IDE a new file as index.html and paste following code.

Here's an example of a simple HTML page:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My First HTML Page</title>
    </head>
    <body>
        <h1>Welcome to My Website</h1>
        <p>This is a paragraph of text.</p>
        <a href="https://www.example.com">Visit Example</a>
    </body>
</html>
```

## 7. Introduction to CSS
CSS (Cascading Style Sheets) adds style to HTML elements. It lets you add colors, fonts, and layouts to make your web pages look better.

## 8. Applying Basic CSS Styles
You can apply CSS in different ways: inline, within the <head> section, or in an external stylesheet. 
###### For example:

### 1. Inline CSS:

> You apply styles directly within an HTML element using the style attribute.
```html
<p style="color: blue; font-size: 16px;">This is a paragraph with inline CSS.</p>
```

### 2. Internal CSS (in the \<head\> section):

> You include a style tag within the head section of your HTML document.
> This allows you to apply styles to multiple elements within the same page.

```html
<head>
    <style>
        p {
            color: red;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <p>This is a paragraph with internal CSS.</p>
</body>
```

### 3. External CSS:

> You create a separate CSS file (e.g., styles.css) and link it to your HTML document using the link tag in the head section.
> This is the most recommended way to apply CSS as it keeps your styles separate from your HTML, making it easier to maintain and update.

###### In your HTML file:

```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <p>This is a paragraph with external CSS.</p>
</body>
```

###### In your styles.css file:
```css
p {
    color: green;
    font-size: 20px;
}
```

## 9. HTML Elements as WebElements
In Selenium automation, HTML elements are often called WebElements. 
These elements can have attributes like id, class, and style that affect their appearance and behavior.

Conclusion
Understanding HTML and CSS is essential for designing web pages and automating web interactions with Selenium. By learning common tags and how to style them, you'll be ready to create attractive and functional web pages.

> ### Interacting with the DOM in Selenium
> What is the DOM?: DOM stands for Document Object Model. It's the structure of the HTML page combined with CSS that represents the page.
> Finding Elements: In the browser's inspect tool, you can view the DOM in the "Elements" section. To find a specific element's HTML code, you can right-click on the element and choose "Inspect" or use the picker tool in the DOM view to select an element directly.



1. ##### Click Here &rarr; [SEE - HTML CHEATSHEET](html-cheatsheet.md)
2. ##### Click Here &rarr; [SEE - CSS CHEATSHEET](css-cheatsheet.md)
3. ##### Click Here &rarr; [Go Back to Table of Contents](../README.md)