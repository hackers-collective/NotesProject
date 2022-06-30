# Multiple Values - JavaScript

For more complex programming, objects and arrays can contain multiple values.

## Index

- [Arrays and their properties](#arrays-and-their-properties)
  - [Creating Arrays](#creating-arrays)

## Arrays and their properties

In JS, Arrays are lists of values of all data types and it is possible for one array to contain different data types.

Arrays are very useful to store multiple values inside one variable.

### Creating Arrays

Not a Good Practice

```javascript
arr1 = new Array("Purple", "Green", "Yellow");
```

Good Practice

```javascript
arr2 = ["Black","Orange","Pink"];
```

In JS, we can have mixed arrays and arrays can hold any type of variable. The values of the array won't be converted to a single data type or anything like that. Hence, JavaScript simply stores all the variables with their own data type and value in the array:

```javascript
let arr = ["Hey There!", 812, false];

console.log(typeof arr[0]);
console.log(typeof arr[1]);
console.log(typeof arr[2]);
```

It will log:

```console
string
number
boolean
```

We can even define an Array using const; but in that case, we can only change the values of a constant array, but cannot change the array itself. For Example:

```javascript
const arr = ["Hey There"];
arr[0] = "Hi There";
console.log(arr[0]);

arr = ["Nope, You're not there"];
```

It will output:

```console
Hi There
TypeError: Assignment to constant variable.
```

### Accessing Elements

We can access elements of the array by referencing the array's index.

JavaScript assigns an index to every value of the array itself.

Generally, the first value is assigned the position of 0, the second 1, the third 2, and so on.

To call a specific value of the array based on its position, we can use the name of our array, add square breackets to the end, and put the index we want to access between the square brackets, like this

ARRAY[n]

For Example:

```javascript
bikes = ["KTM", "Suzuki", "BMW", "Royal Enfield"];
console.log(bikes[1]);
```

It will output the following:

```console
Suzuki
```

Because, Suzuki is at index position 1.

If we use -1 as index value to call the item, it will output undefined instead of throwing an Error.

### Overwriting Elements

Elements in an array can be overwritten. This can be done by accessing a certain element using the index and assigning a new value. For Example:

```javascript
bikes[0] = "Ducati";
console.log(bikes[0]);
```

It will log Ducati instead of KTM because it has overwritten the old value. Let's output the whole array:

```javascript
console.log(bikes);
```

Output:

```console
['Ducati', 'Suzuki, 'BMW', 'Royal Enfield']
```

And, if we update a negative index as

ARRAY[-1] = "Something"

Still, it will output the something for -1.

### Built-in length property

In JS, the arrays have a very useful built-in property called length. This will return the number of values that the array has. For Example:

```javascript
colors = ["black","orange","pink"];
emptyArray = [];

console.log("Lenght of colors: ", colors.length);
console.log("Length of empty array: ", emptyArray.length);
```

This will log the following:

```console
Length of colors: 3
Length of empty array: 0
```

Length is always one higher than the maximum index because the index of the array starts at 0.

To access the last element of an array:

`lastElement = Array[Array.length - 1];`

The length of the array only counts the integer numbers starting from 0 up to the highest filled index. If there are elements in the middle of the sequence that do not have a value, they will still get counted. For Example:

```javascript
numbers = [12, 24, 36];
numbers[5] = 48;

console.log(numbers.length);
```

In this case, the length becomes 6.

If we log the array, we can see why:

```javascript
console.log("numbers", numbers);
```

The output will be as follows:

```console
numbers [ 12, 24, 36, <2 empty items>, 48 ]
```

Because we added an element, 48, at index 5, it also created 2 elements at index positions 3 and 4 containing empty values.

## Array Methods

Methods are functions ona certain object. Instead of holding a value, like properties, they perform actions.
