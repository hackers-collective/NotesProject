# 101 - JavaScript

## Index

- [Variables](#variables)
  - [Declaring Variables](#declaring-variables)
  - [let, var and const](#let-var-and-const)

- [Primitive Data Types](#primitive-data-types)
  - [String](#string)
  - [Escape Characters](#escape-characters)
  - [Number](#number)
  - [BigInt](#bigint)
  - [Boolean](#boolean)
  - [Symbol](#symbol)
  - [Undefined](#undefined)
  - [null](#null)

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

- If you declare a string with dingle quotes, and string itself contains a single quote character, the string will end as soon as second quote is detected, even if it's in the middle of a word. For Example: 

```javascript
let activity = 'Let's do this';
```

- It can be solved using Double Quotes instead of single quotes, and it will also work vice-versa — in case there is a double quote character in your string. For Example: 
 
```javascript
let activity = "Let's do this";
```

In a string, using backticks, you can point to variables and the variable's value will be substituted in the line.

Example Code Snippet

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

```javascript
let string2 = 'Hello, What\'s your name? Is it "Mike"?';
```

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

In some cases, you will need an even bigger number because of the limits of the number data type which are between 2<sup>53</sup>-1 and -(2<sup>53</sup>-1), BigInt comes into play in this case.

A BigInt data type can be recognized by the postfix n, For Example:

```javascript
let bigNr = 90071992547409920n;
```

It is important to understand that we can't mix BigInt with the Number data type to perform operations.

If we do so, For Example: ```let result = bigNr + intNr;```, it will throw the error as

```console
Uncaught TypeError; Cannot mix BigInt and other types, use explicit conversions
```

### Boolean

The Boolean data type can hold only two values: `true` and `false`; generally used to indicate on/off or yes/no or true/false situations.

For Example:

```javascript
let bool1 = false;
let bool2 = true;
```

More Examples:

Whether an element is deleted

```javascript
let objectIsDeleted = false;
```

Or, whether the light is on or off

```javascript
let lightIsOn = true;
```

### Symbol

Symbol is new data type introduced in ECMA Script 6 or ES6 (current version of JavaScript) which can be used when it is important that variables are not equal, even though their value and type are the same (in this case, they would both be of the symbol type).

For Example: let's compare the following string declarations to the symbol declarations, all of equal value:

```javascript
let str1 = "Hi, JavaScript!";
let str2 = "Hi, JavaScript!";
console.log("Both of two Strings are same: ", str1 === str2);

let sym1 = Symbol("Hi, JavaScript!");
let sym2 = Symbol("Hi, JavaScript!");
console.log("Both of two Symbols are same: ", sym1 === sym2);
```

And the output:

```console
Both of two strings are same: true
Both of two Symbols are same: false
```

What actually happening here is JS concludes that the Strings (`str1` and `str2` in this context) are the same and have the same value, and the same type. However, each Symbol (`sym1` and `sym2`) is unique even they contain the same string, they are not the same, and output `false` when compared; because of the `Symbol` function.

### Undefined

JavaScript has a special data type called "undefined" for a variable that has not been assigned a value.

For Example:

```javascript
let unassigned;
console.log(unassigned);
```

The output here will be

```console
Undefined
```

It is possible to assign an `undefined` value purposefully; but it is even more important to know that manual assignment of `undefined` as a value is not a good practice in Code Writing.

```javascript
let badPracticeToFollow = undefined;
```

There are number of reasons to not do this. For Example

If you're checking for equality, you would want to know whether two values are actually equal, not just that they are both undefined. This way, someone's pet and their last name might be considered equal, whereas they are actually both just empty values.

### null

null is a special value for describing that a variable is empty or has an unknown value. The keyword `null` is case sensitive.

```javascript
let empty = null;
```

The `undefined` issue can be solved with `null`

In previous issue we encountered with setting a variable as undefined, but if you set it to null, you will not have the same problem.

It is one of the great use cases of `null` to assign null to a variable when you want to say it is empty and unknown at first:

```javascript
let badPracticeToFollow = undefined;
let lastName;
console.log("Same undefined: ", lastName === badPracticeToFollow);

let bestPractice = null;
console.log("Same null: ", lastName === betterOption);
```

This outputs the following:

```console
Same undefined: true
Same null: false
```

This shows that an automatically undefined variable (lastName) and a deliberately undefined variable (badPracticeToFollow), are considerd equal, which is problematic. On the other hand, lastName and betterOption, which was explicitly declared with a value of null, are not equal.

## Data Types analysis and modifications

### Working out the type of a variable

To determine what kind of data type you are dealing with especially with null and undefined, the role of `typeof` comes into play.

typeof, an operator in JavaScript, returns the type of the variable, and you can check the type of a variable by entering typeof, then either a space followed by the variable, or the variable in brackets. For Example:

```javascript
testVar = 1;
varTypeTest1 = typeof testVar;
varTypeTest2 = typeof(testVar);

console.log(varTypeTest1);
console.log(varTypeTest2);
```

Both of the methods above will output number. Brackets aren't required because typeof is an operator, not a method, unlike console.log. But, using brackets makes your code easier to read.

More Examples:

```javascript
let str = "Hi";
let nr = 812;
let bigNr = 12345678901234n;
let bool = false;
let sym = Symbol("unique");
let unDef = undefined;
let unknown = null;

console.log("str ", typeof str);
console.log("nr ", typeof nr);
console.log("bigNr ", typeof bigNr);
console.log("bool ", typeof bool);
console.log("sym ", typeof sym);
console.log("unDef ", typeof unDef);
console.log("unknown ", typeof unknown);
```

This will produce the following output:

```console
str String
nr number
bigNr bigint
bool boolean
sym symbol
unDef undefined
unknown object
```

**Important:** Because of backward compatibility problem, null returns object.

### Type Conversion

THe variables in JavaScript can change types.
JavaScript can automatically change the type on the fly unlike other languages. For Example:

```javascript
let nr1 = 2; // A Number
let nr2 = "2"; // A Sring

console.log(nr1 * nr2);
```

JavaScript does not just throw an error, it first tries to convert the string value to a number.

In this case, console.log will output the 4 in the console.

But, it seems not a good practice to follow; For Example:

```javascript
let nr1 = 2;
let nr2 = "2";

console.log(nr1 + nr2);
```

This one will log 22. Because, the plus sign here is used to concatenate strings. Therefore, instead of converting a string to a number, it is converting a number to a string, and making them 22.

There are 3 built-in functions we can use to convert the data type of our variable: String(), Number(), and Boolean()

String() converts a variable to type String; takes any value, including undefined and null, and puts quotes around it. For Example:

```javascript
let nrToStr = 6;
nrToStr = String(nrToStr);
console.log(nrToStr, typeof nrToStr);
```

This will log the following:

```console
6 string
```

Number() tries to convert a variable to a number. If that cannot be done logically, it will change the value into NaN (not a number). For Example:

```javascript
let strToNr = "12";
strToNr = Number(strToNr);
console.log(strToNr, typeof strToNr);
```

This will log the following:

```console
12 number
```

Boolean() converts a variable to a Boolean. This will be true for everything except for null, undefined, 0 (number), an empty string, and NaN. For Example:

```javascript
let strToBool = "I'm string, I'll always return true";
strToBool = Boolean(strToBool);
console.log(strToBool, typeof strToBool);
```

This will log the following:

```console
true boolean
```

An empty string and null will both result in the number 0. It can come in handy at times when you want to convert a string to 0 when it is empty or null. For Example:

```javascript
let nullToNr = null;
nullToNr = Number(nullToNr);
console.log("null ", nullToNr, typeof nullToNr);

let strToNr = "";
strToNr = Number(strToNr);
console.log("empty string ", strToNr, typeof strToNr);
```

This will output:

```console
null 0 number
empty string 0 number
```

Anything that can't be interpreted as a number by simply removing the quotes will evaluate as NaN (not a number). For Example:

```javascript
let strToNr2 = "hello";
strToNr2 = Number(strToNr2);
console.log(strToNr2, typeof strToNr2);
```

The result that will be loggd to the console is:

```console
NaN number
```

Any string will return true when converted to a Boolean, even the string "false". Only an empty string, null, and undefined will lead to a Boolean value of false. For Example:

```javascript
let strToBool1 = "false";
strToBool1 = Boolean(strToBool1);
console.log(strToBool1, typeof strToBool1);

let strToBool2 = "";
strToBool2 = Boolean(strToBool2);
console.log(strToBool2, typeof strToBool2);
```

This one will log the following:

```console
true boolean
false boolean
```

## Operators

Operators come in handy whenever we want to work with the variables, modify them, perform calculations on them, and compare them. We use them to operate on our variables.

### Arithmetic Operators
