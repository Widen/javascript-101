Context
----

# _Javascript 101_


[What is a compiler and interpreter? (video)](https://www.youtube.com/watch?v=kmQUB-5cEgM)

# Context

*Definition*: The _minimal_ set of data needed to save and then resume the task at some point.

> note that [**context**](https://en.wikipedia.org/wiki/Context_(computing) is a subset of the program's [_state_](https://en.wikipedia.org/wiki/State_(computer_science).

**In javascript:**

- Object based
- `this`
    - the current calling function (function based)
    
```javascript
// Functions do not change context
function fooFunction() {
    return this;
};

console.log(fooFunction());
```

```javascript
// Objects change context
function fooFunction() {
    return this;
};

var myObject = { 
    bar: fooFunction
};

console.log(myObject.bar());
```

### `.call(thisArg[, arg1[, ... argn]]])`

Calls a function with given `this` value and arguments.
    
```javascript
// `call`
function fooFunction(arg1, arg2) {
    console.log(arg1, arg2);
    return this;
};
var myObject = { bar: function() {} };

console.log(fooFunction.call(myObject, 'w00t', 'w00t'));
```

### `.apply(thisArg, [argsArray])`

Like `call` but Array of arguments

**Example:**

```javascript
// `call`
function fooFunction(arg1, arg2) {
    console.log(arg1, arg2);
    return this;
};
var myObject = { bar: function() {} };

console.log(fooFunction.apply(myObject, ['w00t', 'w00t']));
```

### `.bind(thisArg[, arg1[, ... argn]]])` 

Returns a new function that has provided `this` and arguments when called

**Example:**

```javascript
// `call`
function fooFunction() {
    return this;
};
var myObject = { bar: function() {} };

var boundFooFunction = fooFunction.bind(myObject);

console.log(boundFooFunction());
```

# Inheritance

## What is inheritance?

### Why?

#### Code Reuse

Subclass maintains base class objs and methods

#### Overriding

A class is permitted to replace and object's implementation

#### Visibility

Methods and functions can be contained and hidden from public use

## Inheritance with Javascript

**Not like Java!**

- prototype chain
     - do not touch native prototype!
- inheriting properties
- inheriting methods

**DO NOT TOUCH THE NATIVE PROTOTYPE!**

![](http://media0.giphy.com/media/4evFnSs4h7FFm/giphy.gif)

### Creating Objects

#### Syntax

You can use regular ol' Javascript syntax to create objects, and even do a bit of inheritance.

**Example:**

```javascript
var obj = { 
    a: 1,
    b: {
        c: 2
    }
};

var foo = function(){ console.log("foo"); });
[]
```

#### Constructor

##### `Object.create(proto[, propertiesObject]);`

`proto` - the object which should be the prototype of the newly-created object

**Example:**

```javascript
var defaults = {
    zero: 0,
    one: 1
};

var myOpts = Object.create(defaults);
var yourOpts = Object.create(defaults);

// When I want to change *just* my options
myOpts.zero = 1000;

// When you wanna change yours
yourOpts.one = 42;

// When we wanna change the **defaults** after we've got our options
// even **AFTER** we've already created our instances
defaults.two = 2;

myOptions.two; // 2
yourOptions.two; // 2
```