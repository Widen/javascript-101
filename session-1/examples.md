Examples
=========

The following is a set of examples from the session 1 presentation.

# Outline
1. [Objects](#objects)
2. [Functions](#functions)
3. [Primitves](#primitives)
4. [Variables](#variables)
5. [Outputting text](#outputting-text)
6. [Arrays](#arrays)
7. [Including JavaScript on an HTML page](#including-javascript-on-a-page)


## Objects

### creation
```javascript
// empty object literal
var myObject = {};

// object literal with a parameter, "foo"" having a value of "bar"
var myObject2 = { foo: "bar" };
```
**Note:** There are other ways to create an object.  For example, via a "constructor function".  Or, via `Object.create()`.  We'll discuss those in a later session.


### accessing properties
```javascript
var myObject = {one: 1, 2: "two"};

// prints "1" to the console, the value of the "one" property on myObject
console.log(myObject.one);

// prints "two" to the console, the value of the "2" property on myObject
console.log(myObject["2"]);

// syntax error - you cannot use "dot notation" to access certain properties, 
// such as those that start with a number
console.log(myObject.2);
```

### removing properties
```javascript
var myObject = {one: 1, two: 2};

// removes the "one" property and its value from the object completely, 
// now only one property remains, and the object looks like this: {two: 2}
delete myObject["one"];

// removes the "two" property and its value from the object completely, 
// now no properties remain, and the object looks like this: {}
delete myObject.two;
```

### looping over properties
```javascript
var myObject = {one: 1, two: 2};

// more comlicated, but has a key advantage, which we will discuss in a later session
// also, this will not work in Internet Explorer 8 and older
var props = Object.keys(myObject);
for (var i = 0; i < props.length; i++) {
    var prop = props[i];
    console.log("prop: " + prop + "; value: " + myObject[prop]);
}

// simple, but with a big drawback (which we can overcome with a few more lines)
// the drawback will be discussed in a later session
for (var prop in myObject) {
    console.log("prop: " + prop + "; value: " + myObject[prop]);
}
```


## Functions

### creating
```javascript
// this will print "invoked" to the console when executed
var myFunc = function() {
    console.log("invoked!");
};

// objects can have properties with function values too
var myObject = {
    callMe: function() {
        console.log("called!");
    }
};
```

### invoking
```javascript
var myFunc = function() {
    console.log("invoked!");
};

// this executes the myFunc function
myFunc();
```

### passing arguments
```javascript
var logMessage = function(message) {
    console.log(message);
};

// "this is a message" will be logged to the console
logMessage("this is a message");


var printNameAndAge = function(name, age) {
    console.log("Hello " + name + ".  I hear you are " + age + " years old.");
};

// prints "Hello Ray.  I hear you are 33 years old." to the console
printNameAndAge("Ray", 33);


// You can make use of the arguments psuedo-array for functions that take 
// a variable number of arguments.  Be careful, pseudo arrays are not actually arrays, 
// just objects with a length property.  We'll talk more about arrays later in this examples page.
var addAllNumbers = function() {
    var sum = 0;
    for (var i = 0; i < arguments.length; i++) {
        sum += arguments[i];
    }
    
    console.log(sum);
};

// prints 15 to the console
addAllNumbers(1, 2, 3, 4, 5);
```
### types of functions

#### named
```javascript
// invoke this by referring to its name
function myFunc() {
    // ...
};
```

#### anonymous
```javascript
// A function without a name.  Can be passed and executed later by reference.  
// Also used with IIFEs (see below)
function() {
    // ...
}
```

#### function expressions
```javascript
// Just a function explicity assigned to a variable.
// ee further down for more examples of variables.
var myFunc = function() {
    // ...
};
```

#### function declarations
```javascript
// Can still be invoked simply by calling the name of the function.
function myFunc() {
    // ...
}
```

#### Immediately Invoked Function Expressions (IIFE)
```javascript
// This function is invoked automatically, as soon as the JS parser hits it.  
// The use of IIFes will become more clear once we discuss scope in more detail in a later session.
(function() {
    console.log("executed as soon as the JavaScript interpreter reaches this");    
}());
```


## Primitives

### 5 types
1. `null` (a value explicitly set to a variable or property)
2. `undefined` (the default value when a variable has been declared without an explicit value)
3. strings: `"hi there"`
4. booleans: `true` and `false`
5. numbers: `1`, `1.5`, `-3`

### NOTE: Primitives are objects too
- Except for `null` and `undefined`.
- When you attempt to access a property on a primitive, the JavaScript interpreter constructs the associated Object (`Boolean`, `String`, `Number`) and passes the primitive in as a parameter.  The result is an `Object`, which you can call methods on.

```javascript
// outputs "hi"
console.log("HI".toLowerCase());

// outputs "true"
console.log(true.toString());

// outputs 10.000 - note that we must wrap the number to access its associated object
(10).toFixed(3);

// identical to above, just another way to access the Number object
10..toFixed(3);
```


## Variables
...coming soon

## Outputting Text
...coming soon

## Arrays
...coming soon

## Including JavaScript on a Page
...coming soon


