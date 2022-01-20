# Object Destructuring
Base file: fileA.js
```js
const myNumber = 42;
const myString = "hello";
const myFunction = () => {
  // myFunction's code
};

module.exports = {
  myNumber, // stores 42 as myNumber
  myString, // stores "hello" as myString
  myFunction, // stores the function as myFunction
};
```
Import Without Destructure
```js
const myObject = require("./fileA");

myObject.myNumber; // => 42
myObject.myString; // => "hello"
myObject.myFunction; // => the function you wrote
```
With Destructure
```js
// this is destructuring
const { myNumber, myString, myFunction } = require("./fileA");

myNumber; // => 42
myString; // => "hello"
myFunction; // => the function you wrote
```

# HTTP
## Methods
There are 9 HTTP request methods, but we only need to consider 4 of them right now:

- GET: used to "get" some data from the server
- POST: usually used to create some new data
- PUT: generally used for editing existing data on the server
- DELETE: used to delete some existing data

We'll explore these in detail over the next few weeks. Another name for HTTP methods is "verbs", since the methods can be seen as "action words".
## Paths and URL Structure
In order to request a "resource" (webpage, etc.) from an HTTP server, we need to know its URL. Every web developer should be able to correctly identify a Uniform Resource Locator, or URL. The path is a part of the URL.

Read the MDN article, [Understanding URLs and their structure](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL), and identify the different components of the following URL:
```
http://www.example.edu:80/path/to/myfile.html?key1=value1&key2=value2#SomewhereInTheDocument
```
- Protocol
- Domain (or Host)
- Port
- Resource Path
- Query Parameters
- Anchor

## Body
Response Body
The response will also usually contain some data, such as the data the client originally requested. This data is stored in a part of the response which is called the body. The body may store data in many kinds of formats, such as text and images. For our purposes, the body will often contain webpages (HTML) or data encoded in JSON, which we'll learn about later on.