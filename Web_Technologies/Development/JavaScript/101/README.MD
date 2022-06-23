# 101 - JavaScript

Index

## Variables

Variables are the values in your code that can represent different values each time the code runs. Without the variables, a piece of code would do the exact same thing every single time it was run which makes it static.

### Declaring Variables

In JavaScript, ```let```, ```var```, or ```const``` can be used to declare a variable at first time. Second time, you only use the name of existing variable to assign it a new value. For Example:

```javascript
let studentName = "John";
studentName = "Rock";
```

### let, var and const

Generally, the variable definition consists of three parts

- variable-defining keyword (let, var, or const in JavaScript)
- variable name
- variable value

The ```let``` and ```var```, both used for variables that might have new value assigned to them somewhere in the code. The differnce in between both is scope-based

- ```var``` has a global scope; i.e you can use the variables defined with var in the entire script.
- ```let``` has a block scope; i.e you can only use variables defined withlet in the specific block of code in which they were defined.

Note: The block of code will always start with { and end with }

At last, **const** is used for variables that only get a value assigned once.

For example: value of PI, which will not change.

## Primitive data types
