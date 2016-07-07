# Intro to HTML & the DOM

### Learning Objectives
* Build a simple web page using HTML
* Explain the various parts of an HTML document, including:
  - the `<head>` and `<body>` tags
  - container elements such as `<div>`, `<header>`, `<footer>`, `<section>`, and `<article>`
  - common elements such as `<h1>`, `<h2>`, `<p>`, `<ul>`, and `<li>`
* Explain the difference between _HTML_ and the _DOM_

### Preparation
- Pre-work and About Me page completion

## Differentation between HTML and DOM

_HTML_: the language we use to create an HTML Web Page / Document
_DOM_: the Document Object Model, i.e. the in-memory representation of the HTML page created when the browser _renders_ the HTML document.

Note that the _DOM_ can be _manipulated_ via _JavaScript_ code.

### Hook (5 min)
We're gonna get into DOM manipulation later in the week, but to demonstrate the difference between an _HTML_ document and the _DOM_ that is created from the _HTML_ document, let's go to the [ESPN](http://espn.go.com/) web site and play around with some headlines.

Using the Chrome DevTools Inspector, alter something on the page.

Then go to [Atlanta Craigslist](https://atlanta.craigslist.org/) and try running the following `javascript` DOM manipulation code in the JavaScript console:

```javascript
document.getElementById('logo').children[0].text = 'MikesList';
document.getElementsByClassName('ban')[0].children[0].text = 'WDI Rocks!'
```

Questions:

- Did I just hack Craigslist?
- What happens if I refresh the page?
- What am we actually changing- the HTML or the DOM?


### What is HTML?
HTML stands for "Hyper Text Markup Language". It is not a general purpose programming language like JavaScript or Ruby but rather a _markup_ language, i.e. a language for representing structured text.

HTML is the skeleton of a website. It is the *structured content* of the website.

![Anatomy of an HTML Document](images/anatomy-of-an-html-doc.jpg)

The `<head>` section is for metadata and the `<body>` section is for the visible content of the web page.

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

### What is the DOM?

- A browser receives a page as HTML and creates a model and stores it in memory creating a Document Object Model (a.k.a. the DOM tree).

![DOM Tree](images/dom_tree.gif)

- The DOM has properties, methods and events.
- Each DOM "element" is an object, and may be accessed and modified independently of other content.
- The DOM is a `tree` data structure consisting of parent and child nodes.
- In the console, type `document.` and check out the available methods.
- Demo `document.title` and `document.body.children[0]`.
- Demo get element by class or id or tagname.
- As with our earlier ESPN example, you can change the HTML in the inspector but when you re-render the changes are gone. Try `document.write('WDI Rocks!!!')`

What is the Window Object?

- Each browser window or tab
- Location property is the URL of the page.
- In the console, type `window.` an check out the available methods.
- Demo `window.location` and `window.document.write('Hello')`.
- Also, point out `localStorage`.

## Introduction to HTML tags

**YOU DO: Option 1**

Consider using the [HTML Practice Exercise](https://github.com/ATL-WDI-Exercises/html-dom/blob/master/html_practice_exercise.md) to have each student build a page in 15-ish min. Then, choose a student to demo what they built as you guide them through the review notes below.

**YOU DO: Option 2**

Pair up and have students look up the following tags below:

`<!DOCTYPE html>` -> informs the browser that this file is an HTML file

`<html>...</html>` -> contains your html content - it will tell the browser that everything within these tags should be interpreted as HTML.

When opening a new html file, it is important to include a "head".

```html
<head>
  <title>Page's title</title>
  <meta name="description" content="...">
  <meta name="keywords">
</head>
```

The "head" is important for search engines, as it helps provide additional information about the website. Anything within the <head> tags will NOT be displayed on the page.

We had these tags right after the opening `<html>` tag, and before the opening `<body>` tag.

> It is important to mention that `<meta>` "content" and "keywords" are outdated HTML elements, and most recent webpages don't use them anymore.

`<head>...</head>`    -> contains the title, links to external stylesheets, js files, google fonts, etc, and meta tags.

`<body>...</body>`    -> contains the body of the page we will display.

`<p>...</p>`   -> paragraph

`<b>...</b>`   -> makes the wrapped word/text bold - prefer to avoid this tag due to it offering presentation rather than semantic meaning

`<strong>...</strong>`  -> a bit similar to bold, the browser interprets this as an important bit of text, and will direct the reader's attention to it.

`<i>...</i>`      -> makes the wrapped word/text italic - prefer to avoid this tag due to it offering presentation rather than semantic meaning

`<em>...</em>`    -> a bit similar to italic, used by the browser to add emphasis on a word.

`<h1>...</h1>` to` <h6>...</h6>` -> headings, from big to small

`<ul>...</ul>`    -> unordered list (bullet points)

`<ol>...</ol>`    -> ordered list (numbered)

`<li>...</li>`    -> elements to be put within the ordered/unordered list tags

`<br />`        -> self-closing tag, allowing you to break the content (CSS will allow us to achieve the same result, in a better way).

`<img src="url" alt="description" /> `-> image tag. This is a self-closing tag, meaning you don't need a </img> tag. It should include the source of the file (can be a url or a file path) and a description (alt) for the search engines.

`<link>` -> self closing

`<a href="url">...</a>` -> link to another page; needs to include a href, which is the url it is linking to. You can add a `target="_blank` which will open the link into a new tab in the browser. We can also wrap images within `<a>` tags to transform it into a link.

In our code example above:

```html
<a href="www.w3.org" target="_blank">
  <img src="http://www.misiide.net/images/2013/03/Tim-Berners-Lee.jpg" alt="A picture of Tim Berners-Lee!" />
</a>
```

Add the href above to make this makes the image "clickable", and redirects to the W3 website.

`<span>...</span>`  -> inline element, allows us to isolate a bit of text and apply it a style with CSS (we'll see this later on today). SPAN elements take only the space they need on the page, as opposed to DIV elements.

`<div>...</div>`    -> block element, these elements take up the whole width of the page, unless specific style is applied to them with CSS. They can contain paragraphs, headings, text, images, other divs, etc. They work as a way to structure the page with clearly delimited blocks.


## Creating a table in HTML

We use the `<table>` tags to display tabular data.

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
        <tr>
        <tr>
          <td>September 29</td>
          <td>73 kg</td>
          <td>2.1 km</td>
        <tr>
      </tbody>
  </table>
```

In our browser, we get:

Date | Weight | Distance Walked
-----|--------|-----------------
September 15 | 75 kg |1.8 km
September 29 |73 kg | 2.1 km

Table-specific tags:

`<table>...</table>`  -> contains the table data, and defines the table structure
`<thead>...</thead>`  -> the head of the table (bolder text) - optional
`<tr>...</tr>`    -> defines a row
`<th>...</th>`    -> defines a cell within that row
`<tbody>...</tbody>`  -> the body of the table

> REMEMBER: Don't use tables to define the layout of a page! This is a very old and dated technique that results in a poor overall design that is not easily styled with CSS.

## Google Chrome Developer Tools

Let us have a quick first look at **Chrome Developer Tools**. Available as a console in Google Chrome, it allows us to get a lot of information about the page we're on, providing a detailed look into the HTML structure of the page and the CSS styling, among other things.

In Chrome, you can access it with `Cmd+Alt+i`, or right-click "Inspect element".

As of now, let's mainly look at the "Elements" tab -> it's a very powerful way to look at the page structure, and locate specific elements within the page.

You can also gain some useful information on all of the elements by looking at the data on the right column of the console, most notably the CSS properties currently applied to the elements... and change them "live" (these changes, however, only apply to the page as displayed - it will not be saved in your CSS file, and all these changes disappear on the next page reload).

We will get to play with this functionality more as we dig deeper into the CSS chapter.

---

## Other Topics

For information on accessibility and search engine optimization, see [Accessibility and SEO](accessibility-and-seo.md).

For information on HTML5 Boilerplate, see [HTML5 Boilerplate](html5-boilerplate.md).

---

## HTML 5 Tags

See [HTML5 New Elements](http://www.w3schools.com/html/html5_new_elements.asp)

---

## Additional Resources

* [Online HTML live editor](https://thimble.webmaker.org/en-US/projects/wrangler/)
* [HTML element reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
* [HTML5 element reference](https://developer.mozilla.org/en/docs/Web/Guide/HTML/HTML5/HTML5_element_list)
* [Tim Berners-Lee](http://www.w3.org/People/Berners-Lee)
* [Evolution of the Web - Great Link](http://www.evolutionoftheweb.com/)
* [Stack Overflow: What is the difference between Section and Div](http://stackoverflow.com/questions/6939864/what-is-the-difference-between-section-and-div)
* [HTML5 Doctor](http://html5doctor.com/)
* [HTML5 Validator](http://html5.validator.nu/)
* [Semantic HTML](http://en.wikipedia.org/wiki/Semantic_HTML)

---

## Exercise #1

Using HTML tags only (don't worry about CSS), use the starter code below to recreate the Document Outline for the following website:

[How We Use Energy](http://needtoknow.nas.edu/energy/energy-use/)

* [Starter Code](https://github.com/ATL-WDI-Exercises/html-dom/blob/master/energy_dom_outline/energy_document_outline.html)
* [Finished Code](https://github.com/ATL-WDI-Exercises/html-dom/blob/master/energy_dom_outline/energy_document_outline_fin.html)

## Exercise #2

Clone your HTML/DOM repo and work on the [Busy Hands](https://github.com/ATL-WDI-Exercises/busy-hands) exercise.

