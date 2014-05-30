Examples
=========

The following is a set of examples from the session 1 presentation.

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

// simple, but with a big draw (which we can overcome with a few more lines)
// the drawback will be discussed in a later session
for (var prop in myObject) {
    console.log("prop: " + prop + "; value: " + myObject[prop]);
}
```


## Functions
...coming soon

## Primitives
...coming soon

## Variables
...coming soon

## Outputting Text
...coming soon

## Arrays
...coming soon

## Including JavaScript on a Page
...coming soon


