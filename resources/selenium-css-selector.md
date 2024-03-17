# **CSS Selectors**

## **Introduction:**

> CSS Selectors are patterns used to select elements for styling in a webpage.
> Like XPath, they can be used to locate web elements in Selenium for automation testing.


> CSS Selectors are often simpler and more performant than XPath, making them a preferred choice for many scenarios.

### **Types of CSS Selectors**

- **Simple Selectors:** Select elements based on name, id, or class.
- **Attribute Selectors:** Select elements based on their attributes.
- **Combinators:** Combine multiple selectors to refine element selection.

### **CSS Selector Syntax**

- **Element Selector:** `tagName`
- **ID Selector:** `#id`
- **Class Selector:** `.class`
- **Attribute Selector:** `[attribute=value]`

### **Extended Usage of CSS Selectors**
| Selector     | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| `div span`   | Selects all `<span>` elements inside `<div>` elements.                      |
| `div > span` | Selects all `<span>` elements that are direct children of `<div>` elements. |
| `h1 + p`     | Selects the first `<p>` element that directly follows an `<h1>` element.    |
| `h1 ~ p`     | Selects all `<p>` elements that follow an `<h1>` element.                   |

> CSS Selectors can be combined and used in complex ways to target specific elements:

### **Purposes of Using CSS Selectors in Selenium:**

- **Readability:** CSS Selectors are often more concise and easier to understand than XPath.
- **Performance:** CSS Selectors can be faster than XPath in some browsers.
- **Compatibility:** CSS Selectors are widely supported across different browsers.

### **Examples of CSS Selectors:**

| CSS Selector         | Explanation                                                              |
|----------------------|--------------------------------------------------------------------------|
| `div`                | Selects all `<div>` elements.                                            |
| `#myId`              | Selects the element with `id="myId"`.                                    |
| `.myClass`           | Selects all elements with `class="myClass"`.                             |
| `[name='myName']`    | Selects all elements with `name="myName"`.                               |
| `a[target='_blank']` | Selects all `<a>` elements with `target="_blank"`.                       |
| `input[type='text']` | Selects all `<input>` elements with `type="text"`.                       |
| `div > p `           | Selects all `<p>` elements that are direct children of `<div>` elements. |
| `ul + p`             | Selects the first `<p>` element that directly follows a `<ul>` element.  |
| `li:first-child `    | Selects the first `<li>` element in each list.                           |
| `:not(.myClass) `    | Selects all elements that do not have the class myClass.                 |

### **Practical Examples:**

###### Example HTML
```html
<body>
  <div>
    <a href="#link1">Link 1</a>
  </div>
  <div class="link-container">
    <a href="#link2" id="second-link">Link 2</a>
  </div>
  <div id="third-link-container">
    <a href="#link3">Link 3</a>
  </div>
</body>
```

### **CSS Selector Solutions**

| Task                                                        | CSS Selector                |
|-------------------------------------------------------------|-----------------------------|
| Select all `<a>` elements                                   | `a`                         |
| Select elements that have a specific attribute.             | `[id] `                     |
| Selects elements with a specific attribute and value.       | `[id=third-link-container]` |
| Selects <tag> elements with a specific attribute and value. | `a[id=second-link]`         |


```html
<div title="unique title">
  <div> First gen
    <div> Second Gen
      <div> Third gen
        <p>Third descendant div</p>
      </div>
    </div>
  </div>
</div>
```
| Task                                                                    | CSS Selector                          |
|-------------------------------------------------------------------------|---------------------------------------|
| Select preceding elements                                               | `tag[attribute=value]>tag>tag`        |
| Select `<p>` element going from top `<div>` tag                         | `div[title='unique title']>div>div>p` |
| Select `<p>` element going from top `<div>` tag by skipping generations | `div[title='unique title'] p`         |

```html
<body>
  <div class="link-container">
      <button id="example-button">
          <a href="#example" name="long-name-example-link">Click me!</a>
      </button>
  </div>
</body>
```
### **CSS Selector Tasks and Solutions**

| Task                                                                                             | CSS Selector              |
|--------------------------------------------------------------------------------------------------|---------------------------|
| Selects `<a>` elements whose `name` attribute contains `name-example`.                           | `a[name*='name-example']` |
| Selects `<a>` elements whose `name` attribute starts with `long-name`.                           | `a[name^='long-name']`    |
| Selects `<a>` elements whose `name` attribute ends with `example-link`.                          | `a[name$='example-link']` |
| Selects `<a>` elements that are descendants of any element with class `create` inside a `<div>`. | `div #example-button a`   |
