Create a JavaScript application that interfaces with a server's file system.  The application should be able
to send files to the server and report the result of this attempt.  Monitoring the health of the server is an
additional concern.  The result of a file upload or a server status notification should be displayed as an "alert"
to the user.  Don't use `window.alert`.  Instead, create a message handler that renders an element in the DOM that
displays the message associated with the event, appropriately color-coded.  These messages should also be logged to the
console, and errors should be sent to an endpoint for further processing.  

The exercise should touch on scope, context, inheritance, and closures.  It will also alow you to create code that
you can improve and evolve over time as you learn more about JavaScript and the tools available to you as a web
developer.


### A few key concepts to be aware of before we start

* **closures** are formed when a nested function is defined inside of another function, allowing access to the outer functions variables.  One benefit involves passing functions around for the purposes of getting a callback when something happens.
* **scope** pertains to the variable access of a function when it is invoked, and is unique to each invocation.  Closures make use of scope (described above).  New scope is created for each function, and a chain of scopes are available to this new scope, from the current function all the way up through all ancestor functions.
* **context** always refers to the value of the `this` keyword, which is a reference to the object that owns the currently executing code.  Context is often confused with scope, but they are different concepts.
* **inheritance** is expressed via a prototype model in JavaScript.  Remember, everything in JavaScript is an `Object`, and all `Objects` that have some hierarchical relation to each other are connected to each other via a prototype link (usually accessible via the instance's `__proto__` property).  The root node/parent has a `null` prototype.  You may inherit from one object by setting your new object definition's `prototype` to an instance of the parent.  This will inherit all properties associated with the parent's prototype (including properties it inherits from its parents, and so on). 


### Specifications for the application

#### Main application
* Register for asynchronous server events
* Server events are informational, unless an error is detected, in which case they are warnings.  Text will accompany status.  Appropriate messages should be created and posted based on the event type.
* Allow a "file" to be "uploaded" when requested by the user with the help of the file system service
* The upload process is asynchronous as well.  The result of this operation can be successful or a failure.  Text _may_ accompany status.  Appropriate messages should be created and posted based on the event type.

#### Message constructs
* 4 types: success, failure, informational, alert
* All messages are logged to the `console`
* All messages are displayed on the page without the use of `window.alert`
* Error messages are also "sent" to the server
* A new message is constructed by type, and the text is passed into the constructor
* API: `post` which does something with the message.

#### File system service
* A new instance must be created by passing a listener function.  This function will be invoked whenever a spontaneous server status is available.  The first parameter of this function describes the status, and the second is a boolean, `isError`.
* API: `upload` which takes a "file" and a callback function.  The callback will be invoked after the operation is complete, passing an optional (may be null) message, and a required boolean `isError`.
