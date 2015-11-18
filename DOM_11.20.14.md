##Intro to The DOM

- Have a basic understanding of what the DOM is and how JavaScript interacts with it
- Access properties belonging to the document object
- Use document methods to access elements
        - getElementsByTagName
        - getElementById
        - getElementsByClassName
- Manipulate elements and styling using JavaScript 


DOM is:

The Document Object Model (DOM) is an application programming interface (API) for valid HTML and well-formed XML documents. 

DOM: 

- Defines the logical structure of documents and the way a document is accessed and manipulated.

- The HTML you write is parsed by the browser and rendered into the DOM


**DOM Tree:**

![DOM Tree](http://www.webstepbook.com/supplements/slides/images/dom_tree.gif)

**Family Tree:**

![family tree](http://www.yangfamilytaichi.com/yang/tree/images/familytree.jpg)


Activity (5 minutes):

**Draw a DOM Tree**

	<html>
	
		<head>
		
			<title>Webpage</title>
			
		</head>
		
		<body>
		
			<div>
			
				<section>
					
					<p>Hi I'm a paragraph</p>

					<a href="#">Hi I'm a link</a>					
					
				</section>
				
				<article>
				
					<p>Hi I'm a paragraph</p>				
					
					<a href="#">Hi I'm a link</a>
					
				</article>
				
			</div>
			
		</body>
		
	</html>
	
	

###When is the DOM different than HTML?

If you have mistakes in your HTML, and the browser has fixed them for you.


If you have a table element and leave out the tbody. It'll exist in the DOM but not the HTML

###JavaScript can manipulate the DOM

Imagine if you have an empty div element like this:

	<div id="container"></div>

Use JavaScript to change the #container value:

	<script>
		
		var container = document.getElementById("container");
		
		container.innerHTML = "New Content";
		
	<script>


Which is different than your original HTML or what you would see in View Source!

Activity: Do the getElementById 
Activity: Students will 

- Create a paragraph with the words "Change me!"
- Use document.getElementById to change the paragraph's words to "I'm changed!"

###Document.getElementsByClassName
Name returns an array-like object of all child elements which have all of the given class name. 


**Activity two**
- Create 4 span tags

- Change the background color of the 3rd span to blue


###document.getElementsByTagName

Returns an HTMLCollection of elements with the given tag name. 

The complete document is searched, including the root node. 

The returned HTMLCollection is live, meaning that it updates itself automatically to stay in sync with the DOM tree without having to call


###Activity:

- Use getElementsByTagName to get the number of spans in the page







	