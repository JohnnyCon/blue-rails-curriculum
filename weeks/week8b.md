
Week 8 (Wednesday)
===================

## Overview

JavaScript is an important part of every web application.  We'll cover the basics of Javascript and how to utilize JavaScript and Ajax wihtin a Rails application.


## JavaScript

There are thousands of very good JavaScript tutorials on the web.  This class does not attempt to cover JavaScript, however let's cover some important points.

*  JavaScript is the only programming language that can run in the browser natively
*  JavaScript should be used to **Add Behavior** to your page (HTML for structure, CSS for style)
*  A couple examles of things JavaScript can be used for:
    *   Dynamically displaying and rendering content
    *   Loading new content to a page asynchronously
    *   Interacting with charts and graphs
    *   Responsive UIs that dynamically render/change without a page postback
*  JavaScript as a language was written in 10 days.
*  JavaScript has both OO and Functional lineage and influences which makes it difficult to master
*  You can write JavaScript directly in the Chrome console and interact with web pages
*  JavaScript has some good parts and some bad parts. There's a book that covers this in depth


## Coffeescript

CoffeeScript is a small language that ultimately compiles to JavaScript. CoffeeScript was written to make writing JavaScript more pleasant and less error prone.

CoffeeScript is the default file type in Rails projects, however you can choose to write JavaScript instead. In this class, we will write coffeescript.

These are some of the key advantages to using CoffeeScript:

*  Easier syntax, looks more like ruby and python.
*  Syntax is more concise, less code to write equivalent in JavaScript
*  Impossible to commit common JavaScript errors, like:
     * Semicolon insertion inconsistency
     * Accidently using == (coersion equality) in stead of === (no coersion)
     * List iterators that work like Ruby on Python, instead of the native/complex JavaScript way
     * Protects against putting varialbes in the global namespace
     * Parenthesis are optional (like ruby) in all cases, except when doing nested function calls (i.e. math calcs)

## jQuery

jQuery is the most popular JavaScript library on the internet today (and has been for 5+ years). jQuery was largely responsible for the rise in interactive web applications.
Working directly with JavaScript and the HTML DOM (HTML Document Object Model) is difficult and inconsistent due to browsers not implementing standards (particularly IE).
jQuery is a library that wraps these inconsistencies and exposes commonly used functionality to programmers.

jQuery's most commonly used operations include:

*  Finding HTML nodes by element, class, attributes or ID.  Nodes can also be found using a combination of these.
*  Hiding and showing elements
*  Add/remove/change CSS styles
*  Dynamically adding HTML content to a page
*  Doing simple animations
*  Leverage the rich plugin ecosystem of predefined components that exists in the jQuery community


#### Finding matching nodes ####

```javascript
// finding all p  nodes
// returns an array of matching nodes
$("p")
```

```javascript
// finding all nodes with nav class
// returns an array of matching nodes
$(".nav")
```

```javascript
// finding all nodes with container ID. ID's should be unique on an HTML page
// so this should theoretically always return an array of zero or 1.
$("#container")
```

```javascript
// finding nodes that match these criteria
// returns array of matching arrays, paragraph elements with a class of primary
$("p.primary")
```

#### Hiding and showing nodes ####

```javascript
// hiding all nodes that match $("p")
$("p").hide()
```

```javascript
// showing all nodes that match $("p")
$("p").show()  
```

#### Showing and hiding nodes ####

```javascript
// hiding all nodes that match $("p")
$("p").hide()
```

```javascript
// showing all nodes that match $("p")
$("p").show()  
```

#### Adding dynamic HTML content ####

```javascript
// replaces the html content within the matching nodes
$("p").html()  
```

```javascript
// replaces the html content within the matching nodes
$("p.title").append("<p>The details</p>")  
```

```javascript
// replaces the html content within the matching nodes
$("<p>The details</p>").appendTo(".p.title")  
```

```javascript
// replaces the html content within the matching nodes
$("p").html()  
```



## Where does it all go?

Look at your GEM file. You should see a coffee-rails gem and a jquery-rails gem.  These gems eliminate the need for complex configuration when using these tools.

The CoffeeScript will automatically be converted to JavaScript before it's sent to the browser.

jQuery will be included in your master page so it's available on all your pages.
