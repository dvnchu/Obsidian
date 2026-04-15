
[[web]]
Websites are primarily created using:

- HTML, to build websites and define their structure
- CSS, to make websites look pretty by adding styling options
- JavaScript, implement complex features on pages using interactivity
# HTML
HyperText Markup Language is the language websites are written in.
![[Pasted image 20251219173503.png]]


The HTML structure (as shown in the screenshot) has the following components:

- The `<!DOCTYPE html>` defines that the page is a HTML5 document. This helps with standardisation across different browsers and tells the browser to use HTML5 to interpret the page.
- The `<html>` element is the root element of the HTML page - all other elements come after this element.
- The `<head>` element contains information about the page (such as the page title)
- The `<body>` element defines the HTML document's body; only content inside of the body is shown in the browser.
- The `<h1>` element defines a large heading
- The `<p>` element defines a paragraph
- There are many other elements (tags) used for different purposes. For example, there are tags for buttons (`<button>`), images (`<img>`), lists, and much more.


Tags can contain attributes. An element can have multiple attributes each with its own unique purpose, e.g., <p attribute1="value1" attribute2="value2">.

Elements can also have an id attribute (`<p id="example">`), which is unique to the element. Element id's are used for styling and to identify it by JavaScript.

You can view the HTML of any website by right-clicking and selecting "View Page Source" (Chrome) / "Show Page Source" (Safari).

## JS
JavaScript is used to control the functionality of web pages - without JavaScript, a page would not have interactive elements and would always be static.

JavaScript is added within the page source code and can be either loaded within `<script>` tags or can be included remotely with the src attribute: `<script src="/location/of/javascript_file.js"></script>`

inds a HTML element on the page with the id of "demo" and changes the element's contents to "Hack the Planet" : `document.getElementById("demo").innerHTML = "Hack the Planet";`

HTML elements can also have events, such as "onclick" or "onhover"

`<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button>`
