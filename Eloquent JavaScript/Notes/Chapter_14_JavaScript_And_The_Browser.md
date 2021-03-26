# Chapter 14 -- The Document Object Model

## Document Structure

Each tag we use in HTML will manifest itself in the browser as an object that can be interacted with. These objects contain information such as the HTML tag being represented, and any text contained within said tag. The structure of objects the browser uses to represent our HTML tags is called the _Document Object Model_ or DOM for short.

## Trees

It’s usually more efficient to find or insert elements into a tree versus a flat array.

## The Standard

The DOM wasn’t designed solely for JavaScript. It was intended to be a language-agnostic interface that could be used for other languages. This is why some aspects of the DOM seem to be poorly integrated with JavaScript.

## Moving Through The Tree

Text nodes have a _nodeValue_ property that holds the string of text that they represent. Recursive functions are often useful when dealing with nested data structures.

## Finding Elements

We can use the _getElementsByTagName_ method to collect all of the elements of a given HTML tag that are descendants of the element node we called the method on.

Other similar methods include _getElementById_ (gets only a single element), and _getElementsByClassName_.

## Changing The Document

A given node can only exist in the document in one place at a time. As a result, inserting a node somewhere will cause it to be removed from its current position (if one exists).

## Creating Nodes

We can create text nodes with the _document.createTextNode_ method.

## Attributes

It’s possible to set additional properties on HTML nodes using the _setAttribute_ method. Once we’ve set additional properties on said nodes, we can use the _getAttribute_ method to get those properties.

## Layout

We can see the amount of pixels an element takes up by accessing the _offsetWidth_ and _offsetHeight_ properties. If we would like to see the size of an element without including the space its borders take up, we can instead use the _clientWidth_ and _clientHeight_ properties.

We can find the exact position of an element on the screen using the _getBoundingClientRect_ method, and we can see where an element is relative to the full document using _pageXOffset_ and _pageYOffset_

## Styling

We can use JavaScript to manipulate the styles of elements using the elements’ _style_ property.

## Cascading Styles

We can specify whether we want to target all children or only direct children using CSS.

```
div p { } // targets all <p> tags inside of <div> tags
div > p // targets only <p> tags that are direct children of <div> tags
```

## Query Selectors

We can use the _querySelectorAll_ method to return a given list of DOM elements that match the query string we pass to this method.

## Positioning and Animating

Browsers do not update what is being displayed or allow interactions while a JavaScript program is running.
