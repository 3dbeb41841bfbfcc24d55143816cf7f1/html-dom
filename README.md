
# Intro to HTML & the DOM

####Objectives:
- Student will demonstrate the ability to use HTML to create a document.
- Student will understand the difference between HTML and the DOM

####Relation to Big Goal
- As full-stack developers we need to be familiar with HTML and the DOM.

###Hook
Using Inspector, alter a webpage to add a funny headline using Gerry as an example.

OR

Goto Atlanta Craigslist and walk though setp by step: `document.getElementsByClassName('ban')[0].innerHTML = "MARC!"`


###HTML and DOM Definition and Overview
WE DO: 

- Instructor holds up a newspaper. Asks students to identify the various parts/sections.
- HTML would be the individual elements (recipe), DOM is what's rendered in the browser (fully baked recipe)
- The idea is to start seeing the structure of a page instead of the content only.

What is the Window Object?

- Each browser window or tab
- Location property is the URL of the page.
- In the console, type `window.` an check out the available methods.
- Demo `window.location`. Also, point out local storage.


What is the DOM?

**DOM Tree:**

![DOM Tree](http://www.webstepbook.com/supplements/slides/images/dom_tree.gif)

- Document Object Model or the DOM tree
- The current broswer page is the DOM and everything is an object.
- Defines structure for all content within the document.
- The DOM has properties, methods and events that each browser implements in the same way.
- When we get to js there's document.load
- Each "element" is an object, and may be accessed and modified independently of other content.
- Inspectible using the web inspector.
- Defines a heirarchy for all content elements in the document.
- In the console, type `document.` and check out the available methods.
- Demo `document.lastModified` and `document.title`. Point out that you can't do this for the Window Object.
- Demo get element by class or id.

YOU DO:
- Have the class play with calling elements.

What does HTML stand for?

- HTML stands for "Hyper Text Markup Language". It is not a programming language, as it doesn't send any instruction to your computer. However, it does send instructions to the browser (Chrome, Firefox, Safari, etc.), telling it what to display on the screen. 
- A browser receives a page as HTML and creates a model and stores it in memory creating a DOM tree.
- DEMO: You can change the HTML in the inspector but when you re-render the changes are gone. Try `document.write('MARC')`
- The skeleton of a website. It is nothing more than *structured content*. HTML is inherently logicless, therefore, it is NOT CODE (it's content).




###Let's walk through some HTML Tags
(Consider using the `html_practice_lab.md` to have each student build a page in 15-ish min using git commits and GitHub. Then, choose a student to demo what they built as you guide them through the review notes below.)

WE DO:

- In your "classwork" folder:   

`$ mkdir html`  
`$ cd html `  
`$ touch demo_1.html`  
`$ subl demo_1.html`  

```
  <!DOCTYPE html>
  <html>
  	<head>
      <title>Page's title</title>
      <meta name="description" content="...">
      <meta name="keywords">
  	</head>
  	<body>
      <h1>My first webpage!</h1>
      <p>Hello, world!</p>

      <p>
        This word is <b>bold</b>.
      </p>

      <p>This word is <i>italic</i>.</p>
      
      <strong>This is strong</strong>

      <h2>Lists</h2>

      <h3>Ordered list</h3>
        <ol>
          <li>Call mom</li>
          <li>Buy milk</li>
        </ol>

      <h3>Unordered list</h3>
        <ul>
          <li>Apple</li>
          <li>Orange</li>
        </ul>
      
      <img src="http://www.misiide.net/images/2013/03/Tim-Berners-Lee.jpg" alt="A picture of Tim Berners-Lee!" />   

      <a href="http://www.google.com" target="_blank">Google</a>

    </body>
  <html>
```

## HTML Tags

YOU DO:

Pair up and have them look up the following tags below:


`<!DOCTYPE html>` -> informs the browser that this file is an HTML file

`<html>...</html>` -> contains your html content - it will tell the browser that everything within these tags should be interpreted as HTML.


#### Introduction to `head` tags


When opening a new html file, it is important to include a "head".

```
  <head>
      <title>Page's title</title>
      <meta name="description" content="...">
      <meta name="keywords">
  </head>
```

The "head" is important for search engines, as it helps provide additional information about the website. Anything within the <head> tags will NOT be displayed on the page. 

We had these tags right after the opening `<html>` tag, and before the opening `<body>` tag.

It is important to mention that `<meta>` "content" and "keywords" are outdated HTML elements, and most recent webpages don't use them anymore.
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

```  
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

```
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

REMEMBER: Don't use tables to define the layout of a page! 



## Google Chrome Developer Tools

Let us have a quick first look at **Chrome Developer Tools**. Available as a console in Google Chrome, it allows us to get a lot of information about the page we're on, providing a detailed look into the HTML structure of the page and the CSS styling, among other things. 

In Chrome, you can access it with `Cmd+Alt+i`, or right-click "Inspect element".

As of now, let's mainly look at the "Elements" tab -> it's a very powerful way to look at the page structure, and locate specific elements within the page.

You can also gain some useful information on all of the elements by looking at the data on the right column of the console, most notably the CSS properties currently applied to the elements... and change them "live" (these changes, however, only apply to the page as displayed - it will not be saved in your CSS file, and all these changes disappear on the next page reload). 

We will get to play with this functionality more as we dig deeper into the CSS chapter. 

------

#HTML5 Boilerplate

Background:

[HTML5 Boilerplate](http://html5boilerplate.com/) was created by Paul Irish and Divya Manian and is an open source project that is perfect for creating HTML ready cross-browser sites that work with older browsers, including IE.

A tool know as [Modernizr](http://modernizr.com/) is included in order to allow you to style the new HTML5 elements in IE and helps with detecting HTML5 or CSS3 features in all browsers, including earlier versions of IE (before v9).

It I mention it helps with IE?

Why should you care:

Here's some of what it can do:

![Why it is awesome](http://www.paulirish.com/wp-content/uploads/2010/08/html5boilerplate_ss.png)

To be clear, HTML5 Boilerplate is **not a framework**. It's a template that can be modified and used for your own projects. You can use as much or as little as you want and make your own additions and subtractions. Still, it's one of the most robust and well-commented starting points we've seen for setting up a solid HTML5 base for your projects.

used to have to use divs with classes and ids for descriptions.

Includes many confusing new "semantic" tags. These tags are (ironically) subjective regarding their content roles, and thus invalidate their own value as content identifiers:

####section
	great container to how this is a grouping and all nested elements belong to one section
	
	a thematic grouping of content

	Why is section preferred over div? Holds more info, used for grouping, a div has no special meaning 

Helpful links:

http://stackoverflow.com/questions/6939864/what-is-the-difference-between-section-and-div
	
http://html5doctor.com/

http://html5.validator.nu/
####article
	is content that makes sense on its own (e.g.- weblog)

####header
	Defines a header for the document or a section 

####Others	
- `<section>`
- `<article>`
- `<header>`
- `<footer>`
- `<nav>`
- `<main>`
- `<aside>`
- `<address>`
- `<cite>`

Includes several new form input types, as well as several new form attributes that target mobile platforms:

- `<input type="number">`
- `<input type="slider">`
- `<input type="date">`

HTML5 includes many new multimedia-oriented tags. These tags were largely motivated by the decline of Flash, so provide new browser-native multimedia capabilities:

- `<canvas>`
- `<video>`
- `<audio>`


----

## Exercise/Lab #1 option 1
Write an [HTML page](https://github.com/ATL-WDI-Exercises/html-dom/blob/master/html_practice_exercise.md) from scratch -> post-WDI future

Requirements:
  
  - valid HTML5  
  - internal link  
  - external link (opens in new window/tab)  
  - image   
  - link email address   opens standard mail-client and populated :to field (subject: "Your site is awesome") 
  
## Exercise/Lab #1 option 2
For those that still have their About Me page (or the above post-WDI future page)- convert it to an HTML 5 template
	

## Exercise/Lab #2

Compose the Document Outline for…
[How We Use Energy](http://needtoknow.nas.edu/energy/energy-use/)

[LAB](https://github.com/marcwright/WDI_ATL_1_Instructors/tree/master/REPO%20-%20DC%20-%20Instructors/w04/d01/document_outline)

[Finished](file:///Users/marcwright/WDI_ATL_1_Instructors/REPO%20-%20DC%20-%20Instructors/w04/d02/document_accessibility/accessibility_fin.html)

## Exercise/Lab #3

[Busy Hands](https://github.com/ga-students/WDI_ATL_2_Instructors/tree/master/Lessons/html_dom/busy_hands_html_dom_lab)

----
## Web Accessibility / SEO

### Concepts
- Define some common content accessibility considerations.
- Explain what the Document Outline is, and why it's important.
- Define what Section 508c is, and explain common requirements that address it.
- Define what WCAG is, and explain common requirements that adddress it.
- Define what ARIA roles are, and what they're used for.
- Explain image "alt" texts, and what they're used for.
- Explain cross-browser compatibility, and name a few major concerns.
- Explain what SEO is, and why it's important.
- Explain what the document `<title>` tag is, and why it's important.

### Mechanics
- Create an HTML document outline based on content heirarchy.
- Configure ARIA roles on major content divisions.

## Accessibility

[Screen Reader](https://www.youtube.com/watch?v=KFPtxCDUPqs)

* 0:00 - H1
* 0:24 - bullet, links
* 1:00 - H2
* 1:17 - image

### ARIA Roles

**Accessible Rich Internet Applications**

Roles may be assigned to any tag. They're typically added to block-level elements to denote the role of the block's internal content.

```
 <div role="banner">Welcome to my website!</div>
```

**Common roles**

- `"banner"` : The page header block.
- `"navigation"` : A region of major site navigation.
- `"search"` : The region containing the site's search form.
- `"main"` : The main content region of the page.
- `"complementary"` : A region that complements the main (ie: a sidebar)
- `"contentinfo"` : The page footer.

----


##ADDITIONAL RESOURCES

HTML:

* Online HTML live editor: <https://thimble.webmaker.org/en-US/projects/wrangler/>
* HTML element reference: <https://developer.mozilla.org/en-US/docs/Web/HTML/Element>
* HTML5 element reference: https://developer.mozilla.org/en/docs/Web/Guide/HTML/HTML5/HTML5_element_list
* Tim Berners-Lee: <http://www.w3.org/People/Berners-Lee/>
* Evolution of the Web: <http://www.evolutionoftheweb.com/> (you'll love it)
* Semantic HTML: <http://en.wikipedia.org/wiki/Semantic_HTML>
