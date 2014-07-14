javascript 101 - session 3
----

# Review

- Objects, Functions, Arrays, and primitives
- Variables
- The Web API (JavaScript objects that represent the DOM)
- Hierarchy of element objects
- Finding elements
- Identifying element types
- Generating HTML/elements
- Modifying HTML/elements

---

# New Topics

## Conditionals

### True and False

[Equality Table](http://dorey.github.io/JavaScript-Equality-Table/)

### Types

What is a type?
Types help ensure safety by requiring the programmer to constrain what "kind"
of variable they are creating into a pre-defined (or user-defined) type.

These type constraints allow the compiler/interpreter to effectively "guess"
which sorts of operations something can perform, and optimize itself for
that sort of thing.

JavaScript Types:

#### Primary (primitive)

##### String type

Examples: `"Hello, World!"`, `"c"`, `""`

##### Number type

Examples: `1`, `1.2`, `-3.1415926535`

##### Boolean type

Examples: `true`

#### Composite

##### Object Type

Example: `{ "foo": "bar" }` |

##### Array Type

Examples: `[1, 2, 3, 4]`, `["H", "e", "l", "l", "o"]` |

#### Special Data Types

##### Null Type

Example: `null`

##### Undefined Type

Example: `undefined`

#### The `typeof` operator

`typeof` will return a string denoting the "type" of "thing" we are working
with.

#### Duck-typing

Rely on documentation, clear code, and testing to ensure correct use.

### Triple Equals `===`

Does not coerce the type of the variable.

```
var zeroStr = '0';
var zeroInt = 0;

// Trip-equals
console.log(zeroStr === zeroInt);
```

#### Double Equals `==`

Coerces the type of the variable.

```
var zeroStr = "0";
var zeroInt = 0;

// Dub-equals
console.log(zeroStr == zeroInt);
```

### The `if` statement

Syntax:

```
if (<condition>) {
    <expression>
}
else if (<condition>) {
    <expression>
}
else {
    <expression>
}
```

```
var a = 'foo'
if (a === 'foo') {
    console.log("a === 'foo' !");
    <expression>
}
else if (a === 'bar') {
    console.log("a === 'bar' !");
}
else {
    console.log("WTF is a?");
}
```

# Exercise Time

## 1
[Exercise 1](http://jsbin.com/sagow/6/edit)

I have set up a jsbin with some simple HTML and Javascript. The purpose
of it is to convert temperatures from Fahrenheit to Celsius and vice versa.
