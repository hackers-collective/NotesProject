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

We can add elements using new indices, but this is not a proper way to do it as it is easy to make mistakes and accidentally overwrite a certain value or skip a certain index.

### Adding and Replacing elements

We can add elements with the push() method. For Example:

```javascript
favoriteFruits = ["grapefruit", "orange", "lemon"];
favoriteFruits.push("tangerine");
```

The value gets added to the end of the array. The push method returns the new length of the array, four in this case.

You can store this length in a variable like this:

```javascript
let lengthOfFavoriteFruits = favoriteFruits.push("lime");
```

The value 5 gets stored in the `lengthOfFavoriteFruits` variable. If we log our array, `favoriteFruits`, like this:

```javascript
console.log(favoriteFruits);
```

Here is the new array:

```console
[ 'grapefruit', 'orange', 'lemon', 'tangerine', 'lime' ]
```

To add elements at a certain index; you can use `splice()` method. For Example:

```javascript
let arrOfShapes = ["circle", "triangle", "rectangle", "pentagon"];
arrOfShapes.splice(2, 0, "square", "trapezoid");

console.log(arrOfShapes);
```

It will log:

```console
[
 'circle',
 'triangle',
 'square',
 'trapezoid',
 'rectangle',
 'pentagon'
]
```

As you can see, the square and trapezoid get inserted on index 2. The rest of the array is shifting to the right. The splice() method takes multiple parameters. The first parameter, 2 in our case, is the index of the array on which we want to start inserting. The second parameter, 0 in our case, is the number of elements we want to delete starting at our previously defined starting index.

The parameters after these first two, square and trapezoid in our case, are whatever should be inserted starting at the start index.

You can add another array to your array using `concat()` method.

For Example:

```javascript
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];

let arr = arr1.concat(arr2);

console.log(arr);
```

This will output:

```console
[ 1, 2, 3, 4, 5, 6 ]
```

We can use concat() method to directly add either a single value, or comma-seperate multiple values.

ARR = ARR1.concat(1,3,4);

### Deleting elements

There are several ways to delete elements from an array.

To Remove last element, you can use `pop()`. For Example

```javascript
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9]
arr.pop();
```

This will result:

```console
[ 1, 2, 3, 4, 5, 6, 7, 8 ]
```

To delete the first element, you can use `shift()`. This causes all other indices to be reduced by one. For Example:

```javascript
arr.shift();
```

This will output:

```console
[ 2, 3, 4, 5, 6, 7, 8 ]
```

We can also use splice to delete values. We specify the index from where we want to start deleting, and then the number of elemets we want to delete.

```javascript
arr.splice(1, 3);
```

Afrer this, the value of the array is as follows:

```console
[ 2, 6, 7, 8 ]
```

If you're relying on index or lengh of an array for some reason or real use case; you can use delete operator to delete any element without changing any of the later indices. For Example:

```javascript
delete arr[0];
```

The array then becomes:

```console
[ <1 empty item>, 6, 7, 8 ]
```

### Finding Elements

We can use `find()` method to check whether a value is present in an array. It actually executes on every lement in the array until it finds a match, and i it does not, then it will return `undefined`.

To know on what position an element is, we can use the `index()` method. It returns the index on which the value is found.

If a value occurs in an array more than once, it will return the first occurrence. If the value is not found, it will return -1. For Example:

```javascript
arr = [2, 6, 7, 8];

let findIndex = arr.indexOf(6);
let findIndex = arr.indexOf(10);

console.log(findIndex, findIndex2);
```

So, the first one will return 1 since that is the index position of 6 in the array. The second one will return -1 because the array does not contain 10.

To find the next occurrence of the specified number, you can add a second argument to indexOf(), specifying from which position it should start searching. For Example:

```javascript
arr = [2, 6, 7, 8];
let findIndex3 = arr.indexOf(6, 2);
```

In this case, the value of findIndex3 will be -1, because 6 cannot be found starting from index 2.

To find the last occurrence of same value happening multiple times in an array, we can use lastIndexOf() method. For Example:

```javascript
let animals = ["dog", "horse", "cat", "platypus", "dog"];
let lastDog = animals.lastIndexOf("dog");
```

The value of lastDog will be 4 because that is the last occurrence of dog in the array.

### Sorting

In JS, a built-in method `sort()` can sort numbers from small to high and strings A-Z.

For Example:

```javascript
let names = ["James", "Alicia", "Fatiha", "Maria", "Bert"];
names.sort();
```

The values of names after soring is as follows:

```console
[ 'Alicia', 'Bert', 'Fatiha', 'James', 'Maria' ]
```

For numbers, it is sorting them in ascending order, as you can see in the following code snippet:

```javascript
let ages = [18, 72, 33, 56, 40];
ages.sort();
```

After executing this sort() method, the value of ages is:

```console
[ 18, 33, 40, 56, 72 ]
```

### Reversing

The elements of the array can be reversed by calling the built-in method, reverse(), on an array. It puts the last element first, and the first element last. It does not matter whether the array is sorted or not; it just reverses the order.

For Example:

```javascript
let names = ["James", "Alicia", "Fatiha", "Maria", "Bert"];
names.reverse();
```

The new order will be:

```console
[ 'Maria', 'James', 'Fatiha', 'Bert', 'Alicia' ]
```

## Multidimensional Arrays

Arrays can contain any data type; in this sense, they can also contain other arrays, and can contain arrays inside array inside array and so on. This is called a multidimensional array.

It's an array of arrays: a list of lists. For Example:

```javascript
let someValues1 = [1, 2, 3];
let someValues2 = [4, 5, 6];
let someValues3 = [7, 8, 9];

let arrOfArrays = [someValues1, someValues2, someValues3];

let arrOfArrays2 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
```

To Access Elements of the inner arrays, you can specify an index twice.

ARRAY[0][1]; => 0 is Index of Array; 1 is Index Position inside Array 0.

For Example:

```javascript
let value1 = arrOfArrays[0][1];
```

The statement will grab the first array because it has an index position of 0. From this first array, it will take the second value, because it has an index position of 1. Then it stores this value in value1. That means the value of value1 will be 2.

It can go many levels deep. For Example:

```javascript
arrOfArraysOfArrays = [arrOfArrays, arrOfArrays, arrOfArrays];
```

This is what the array looks like in terms of values:

```console
[
  [ [ 1, 2, 3 ], [ 4, 5, 6 ], [ 7, 8, 9 ] ],
  [ [ 1, 2, 3 ], [ 4, 5, 6 ], [ 7, 8, 9 ] ],
  [ [ 1, 2, 3 ], [ 4, 5, 6 ], [ 7, 8, 9 ] ]
]
```

To get the middle element of this array, which is the value 5, belonging to the second array of arrays. It is done like this:

```javascript
let middleValue = arrOfArraysOfArrays[1][1][1];
```

The first step is to get the second array of arrays, so index 1. Then we need to get the second array of this one, which again is index 1. Now we reach the level of the values, and we need the second value, so again we use index 1.

This is useful in Matrices.

## Objects in JavaScript

Objects is another complex data structure that can contain more than one value: objects

Objects are very useful and can be used to describe real-life objects as well as more complex abstract concepts that allow for more flexibility in your code.

Arrays are objects with indexed properties, and all the other objects are objects with named properties.

That means, unlike Arrays which automatically generate index number, we can give it a custom descriptive name in Objects.

An object is a chance to group multiple variables into one. This is done with curly brackets: { and }.

For Example:

```javascript
let dog = { 
  dogName: "JavaScript",
  weight: 2.4,
  color: "brown",
  breed: "chihuahua",
  age: 3,
  burlgarBitter: true
}
```

To remember the equation of whether something should be a property, try the following template sentence in your head.

**\*objectname\*** has a(n) _\*property name\*_

To access the properties of this object in a very similar way as we would with array; instead of using the index number, we can use the name of the property to get the value. For Example:

```javascript
let dogColor1 = dog["color"];
```

There is another way to do this. Instead of the square brackets [], the property name can also be added to the object name with a dot in between. For Example:

```javascript
let dogColor2 = dog.color;
```

It is the same way how we call methods. The difference between properties and methods is the lack of parentheses () for properties.

## Updating Objects

We can change the value of the properties of the objects. Again, this is similar to an array because an array is an object as well, but for properties, we have two options. For Example:

```javascript
dog["color"] = "blue";
dog.weight = 2.3;
```

It's useful to note that if we change the data type of one of our properties. For Example:

```javascript
dog["age"] = "three";
```

This is not a problem. JavaScript will just change the whole value and data type to the new situation.

Another element to note is that we are now using the literal string values to refer to the object's properties, but we can also work with variables to achieve this. So, for example:

```javascript
let variable = "age";
console.log(dog[variable]);
```

This will still output three, as we just changed the value of age to three. If we change the value of the variable to another dog property, we will be accessing another property, like this:

```javascript
variable = "breed";
console.log(dog[variable]);
```

This will print chihuahua. And when we update the value accessing this way, it is the exact same as when we would have accessed it with the literal string:

```javascript
dog[variable] = "dachshund";
console.log(dog["breed"]);
```

So, this will log dachshund to the console.
