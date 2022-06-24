# 101 - JavaScript

## Index

- [Variables](#variables)
  - [Declaring Variables](#declaring-variables)
  - [let, var and const](#let-var-and-const)

- [Primitive Data Types](#primitive-data-types)
  - [String](#string)
  - [Escape Characters](#escape-characters)
  - [Number](#number)

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

## Primitive Data Types

A relativey simple data structure, just contain a value and have a type.

JavaScript is a loosely typed language. i.e it determines the type based on the value.

For Example: if we declare a value of 10, JavaScript will automatically define it as a number type.

### String

Generally, Strings are used to store a text value, and a sequence of characters.

In JS, following are the different ways to declare a string:

- Double Quotes \"\"
- Single Quotes \'\'
- Backticks: special template strings in which you can use variable directly \`\`

The difference between single quotes and double quotes is that you can use single quotes as [literal characters](/Programming_Languages/README.MD/#terminologies) in dobule quotes strings, and vice-versa.

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

Backslash has other more purposes

- It can be used to create a line break with ```\n```

```javascript
let string3 = "New \nline.";
```

- To include a backslash character itself in the text with ```\\```

```javascript
let string4 = "I'm containing a backslash: \\!";
```

### Number

Basically, a datetype used to represent numbers.

Unlike other programming languages, JavaScript has only data type for all the different types of numbers: number.

Developers of JavaScript decided to go for a 64-bit floating-point number; i.e it can store rather large numbers and both signed and unsigned numbers, decimal numbers, and more.

JavaScript can represent the following different kinds of numbers: integers, decimals, exponentials, octal, hexadecimal, and binary numbers.

For Example:

```javascript
int intNr = 1; // Number
int decNr = 1.5; // Decimal;
int expNr = 1.4e15; // Exponential;
int octNr = 0o10; // Octal; decimal version would be 8
int hexNr = 0x3E8; // Hexadecimal; decimal version would be 1000
int binNr = 0b101; // Binary; decimal version would be 5
```

All the above numbers are of the number data type. 

Integers, flaoting points, binary numbers all are one data type "number" in the below example

```javascript
let intNr2 = -111; // Unsigned
let decNr2 = 45.78;
let binNr2 = 0b100;
```

### BigInt

In some cases, you will need an even bigger number because of the limits of the number data type are between 2<sup>53</sup>-1 and -(2<sup>53</sup>-1), BigInt comes into play in this case.
