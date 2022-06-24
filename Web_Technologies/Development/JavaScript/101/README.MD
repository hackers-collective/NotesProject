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

A relativey simple data structure, just contain a value and have a type.

JavaScript is a loosely typed language. i.e it determines the type based on the value.

For Example: if we declare a value of 10, JavaScript will automatically define it as a number type.

### String

Generally, Strings are used to store a text value, and a sequence of characters.

In JS, following are the different ways to declare a string:

- Double Quotes \"\"
- Single Quotes \'\'
- Backticks: special template strings in whichyou can use variable directly \`\`

The difference between single quotes and double quotes is that you can use single quotes as literal characters in dobule quotes strings, and vice-versa.

- If you declare a string with dingle quotes, and string itself contains a single quote character, the string will end as soon as second quote is detected, even if it's in the middle of a word.

- For Example: ```let activity = 'Let's do this';```

- It can be solved using Double Quotes instead of single quotes, and it will also work vice-versa — in case there is a double quote character in your string.

- For Example: ```"Let's do this";```

In a string, using backticks, you can point to variables and the variable's value will be substituted in the line.

- Example Code Snippet

```javascript
let language = "JavaScript";
let message = `Let's learn ${language}`;
console.log(message);
```

Variables in these template strings are specified between ```${nameOfVariable}```.

### Escape Characters

A special character (a backslash "\\") that can be used to tell JavaScript not to take the next character as you normally would.

For Example: ```let string1 = "Hello, What's your name? Is it \"Vikash\"?";```

and will work in this way also

```let string2 = 'Hello, What\'s your name? Is it "Mike"?';```

It all happening normally because the backslash before the quote character gives the quote character a different meaning that it should be a literal character instead of an indicator to end string.
