---
title: "Array Methods"
seoDescription: "Array, methods"
datePublished: Mon Jul 10 2023 20:37:06 GMT+0000 (Coordinated Universal Time)
cuid: cljxbqxi7000209idftco3848
slug: array-methods
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689001878066/39df84d3-fe23-4777-b60b-28509b0715e6.png
tags: javascript, developer, frontend-development, vanilla-js-1, technicalwriting-javascript-frontenddevelopment

---

### Introduction

An array is a type of data structure in programming most especially in Javascript language, they are used to store data in such a way they can be easily accessed. An array can consist of strings, integers, objects, floats, and arrays.

This article will give a proper guide on how to manipulate an array using these methods

`POP()`

`PUSH()`

`UNSHIFT()`

`SHIFT()`

`SLICE()`

`SPLICE()`

### **PUSH() Method**

The `push()` method is used to add an element at the end of an array. For example,

```javascript
const arr = [1, 2, 3, 4, 5];
arr.push(6);
console.log(arr);
// output arr = [1, 2, 3, 4, 5, 6]
```

### POP() Method

The `pop()` method is used to remove the last element from an array. For example,

```javascript
const arr = [1, 2, 3, 4, 5, 6];
arr.pop();
console.log(arr);
//output arr = [1, 2, 3, 4, 5];
```

### SHIFT() Method

The `shift()` method is used to remove the first element from an array. For example,

```javascript
const arr = [1, 2, 3, 4, 5, 6];
arr.shift();
console.log(arr);
//the output arr = [2, 3, 4, 5, 6];
```

### UNSHIFT() Method

The `unshift()` method is used to add an element at the beginning of an array. For example,

```javascript
const arr = [1, 2, 3, 4, 5, 6];
arr.unshift(0);
console.log(arr); 
//output arr = [0, 1, 2, 3, 4, 5, 6];
```

### SLICE() Method

The `slice()` method is used to copy or extract a given number of elements to a new array, leaving the array it is called upon untouched. `slice()` takes only 2 parameters — the first is the index of the first element to include in the slice. The default value is 0. The second is the index at which to stop extraction. For example,

```javascript
const arr = [1, 2, 3, 4, 5, 6];
const array = arr.slice(1, 3);
console.log(array);
// output arra = [2,3];
```

If the parameter is left off, the array's elements will all be returned in their entirety, without omission. For example,

```javascript
const arr = [1, 2, 3, 4, 5, 6];
const array = arr.slice();
console.log(array);
// output arra = [1, 2, 3, 4, 5, 6];
```

### SPLICE() Method

The `splice()` method in JavaScript is used to change the content of an array by removing or replacing existing elements and/or adding new elements in place. It is a mutating method, which means that it changes the original array.

It can take up to three parameters. The first parameter stated where the cutting will start while the second parameter stated where the cutting will end. for example,

```javascript
const arr = [1, 2, 3, 4, 5, 6];
arr.splice(1, 3);
console.log(arr);
//the output will be arr = [1, 5, 6]
```

the third parameter can be comprised of one or more elements to add to the array. for example,

```javascript
const arr = [1, 2, 3, 4, 5, 6];
arr.splice(1, 3, 4, 5);
console.log(arr);
//the output will be  arr = [1, 4, 5, 5, 6]
```

### CONCLUSION

From this above explanation, I have been able to enlighten you on how an array can be manipulated. For further explanation check this documentation [here](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/).