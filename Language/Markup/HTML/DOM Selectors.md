---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
getElementsByTagName - Find elements by tag name  
  
getElementsByClassName - Find elements by class name  
  
getElementById - Find an element by element id  
  
  
better  
//////  
querySelector - The querySelector() method returns the first child element that matches a specified CSS selector(s) of an element.  
  
var x = document.getElementById("myDIV");  
x.querySelector(".example").innerHTML = "Hello World!";  
  
  
  
  
querySelectorAll - The querySelectorAll() method returns a collection of an element's child elements that match a specified CSS selector(s), as a static NodeList object.  
  
  
  
var x = document.getElementById("myDIV").querySelectorAll(".example");  
  
// first query then get and set or any other command like changing style///  
  
getAttribute - The getAttribute() method returns the value of the attribute with the specified name, of an element.  
  
var x = document.getElementsByTagName("H1")[0].getAttribute("class"); // this will give class name value  
  
  
setAttribute - The setAttribute() method adds the specified attribute to an element, and gives it the specified value.  
------------------------------------------------  
var button = document.getElementById("enter");  
var input = document.getElementById("userinput");  
var ul = document.querySelector("ul");  
  
function inputLength() {  
return input.value.length;  
}  
  
function createListElement() {  
var li = document.createElement("li");  
li.appendChild(document.createTextNode(input.value));  
ul.appendChild(li);  
input.value = "";  
}  
  
function addListAfterClick() {  
if (inputLength() > 0) {  
createListElement();  
}  
}  
  
function addListAfterKeypress(event) {  
if (inputLength() > 0 && event.keyCode === 13) {  
createListElement();  
}  
}  
  
button.addEventListener("click", addListAfterClick);  
input.addEventListener("keypress", addListAfterKeypress);  
----------------------------------------------  
  
##Changing Styles  
style.{property} //ok  
The style property returns a CSSStyleDeclaration object, which represents an element's style attribute.  
  
document.getElementById("myH1").style.color = "red";  
  
  
className //best  
The className property sets or returns the class name of an element (the value of an element's class attribute).  
  
  
classList //best  
The classList property returns the class name(s) of an element, as a DOMTokenList object.  
This property is useful to add, remove and toggle CSS classes on an element.  
The classList property is read-only, however, you can modify it by using the add() and remove() methods.  
document.getElementById("myDIV").className = "mystyle";  
document.getElementById("myDIV").classList.add("mystyle");  
  
classList.remove  
classList.toggle  
  
DOMTokenList Represents a space-separated token list within the DOM, such as the contents of the className property of an element, treated as a zero-based array-like object. DOMTokenList objects are case-sensitive, even when the underlying string might ordinarily be treated in a case-insensitive manner.  
  
The Element.classList is a read-only property that returns a live DOMTokenList collection of the class attributes of the element. This can then be used to manipulate the class list.  
  
Using classList is a convenient alternative to accessing an element's list of classes as a space-delimited string via element.className.  
  
  
  
A DOMTokenList representing the contents of the element's class attribute. If the class attribute is not set or empty, it returns an empty DOMTokenList, i.e. a DOMTokenList with the length property equal to 0.  
  
Although the classList property itself is read-only, you can modify its associated DOMTokenList using the add(), remove(), replace(), and toggle() methods.  
  
## Bonus  
innerHTML //DANGEROUS  
The innerHTML property sets or returns the HTML content (inner HTML) of an element.  
  
parent element  
var x = document.getElementById("myLI").parentElement.nodeName;  
The parentElement property returns the parent element of the specified element.  
  
  
  
children  
var c = document.body.children;  
  
The children property returns a collection of an element's child elements, as an HTMLCollection object.  
  
The elements in the collection are sorted as they appear in the source code and can be accessed by index numbers. The index starts at 0.  
  
  
  
##It is important to CACHE selectors in variables  
  
Select HTML elements by ID uses less memory  
  
use a strong tag for bold and em for italicized  
span is like an inline div the manipulate specific elements  
Add JavaScript links to the bottom of body the HTML page  
  
  
[https://www.w3schools.com/js/js_htmldom_document.asp](https://www.w3schools.com/js/js_htmldom_document.asp)  
  
[https://www.w3schools.com/cssref/css_selectors.asp](https://www.w3schools.com/cssref/css_selectors.asp)  
  
[https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)