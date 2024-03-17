# CSS Cheat Sheet

Below is a detailed CSS cheat sheet with selectors, properties, and their possible values. This cheat sheet is designed to be comprehensive and beginner-friendly.

## Selectors

| Selector              | Description                                                                               |
|-----------------------|-------------------------------------------------------------------------------------------|
| `*`                   | Universal selector, matches any element.                                                  |
| `element`             | Type selector, matches all elements with the given node name.                             |
| `.class`              | Class selector, matches all elements with the given class attribute.                      |
| `#id`                 | ID selector, matches an element with the given ID attribute.                              |
| `[attribute]`         | Attribute selector, matches elements with the specified attribute.                        |
| `:pseudo-class`       | Pseudo-class selector, matches elements in a specific state (e.g., `:hover`, `:focus`).   |
| `::pseudo-element`    | Pseudo-element selector, selects a part of an element (e.g., `::before`, `::after`).      |
| `element1 element2`   | Descendant selector, matches `element2` that is a descendant of `element1`.               |
| `element1 > element2` | Child selector, matches `element2` that is a direct child of `element1`.                  |
| `element1 + element2` | Adjacent sibling selector, matches `element2` that is immediately preceded by `element1`. |
| `element1 ~ element2` | General sibling selector, matches `element2` that is preceded by `element1`.              |

## Properties and Values

### Text and Font

| Property            | Possible Values                                                              |
|---------------------|------------------------------------------------------------------------------|
| `color`             | Color names, RGB, HEX, etc. (e.g., `red`, `#ff0000`, `rgb(255, 0, 0)`)       |
| `font-family`       | Font names or generic family (e.g., `Arial`, `sans-serif`)                   |
| `font-size`         | Length units, keywords (e.g., `12px`, `1.5em`, `large`)                      |
| `font-weight`       | `normal`, `bold`, `100` to `900`                                             |
| `font-style`        | `normal`, `italic`, `oblique`                                                |
| `text-align`        | `left`, `right`, `center`, `justify`                                         |
| `text-decoration`   | `none`, `underline`, `overline`, `line-through`                              |
| `text-transform`    | `none`, `capitalize`, `uppercase`, `lowercase`                               |
| `line-height`       | Number, length units, percentage (e.g., `1.5`, `20px`, `150%`)               |

### Box Model

| Property            | Possible Values                                                              |
|---------------------|------------------------------------------------------------------------------|
| `width`             | Length units, percentage (e.g., `100px`, `50%`)                              |
| `height`            | Length units, percentage (e.g., `200px`, `75%`)                              |
| `margin`            | Length units, percentage, auto (e.g., `10px`, `5%`, `auto`)                  |
| `padding`           | Length units, percentage (e.g., `15px`, `10%`)                               |
| `border`            | Border width, style, color (e.g., `2px solid black`)                         |
| `box-sizing`        | `content-box`, `border-box`                                                  |

### Layout

| Property                         | Possible Values                                              |
|----------------------------------|--------------------------------------------------------------|
| `display`                        | `none`, `block`, `inline`, `inline-block`, `flex`, `grid`    |
| `position`                       | `static`, `relative`, `absolute`, `fixed`, `sticky`          |
| `top`, `right`, `bottom`, `left` | Length units, percentage, auto (e.g., `20px`, `10%`, `auto`) |
| `float`                          | `left`, `right`, `none`                                      |
| `clear`                          | `left`, `right`, `both`, `none`                              |
| `overflow`                       | `visible`, `hidden`, `scroll`, `auto`                        |

### Background

| Property              | Possible Values                                                           |
|-----------------------|---------------------------------------------------------------------------|
| `background-color`    | Color names, RGB, HEX, etc. (e.g., `blue`, `#00ff00`, `rgb(0, 255, 0)`)   |
| `background-image`    | `url(image.jpg)`, `none`                                                  |
| `background-repeat`   | `repeat`, `repeat-x`, `repeat-y`, `no-repeat`                             |
| `background-position` | Position keywords, length units, percentage (e.g., `center`, `top right`) |
| `background-size`     | Length units, percentage, `cover`, `contain`                              |

### Miscellaneous

| Property     | Possible Values                                   |
|--------------|---------------------------------------------------|
| `opacity`    | Number between `0` (transparent) and `1` (opaque) |
| `visibility` | `visible`, `hidden`, `collapse`                   |
| `cursor`     | `pointer`, `default`, `crosshair`, etc.           |
| `z-index`    | Integer (e.g., `1`, `10`, `-1`)                   |


###### Click Here &rarr; [SEE - HTML CHEATSHEET](html-cheatsheet.md)
###### Click Here &rarr; [Go Back to Table of Contents](../README.md)