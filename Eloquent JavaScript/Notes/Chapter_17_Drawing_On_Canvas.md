# Chapter 17 -- Drawing On Canvas

A canvas is a DOM element that holds a picture. Using canvases we can draw shapes onto the DOM element that the canvas holds.

## SVG

The \<circle> and \<rect> tags create dom elements that JavaScript scripts can interact with.

## The Canvas Element

Canvas elements have width and height properties that we can set to determine how large the canvas will be. Newly created canvases are transparent (though they still take up space in the document).

## Lines And Surfaces

Shapes inside of a canvas can be _filled_ (the entire area of the shape is colored), or _stroked_ (only the outline of the shape is colored). Canvases get a default width of 300px and default height of 150px.

## Paths

Paths are sequences of lines created by method calls. Paths need to be closed before they can be filled (using the _fill_ method).

## Curves

Curved lines can be drawn using the _quadraticCurveTo()_, _arc()_ or _bezierCurveTo()_ methods.

## Text

2D canvas drawings have _fillText()_ and _strokeText()_ methods to add text to our canvases.

## Choosing A Graphics Interface

Each method of generating graphics has various strengths and weaknesses. Plain old HTML is simple. Canvas is efficient for drawing large numbers of tiny elements. SVG is great for producing crisp graphics that look sharp at any zoom level.
