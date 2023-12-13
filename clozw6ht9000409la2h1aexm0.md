---
title: "Selector in CSS"
seoTitle: "Selector in CSS"
seoDescription: "Becoming an expert in CSS selectors involves understanding and mastering selectors at various levels. Here's a step-by-step guide categorizing"
datePublished: Wed Nov 15 2023 15:03:08 GMT+0000 (Coordinated Universal Time)
cuid: clozw6ht9000409la2h1aexm0
slug: selector-in-css
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/jLwVAUtLOAQ/upload/8429bfb3227da950c2dd431f81a7f329.jpeg
tags: css

---

# Selector in CSS

Becoming an expert in CSS selectors involves understanding and mastering selectors at various levels. Here's a step-by-step guide categorizing them into basic, mid-level, and advanced levels:

### Basic Level:

#### 1\. **Universal Selector:**

* `*`: Selects all elements on the page.
    

#### 2\. **Type Selector:**

* `element`: Selects all instances of a specified HTML element.
    

#### 3\. **Class Selector:**

* `.classname`: Selects all elements with a specific class.
    

#### 4\. **ID Selector:**

* `#id`: Selects a single element with a specific ID.
    

#### 5\. **Descendant Selector:**

* `ancestor descendant`: Selects all descendants of an ancestor element.
    

#### 6\. **Child Selector:**

* `parent > child`: Selects direct children of a parent element.
    

#### 7\. **Adjacent Sibling Selector:**

* `prev + next`: Selects an element that is immediately preceded by a specified element.
    

#### 8\. **Attribute Selector:**

* `[attribute]`: Selects elements with a specified attribute.
    

#### 9\. **Attribute with Value Selector:**

* `[attribute=value]`: Selects elements with a specific attribute value.
    

#### 10\. **Pseudo-classes:**

* `:hover`, `:active`, `:focus`: Selects elements based on user interaction.
    

### Mid-Level:

#### 11\. **Grouping:**

* `selector1, selector2`: Groups multiple selectors to apply the same styles.
    

#### 12\. **Multiple Classes and Selectors:**

* `.class1.class2`: Selects elements with both class1 and class2.
    
* `selector1.selector2`: Selects elements that match either selector1 or selector2.
    

#### 13\. **Nth Child and Nth of Type:**

* `:nth-child(n)`, `:nth-of-type(n)`: Selects elements based on their position.
    

#### 14\. **Not Selector:**

* `:not(selector)`: Selects elements that do not match the specified selector.
    

#### 15\. **Attribute Starts/Ends/Contains Selector:**

* `[attribute^=value]`, `[attribute$=value]`, `[attribute*=value]`: Selects elements based on the beginning, end, or containing a specific value in an attribute.
    

### Advanced Level:

#### 16\. **Sibling Combinator:**

* `prev ~ siblings`: Selects all siblings after the specified element.
    

#### 17\. **General Sibling Selector:**

* `prev ~ siblings`: Selects all siblings with the same parent.
    

#### 18\. **Complex Selectors:**

* Combine various selectors to create complex rules for targeting specific elements.
    

#### 19\. **Attribute Selectors with Regular Expressions:**

* `[attribute~=value]`: Selects elements where the specified attribute contains a certain word.
    

#### 20\. **Custom Data Attributes:**

* `[data-*]`: Selects elements based on custom data attributes.
    

#### 21\. **:nth-child() An+B Formula:**

* `:nth-child(an+b)`: Allows for more complex patterns in selecting elements.
    

#### 22\. **:before and :after Pseudo-elements:**

* `::before`, `::after`: Select and style generated content.
    

#### 23\. **:first-child, :last-child, :only-child:**

* `:first-child`, `:last-child`, `:only-child`: Select elements based on their position within a parent.
    

#### 24\. **Complex Structural Selectors:**

* Use combinations of `:not`, `:nth-child`, and other selectors for advanced structural targeting.
    

#### 25\. **Custom Selectors (using CSS Variables):**

* Leverage CSS variables to create reusable and dynamic selectors.
    

### Practice and Application:

* Apply these selectors in real projects.
    
* Solve challenges on platforms like CodePen, JSFiddle, or online coding challenges.
    
* Explore browser developer tools to experiment with selectors on live websites.
    

Remember, becoming an expert requires hands-on practice and continuously challenging yourself with real-world scenarios. Stay curious and keep experimenting!

---

Let's go through examples for each topic at the basic, mid-level, and advanced levels:

### Basic Level:

#### 1\. **Universal Selector:**

* Example: Apply styles to all elements on the page.
    
    ```css
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    ```
    

#### 2\. **Type Selector:**

* Example: Style all `<p>` elements.
    
    ```css
    p {
      font-size: 16px;
      color: #333;
    }
    ```
    

#### 3\. **Class Selector:**

* Example: Style elements with the class "highlight".
    
    ```css
    .highlight {
      background-color: yellow;
    }
    ```
    

#### 4\. **ID Selector:**

* Example: Style the element with the ID "header".
    
    ```css
    #header {
      font-size: 24px;
      font-weight: bold;
    }
    ```
    

#### 5\. **Descendant Selector:**

* Example: Style all `<li>` elements inside a `<ul>`.
    
    ```css
    ul li {
      list-style-type: square;
    }
    ```
    

#### 6\. **Child Selector:**

* Example: Style direct children of `<nav>`.
    
    ```css
    nav > a {
      text-decoration: none;
    }
    ```
    

#### 7\. **Adjacent Sibling Selector:**

* Example: Style the element immediately preceded by a heading.
    
    ```css
    h2 + p {
      font-style: italic;
    }
    ```
    

#### 8\. **Attribute Selector:**

* Example: Style all elements with a "required" attribute.
    
    ```css
    [required] {
      border: 1px solid red;
    }
    ```
    

#### 9\. **Attribute with Value Selector:**

* Example: Style links with `target="_blank"`.
    
    ```css
    a[target="_blank"] {
      color: blue;
    }
    ```
    

#### 10\. **Pseudo-classes:**

* Example: Style links on hover.
    
    ```css
    a:hover {
      text-decoration: underline;
    }
    ```
    

### Mid-Level:

#### 11\. **Grouping:**

* Example: Apply styles to multiple selectors.
    
    ```css
    h1, h2, h3 {
      color: darkblue;
    }
    ```
    

#### 12\. **Multiple Classes and Selectors:**

* Example: Style elements with both classes.
    
    ```css
    .important.highlight {
      font-weight: bold;
      background-color: yellow;
    }
    ```
    

#### 13\. **Nth Child and Nth of Type:**

* Example: Style every second `<li>` in a list.
    
    ```css
    li:nth-child(2) {
      color: green;
    }
    ```
    

#### 14\. **Not Selector:**

* Example: Style all paragraphs except those with the class "excluded".
    
    ```css
    p:not(.excluded) {
      font-size: 18px;
    }
    ```
    

#### 15\. **Attribute Starts/Ends/Contains Selector:**

* Example: Style links with an `href` attribute starting with "https".
    
    ```css
    a[href^="https"] {
      color: green;
    }
    ```
    

### Advanced Level:

#### 16\. **Sibling Combinator:**

* Example: Style all `<p>` elements that are preceded by a `<h2>`.
    
    ```css
    h2 ~ p {
      margin-top: 10px;
    }
    ```
    

#### 17\. **General Sibling Selector:**

* Example: Style all siblings of `<h2>` with the same parent.
    
    ```css
    h2 ~ * {
      font-style: italic;
    }
    ```
    

#### 18\. **Complex Selectors:**

* Example: Style odd rows in a table body but not the first row.
    
    ```css
    tbody tr:nth-child(odd):not(:first-child) {
      background-color: #f2f2f2;
    }
    ```
    

#### 19\. **Attribute Selectors with Regular Expressions:**

* Example: Style elements with a class containing "btn".
    
    ```css
    [class*="btn"] {
      background-color: lightblue;
    }
    ```
    

#### 20\. **Custom Data Attributes:**

* Example: Style elements with a `data-theme` attribute.
    
    ```css
    [data-theme="dark"] {
      color: white;
      background-color: black;
    }
    ```
    

#### 21\. **:nth-child() An+B Formula:**

* Example: Style every 3rd element starting from the 2nd child.
    
    ```css
    :nth-child(3n+2) {
      color: red;
    }
    ```
    

#### 22\. **:before and :after Pseudo-elements:**

* Example: Add a custom icon before each link.
    
    ```css
    a::before {
      content: "\2022"; /* Unicode for a bullet point */
      margin-right: 5px;
    }
    ```
    

#### 23\. **:first-child, :last-child, :only-child:**

* Example: Style the first paragraph in an article.
    
    ```css
    article p:first-child {
      font-weight: bold;
    }
    ```
    

#### 24\. **Complex Structural Selectors:**

* Example: Style the last three list items inside an unordered list.
    
    ```css
    ul li:nth-last-child(-n+3) {
      font-style: italic;
    }
    ```
    

#### 25\. **Custom Selectors (using CSS Variables):**

* Example: Use a CSS variable for dynamic styling.
    
    ```css
    :root {
      --main-color: blue;
    }
    
    .custom-box {
      border: 2px solid var(--main-color);
    }
    ```
    

### Practice and Application:

* Apply these selectors in real projects.
    
* Solve challenges on platforms like CodePen, JSFiddle, or online coding challenges.
    
* Explore browser developer tools to experiment with selectors on live websites.
    

Remember, becoming an expert requires hands-on practice and continuously challenging yourself with real-world scenarios. Stay curious and keep experimenting!

---