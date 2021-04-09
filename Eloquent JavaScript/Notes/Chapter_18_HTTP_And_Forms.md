## The Protocol

HTTP version 2 is significantly faster than HTTP version 1.1. Unfortunately, version 2 is also much more complicated.

Responses from the server come with a status code. Status codes starting with the number 2 indicate that the request succeeded, status codes starting with 4 means there was a problem with the request, and status codes starting with number 5 indicate some error happened on the server.

## Browsers And HTTP

When a form is submitted, the contents of its fields are packaged into an HTTP request.

JavaScript has _encodeURIComponent_ and _decodeURIComponent_ methods we can use on strings to perform or “un-perform” _URL encoding_.

## Fetch

JavaScript is able to make HTTP requests using the _fetch_ interface. When we call _fetch_ it returns a promise that resolves to a _Response_ object that provides information about the server’s response.

## HTTP Sandboxing

By default, browsers protect us by preventing scripts from making HTTP requests to other domains. This default behavior can be overridden by including the following header in the server’s response:

```
Access-Control-Allow-Origin: *
```

## Appreciating HTTP

A commonly used JavaScript model for communicating between the client and the server is called _remote procedure calls_. This model involves requests to the server that include a function’s name and arguments. The server then responds to that request with the value returned by said function (and its accompanying arguments).

## Security And HTTPS

HTTPS provides better security than HTTP by wrapping HTTP traffic in a way that makes it more difficult to read and tamper with. HTTPS requires the receiving of a cryptographic certificate issued by a reputable certificate authority before it exchanges information.

## Form Fields

Fields that appear outside of a form cannot be submitted in the traditional fashion.

## Focus

HTML provides the _autofocus_ attribute for focusing an element immediately when the page is loaded. By default most HTML elements cannot be focused on. We can, however, add the _tabindex_ property to any element to make it focusable.

## The Form As A Whole

Field elements that are contained inside of a form will have a property called _form_ which links them back to the form they are nested in. The form element on the other hand has an _elements_ property which contains the fields nested inside of the form as well as their accompanying values.

## Text Fields

The _selectionStart_ property returns the starting index of the text that is currently selected whereas _selectionEnd_ gives the ending index of the text that is currently selected.

## Select Fields

The \<options> that are nested inside of a \<select> field can be accessed through the select field’s _options_ property. Each option will have a property called _selected_ which is read/write and can be used to view or control whether an option is currently selected.

## File Fields

The _multiple_ property of an \<input type=”file”> element can be set to allow the user to simultaneously select multiple files.

_FileReader_ objects have a _readAsText_ method that can be passed a file. Doing so will allow us to read said file.

## Storing Data Client-Side

Values stored in _localStorage_ persist until they are overwritten, removed by calling the _removeItem_ method on the _localStorage_ object, or the user clears their local data.

The difference between _sessionStorage_ and _localStorage_ is that information stored in _sessionStorage_ is destroyed at the end of each browsing session whereas the information in _localStorage_ persists between sessions.
