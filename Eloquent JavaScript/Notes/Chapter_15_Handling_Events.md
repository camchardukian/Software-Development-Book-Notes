# Chapter 15 Handling Events

## Event Handlers

Browsers enable us to notify our code when an event occurs via the usage of handlers such as the _window.addEventListener()_ method.

## Events And DOM Nodes

Apart from the _window_ object, we can also register event handlers on DOM elements and a number of other objects.

## Event Objects

Each event handler function is passing the _event object_ as an argument. The _event object_’s _type_ property holds a string identifying which type of event triggered the event handler function to run.

## Propagation

If one element is nested in another element the nested element’s event handler will run first. Afterwards the event will “propagate” outward from the child to the parent, onward up the tree to the parent’s parent (if any) and so on until eventually the root of the document has been reached with all of the matching event handlers along the way also have been called.

It is possible to stop the above process before it reaches its natural conclusion via the usage of the _stopPropagation_ method.

## Default Actions

In most cases, JavaScript event handlers run before the default response to an event occurs. Because of this, we can use the _preventDefault_ method on the event object to prevent its default behavior from occurring. It should be noted, however, that the default behaviors of some events cannot be prevented.

## Key Events

The “keydown” event runs both when a key is physically pushed down, but also each time a key repeats (when a user holds a key down).

## Pointer Events

If two clicks happen in rapid succession a “dblclick” event is fired after the second click event. If a “mousedown” event occurs on one element, and the “mouseup” event occurs on another element, the “click” event will occur on the parent of these two elements.

Each mouse event has a _clientX_ and _clientY_ property to indicate exactly where a given mouse event occurred.

The _mousemove_ event is fired whenever the mouse pointer moves.

Some of the common events fired via user interaction in the browser with a touch screen include _touchstart_, _touchmove_, and _touchend_.

## Scroll Events

Calling _preventDefault_ on a scroll event does not prevent scrolling from happening.

## Focus Events

_Focus_ events are fired when elements gain focus, _blur_ events are fired when elements lose focus. The window object will also fire _focus_ and _blur_ events when the user moves to/from the browser tab/window containing said window object.

## Load Event

When a page finishes loading the _load_ events fires on the window and document body objects. When the user tries to close or navigate away from our page, a _beforeunload_ event will run. This event can be used to warn the user of possible data loss that could occur from closing the window.

## Events And The Event Loop

_A web workers_ is a JavaScript process that runs alongside the main script without clogging up the event loop.

## Timers

We can tell the browser we want to perform an animation by using the _Window.requestAnimationFrame_ method. Likewise, we can cancel said animation by calling _requestAnimationFrame_ before the animation returned by _Window.requestAnimationFrame_ is able to run.

## Debouncing

We can write debouncing functions to prevent events from being fired too quickly in rapid succession (as could potentially be the case with events like _mousemove_, _scroll_, or _keydown_).
