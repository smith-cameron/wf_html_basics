# HTML Intro
[**Course Expectations**](https://docs.google.com/presentation/d/1vuLJmJPTUZIt7tJzrRh17pAlZFZdqIsPHz1GQmPTEWc/edit#slide=id.g2f6c619ba3a_0_30)<br>

**Hypertext Markup Language**<br>
Its purpose is to let us communicate with the browser the **structure** of the **content** that we wish to place on a web page.
## [How the Web Works](https://login.codingdojo.com/m/283/8966/60776)
- **Clients** - computers and other internet-connected devices that use the internet
- **Servers** - computers/machines that store web pages or applications
### Request Response Cycle
Clients(i.e.  you using your browser) makes a **request** and the server answers back with a **response**<br>
#### **REQUESTS**
- typing a URL in the address bar of our browser,
- clicking on a link,
- submitting a form, or
- refreshing a page.
- **...What could be some everyday requests that don't require a browser?**

#### **RESPONSE**
The server responds with some kind of content to the client as some combination of HTML, CSS, and JavaScript.<br>
As web developers we are creating **responses**.<br>
Tn Web Fundamentals we will focus on **browser content**.
## HTML TAGS
**Difference between tags and elements?**

**elements** specify different types/sections of content.The syntax for indicating the type of element is with **tags**.

The browser uses the tags to interpret the content. This implies structure and often some default styling.
- Headings `<h1> - <h6>` 
- paragraphs of text `<p>`
- Images
- Links
- Lists
- Tables
- Forms

**Opening and closing tags**
- same as opening tag but with a "/" `<title>Example</title>`
- Some tags can "fast" close 
    - `<input type="text"/>`
- Some tags can "self" close
	1. `<img>`: Used to embed images in a web page.
	2. `<br>`: Used to insert a line break within text.
	3. `<input>`: Used to create input fields for forms.
	4. `<meta>`: Used to provide metadata about the HTML document.
	5. `<link>`: Used to link external resources such as stylesheets. 

    Both are valid

**Nesting**
- Tags can contain other tags. This is called "nesting"
	- **If it is nested it is indented**
- The hierarchy that rises from **nesting** is called **DOM** - Document Object Model.

**Commenting**
- `ctrl+/` to comment whole line

## Elements/Tags
### Text Elements
#### header tags
#### paragraph tags
#### anchor tags
- Important attribute: `href` (the url to route to)
- Text to display
#### msc: `<hr>`, `<br>`, `<em>` & `<strong>`
The **`<hr>`** html element represents a thematic break between paragraph-level elements: for example, a change of scene in a story, or a shift of topic within a section.

The **`<br>`** html element produces a line break in text (carriage-return)
The `<br>` element has a single, well-defined purpose — to create a line break in a block of text.
**USED WITHIN AN ELEMENT**
### Indentation
- Parent => Child & Sibling
- `TAB` === 4 spaces... or 2. <br>
Indentation has no relation to how the page ultimately will look to the client.
It is entirely driven by the parent, child, sibling relationship of tags and elements.
Technically not required... readability counts! ...and sanity.

**Parent, Child, Sibling Relationships:**
Indentation is typically used to reflect the hierarchical relationships between elements:
- Parent: An element that contains one or more other elements.
	- starts and ends on different lines
- Child: An element that is contained within another element.
- Sibling: Elements that share the same parent.
Proper indentation makes it easier to see these relationships at a glance, which is crucial for understanding the structure of the document. 
For example:

```html
<div> <!-- Parent -->
	<p>This is a paragraph.</p> <!-- Child -->
	<ul> <!-- Child -->
		<li>List item 1</li> <!-- Child of <ul> -->
		<li>List item 2</li> <!-- Child of <ul> -->
	</ul>
</div>
```
### Lists
Some "child" tags are designed specifically to work only within certain enclosing or "parent" tags. Multiple children are "siblings"
- **Unordered (bullet) lists**: `<ul>` with nested `<li>` that contain the list items
- **Ordered (numbered) lists**: `<ol>` with nested `<li>` that contain the list items

Different types can be applied to ordered lists with 
- `type="1"`(numbers/default)
- `type="a"`(lower case letters)
- `type="A"`(uppercase letters)
- `type="i"`(lowercase roman numerals)
- `type="!"`(uppercase roman numerals)
### Tables
`<table>` with nested `<tr>` (table rows) that contain nested `<th>` or `<td>` for header or regular data cells, respectively
- `<table>`: Defines boundary of table element.
- `<thead>`: Encapsulates the header row(s) of the table, which usually contains column titles (`<th>`).
- `<tr>`: row
- `<th>`: column titles
- `<tbody>`: Encapsulates the body of the table, which contains the data rows (`<tr>` with `<td>` elements).
- `<tr>`: rows
- `<td>`: cells of the tables
```html
<table>
    <thead>
        <tr>
            <th>Movie</th>
            <th>Year</th>
            <th>Rating</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Up</td>
            <td>2009</td>
            <td>PG</td>
        </tr>
        <tr>
            <td>The Matrix</td>
            <td>1999</td>
            <td>R</td>
        </tr>
    </tbody>
</table>
```
### Form Structure
- `<form>`
- `<label>`
- `<input>`
- `type="submit"`
### Form Inputs
- `type="text"`
- `type="color"`
- `type="number"`
- `type="password"`
- `type="date"`
- `type="datetime-local"`
- `type="radio"`
- `type="checkbox"`
- `<textarea></textarea>`
- `<select>`/`<option>`
### `<div>`
`<div></div>` element exists to create a division where group of tags have a common purpose.
- generic container for flow content. 
- It has no effect on the content or layout until styled in some way using CSS 
	- (aside from `display:block;`)
	- (e.g. styling is directly applied to it, or some kind of layout model like Flexbox is applied to its parent element)
#### div Rules
1. **[[HTML Tags]]**: Whenever possible, use HTML elements that convey the meaning of the content. `<div>` elements are generic containers and don't provide any semantic meaning on their own. Consider using semantic elements like `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, and `<footer>` to better describe the purpose of the content within the `<div>`.
2. **Minimal Use**: Avoid overusing `<div>` elements for styling purposes only. If there's a semantic HTML element available that conveys the same meaning, use it instead. This makes your code more readable and understandable for other developers and assistive technologies.
3. **Separation of Concerns**: Keep your HTML focused on content structure and use CSS for styling. Avoid adding inline styles directly to `<div>` elements, as this can make your HTML less maintainable and harder to update.
4. **Avoid Nested Divs**: Try to keep your HTML structure as flat as possible and avoid excessive nesting of `<div>` elements. Deeply nested `<div>` structures can make your code harder to understand and maintain.
5. **Class and ID Names**: Use descriptive class and ID names to identify the purpose or role of the `<div>` element. This makes it easier to understand the purpose of the element and maintain consistency across your codebase.
### `<img>` & `<video>`
- **Images**: `<img>`
	- Important attributes: `src` (the image file path) and `alt`!
```html
<img src="panda.jpg" alt="panda pic">
```
LINK TO IT
```html
<!-- Go to something -->
<a href="./img/morpheusGoogle.png">CLICK ME TO DISPLAY AN IMAGE</a><br/>
```
- **Videos**: `<video>`
	- Important attributes: `src` (the video file path) and `controls`
	- Also `autoplay loop muted`
```html
<video src="monkey2.mp4" controls></video>
<video src="monkey2.mp4" autoplay loop muted></video>
```
