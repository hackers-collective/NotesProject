# Multiple Values - JavaScript

For more complex programming, objects and arrays can contain multiple values.

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
