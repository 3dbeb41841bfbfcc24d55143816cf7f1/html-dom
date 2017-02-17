# Intro to HTML & the DOM

## Table of Contents
* [Learning Objectives](#learning-objectives)
* [Preparation](#preparation)
* [Differentation between HTML and DOM](#differentation-between-html-and-dom)
* [Introduction to HTML tags](#introduction-to-html-tags)
* [Creating a table in HTML](#creating-a-table-in-html)
* [Google Chrome Developer Tools](#google-chrome-developer-tools)
* [HTML 5 Tags](#html-5-tags)
* [Other Topics](#other-topics)
* [Additional Resources](#additional-resources)
* [Exercise #1](#exercise-#1)
* [Exercise #2](#exercise-#2)


## Learning Objectives
* Build a simple web page using HTML
* Explain the various parts of an HTML document, including:
  - the `<head>` and `<body>` tags
  - container elements such as `<div>`, `<header>`, `<footer>`, `<section>`, and `<article>`
  - common elements such as `<h1>`, `<h2>`, `<p>`, `<ul>`, and `<li>`
* Explain the difference between _HTML_ and the _DOM_

## Preparation
- Pre-work and About Me page completion

## Hook (5m)
This morning we're gonna take a look at the DOM and how we can use the Chrome Dev Tools to manipulate and test it out. This afternoon we'll use more advanced ways to perform DOM manipulation using Javascript.

<details>
<summary>To start, can someone describe the difference between HTML and the DOM in their own words?</summary>
The DOM (Document Object Model) is the browser's intrepretation of the HTML. Your browser creates objects out of the HTML elements.

examples: 

- skeleton => HTML, body => DOM
- song chords, lyrics => HTML, recorded song => DOM
- recipe ingredients => HTML, finished dish => DOM

</details>


**WE DO:** Goto [Kickass App](http://kickassapp.com/) and use it. What is happening?


We're gonna get into DOM manipulation later in the week, but to demonstrate the difference between an _HTML_ document and the _DOM_ that is created from the _HTML_ document, let's go to the [Jezebel](http://jezebel.com/) web site and play around with some headlines.

Using the Chrome DevTools Inspector, alter something on the page.


**YOU DO** Go to [Atlanta Craigslist](https://atlanta.craigslist.org/) and try running the following `javascript` DOM manipulation code in the JavaScript console:

```javascript
document.getElementById('logo').children[0].text = 'MarensList';
document.getElementsByClassName('ban')[0].children[0].text = 'WDI Rocks!'
```

Questions:

<details>
<summary>Did I just hack Craigslist?</summary>
No. We manipulated the DOM, or what existed in the browser's memory.
</details>
<details>
<summary>What happens if I refresh the page?</summary>
All of your changes will disappear.  
</details>
<details>
<summary>What are we actually changing - the HTML or the DOM?</summary>
You are changing the DOM.  The developers at Craigslist will not be worried that their site is now called 'MarensList'.
</details>

<br />

---

## **YOU DO**
- 5 min - Read this article on the difference between HTML and the DOM from [CSS Tricks](https://css-tricks.com/dom/) 
- 5 min - Pair and Share - discuss what you learned with your partner
- 5 min - Ask each group for something they learned in the article

<br />

---

## Let's Differentiate between HTML and the DOM

* **HTML**: the language we use to create an HTML Page/Document
* **DOM**: the Document Object Model, i.e. the in-memory representation of the HTML page, that is created every time the browser _renders_ the HTML document.

**Note**: the _DOM_ can be _manipulated_ via _JavaScript_ code.  And we will discuss this in further detail next week.

<br />

### What is HTML?
**HTML** stands for "Hyper Text Markup Language". It is not a general purpose programming language like *JavaScript* or _Ruby_ but rather a **markup language**, i.e. a language for representing structured text.

To create any website, you need HTML, CSS and JavaScript.  While CSS provides the style and color for a site, and JavaScript allows interaction with the end user, HTML creates the skeleton of a website. It is the *structured content*.

![Anatomy of an HTML Document](images/anatomy-of-an-html-doc.jpg)

The `<head>` section is for metadata, which gives the browser information about the site.  Inside of the head, we would add the title of our website- which is what you see in the browser tab, any link tags to css pages.     

The `<body>` section is for the visible content on a web page.  As well as our JavaScript `<script>` tags.

```html
<!doctype html>
<html>
  <head>
    <!-- document metadata goes here. -->
  </head>
  <body>
    <!-- document contents go here. -->
  </body>
</html>
```

<br />

### What is the DOM?

- A browser receives a page as HTML and creates a **Document Object Model** (a.k.a. the DOM tree) that it stores in memory.

![DOM Tree](images/dom_tree.gif)

- The DOM has properties, methods and events.
- Each DOM **element** is an object, and may be accessed and modified independent of any other content.
- The DOM is a `tree`-like structure or data structure, similar to an outline, that consists of parent and child nodes that represent each element on our site.

- In the console, type `document.` and check out the available methods.
- In the console, type `document.title`.
  <detail>
    <summaryWhat do you expect to see?</summary>
    The `document.title` is going to output the title of the website, or what you see in your browser tab.
  </detail>
- In the console, type `document.body.children[5]`.
  - This will show highlight main content div of our webpage, and we can narrow it down further/highlight other content from there.

#### **WE DO**
- Go to Jezebel.
- In the console, type `document.getElementsByClassName('headline')[0];`
  - We will discuss this more later, but getElementsByClassName, returns an array/list of items with that class.  Arrays are zero-indexed, which means that they start with zero, so we need to add that number in square brackets to highligh the first title. 
  - This will highlight the first news title on the page.
- Update that title to have the id="first-title"
  - The funny thing is that Jezebel doesn't really use ids, so in order to access and Id, we need to take the initiative to add it ourselves.
- In the console, type `document.getElementById('first-title');`
  - This statement will also highlight the first news title on the page, but in a different way.

- As with our earlier Jezebel example, you can change the HTML in the inspector but when you re-render the page, the changes are gone. Try `document.write('WDI Rocks!!!')`. (Traditionally, you only use document.write for testing purposes because you don't have any control over where it renders on the page, and it overwrites everything else).

<br />

## What is the Window Object?

- Represents the window that is open in the browser.
- Location property is the URL of the page.
- In the console, type `window.` and check out the available methods.
- In the console, type `window.location`.
  <details>
    <summary>What do you expect to see?</summary>

  </details>
- In the console, type `window.document.write('Hello')`.
  <details>
    <summary>Knowing what happened before, what do you expect this statement to do?</summary>
  </details>

## HTML vs. DOM Vocabulary

| HTML          | DOM           |  Example                              |
|:-------------:|:-------------:|:------------------------------------- |
| tag / element | node          | `<p>This is a paragraph</p>`          |
| attribute     | property      | `<a href="www.google.com">Google</a>` |

## Introduction to HTML tags

**YOU DO**

Consider using the [HTML Practice Exercise](https://github.com/ATL-WDI-Exercises/html-dom/blob/master/html_practice_exercise.md) to have each student build a page in 15-ish min. Then, choose a student to demo what they built as you guide them through the review notes below.

### Basic Structure of an HTML Document

* `<!DOCTYPE html>` -> informs the browser that this file is an HTML file
* `<html>...</html>` -> contains your html content - it will tell the browser that everything within these tags should be interpreted as HTML.

When opening a new html file, it is important to include a `head` section.

```html
<head>
  <title>Page's title</title>
  <meta name="description" content="...">
  <meta name="keywords">
</head>
```

The `head` is important for search engines, as it helps provide additional information about the website. Anything within the `<head>` and `</head>` tags will NOT be displayed on the page.

We place these tags right after the opening `<html>` tag, and before the opening `<body>` tag.


## Common HTML Elements

### Meta Tags

| Element        | Description                                               |
|:-------------- |:--------------------------------------------------------- |
| `<link>`       | used to load a CSS file - it is self closing. |
| `<script>`     | used to load a JavaScript file or for embedding JavaScript code. |

### Containers

| Element        | Description                                               |
|:-------------- |:--------------------------------------------------------- |
| `<head>`       | contains metadata about the page, including the title, links to external stylesheets, js files, google fonts, etc, and other meta tags. |
| `<body>`       | contains the body of the page we will display. |
| `<div>`        | a container used for grouping child elements. DIVs are _block_ elements that take up the whole width of the page unless specific style is applied to them to do otherwise. They can contain paragraphs, headings, text, images, other divs, etc. They work as a way to structure the page with clearly delimited blocks. |
| `<ul>...</ul>` | an unordered list (bullet points) of `<li>` elements |
| `<ol>...</ol>` | an ordered list (numbered) of `<li>` elements |

### Content

| Element       | Description                                               |
|:------------- |:--------------------------------------------------------- |
| `<p>...</p>`   | a simple paragraph |
| `<span>...</span>`  | inline element, allows us to isolate a bit of text and apply a style to it using CSS (more on this later). |
| `<h1>...</h1>` | Level 1 heading |
| `<h2>...</h2>` | Level 2 heading |
| `<h3>...</h3>` | Level 3 heading |
| `<h4>...</h4>` | Level 4 heading |
| `<h5>...</h5>` | Level 5 heading |
| `<h6>...</h6>` | Level 6 heading |
| `<li>...</li>` | elements to be put within the ordered/unordered list tags |
| `<img src="url" alt="description" /> ` | image tag. This is a self-closing tag, meaning you don't need a closing </img> tag. It should include the source of the file (can be a url or a file path) and a description (alt) for the search engines.
| `<a href="url">...</a>` | hyperlink to another page; needs to include an href which is the url it is linking to. You can add a `target="_blank` which will open the link in a new tab in the browser. We can also wrap images within `<a>` tags to transform it into a link.

#### Example of an Anchor containing an Image

```html
<a href="www.w3.org" target="_blank">
  <img src="http://www.misiide.net/images/2013/03/Tim-Berners-Lee.jpg" alt="A picture of Tim Berners-Lee!" />
</a>
```

The `href` above makes the image "clickable" and redirects to the W3 website.


### Styled Text

These tags can be used to set a specific style to text in an HTML document.

> NOTE: You should usually avoid these tags as it is better to use CSS for styling content.

| Element       | Description                                               |
|:------------- |:--------------------------------------------------------- |
| `<b>...</b>`  | makes the wrapped text bold |
| `<strong>...</strong>` | a bit similar to bold, the browser interprets this as an important bit of text, and will direct the reader's attention to it. |
| `<i>...</i>`  | makes the wrapped text italic. |
| `<em>...</em>` | a bit similar to italic, used by the browser to add emphasis on a word. |
| `<br />`       | self-closing tag, allowing you to break the content (CSS will allow us to achieve the same result, in a better way). |

## Creating a table in HTML

We can use the `<table>` tags to display tabular data.

Table-specific tags:

| Element       | Description                                               |
|:------------- |:--------------------------------------------------------- |
| `<table>...</table>`  | contains the table data, and defines the table structure |
| `<thead>...</thead>`  | the head of the table (bolder text) - optional
| `<tr>...</tr>` | defines a row
| `<th>...</th>` | defines a cell within that row
| `<tbody>...</tbody>` | the body of the table


Example:

```html
  <table border="1">
    <thead>
        <tr>
          <th>Date</th>
          <th>Weight</th>
          <th>Distance walked</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>September 15</td>
          <td>75 kg</td>
          <td>1.8 km</td>
        </tr>
        <tr>
          <td>September 29</td>
          <td>73 kg</td>
          <td>2.1 km</td>
        </tr>
      </tbody>
  </table>
```

In our browser, we get:

Date | Weight | Distance Walked
-----|--------|-----------------
September 15 | 75 kg |1.8 km
September 29 |73 kg | 2.1 km

> REMEMBER: Don't use tables to define the layout of a page! This is a very old and outdated technique that results in a poor overall design that is not easily styled with CSS and is not *responsive* to varying screen sizes.

---

## HTML Cheatsheet

![Anatomy of an HTML Document](images/html-cheat-sheet-v1.png)

---

## Google Chrome Developer Tools

Let us have a quick first look at **Chrome Developer Tools**. Available as a console in Google Chrome, it allows us to get a lot of information about the page we're on, providing a detailed look into the HTML structure of the page and the CSS styling, among other things.

In Chrome, you can access it with:
  - `Cmd+Alt+i` on a Mac
  - `Ctrl + Shift + C` or `F12` on Windows or Linux
  - right-click on the browser and click on "Inspect element"

As of now, let's mainly look at the "Elements" tab -> it's a very powerful way to look at the page structure, and locate specific elements within the page.

You can also gain some useful information on all of the elements by looking at the data on the right column of the console, most notably the CSS properties currently applied to the elements... and change them "live" (these changes, however, only apply to the page as displayed - it will not be saved in your CSS file, and all these changes disappear on the next page reload).

We will get to play with this functionality more as we dig deeper into the CSS chapter.

---

## HTML 5 Tags

See [HTML5 New Elements](http://www.w3schools.com/html/html5_new_elements.asp)

---

## Other Topics

For information on accessibility and search engine optimization, see [Accessibility and SEO](accessibility-and-seo.md).

For information on HTML5 Boilerplate, see [HTML5 Boilerplate](html5-boilerplate.md).

---

## Additional Resources

* [Online HTML live editor](https://thimble.webmaker.org/en-US/projects/wrangler/)
* [HTML element reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
* [HTML Elements by Category](http://www.w3schools.com/tags/ref_byfunc.asp)
* [HTML5 element reference](https://developer.mozilla.org/en/docs/Web/Guide/HTML/HTML5/HTML5_element_list)
* [Tim Berners-Lee](http://www.w3.org/People/Berners-Lee)
* [Evolution of the Web - Great Link](http://www.evolutionoftheweb.com/)
* [Stack Overflow: What is the difference between Section and Div](http://stackoverflow.com/questions/6939864/what-is-the-difference-between-section-and-div)
* [HTML5 Doctor](http://html5doctor.com/)
* [HTML5 Validator](http://html5.validator.nu/)
* [Semantic HTML](http://en.wikipedia.org/wiki/Semantic_HTML)
* [CSS Tricks](https://css-tricks.com/dom/)

---

## Exercise #1

Using HTML tags only (don't worry about CSS), use the starter code below to recreate the Document Outline for the following website:

[How We Use Energy](http://needtoknow.nas.edu/energy/energy-use/)

* [Starter Code](https://github.com/ATL-WDI-Exercises/html-dom/blob/master/energy_dom_outline/energy_document_outline.html)
* [Finished Code](https://github.com/ATL-WDI-Exercises/html-dom/blob/master/energy_dom_outline/energy_document_outline_fin.html)

## Exercise #2

Clone your HTML/DOM repo and work on the [Busy Hands](https://github.com/ATL-WDI-Exercises/busy-hands) exercise.
