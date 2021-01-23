---
title: "Javascript Shortcut Techniques"
layout: post
date: 2021-01-23 16:20
image: /assets/images/markdown.jpg
headerImage: false
tag:
- javascript techniques
- javascript 
star: true
category: blog
author: kushalagrawal
description: Javascript Shortcut Techniques
---

<img alt="Image for post" class="fd er en hh w" src="https://miro.medium.com/max/3200/1\*Llp0NKRQruyekQKqxwPF7w.png" width="1600" height="686" srcSet="https://miro.medium.com/max/552/1\*Llp0NKRQruyekQKqxwPF7w.png 276w, https://miro.medium.com/max/1104/1\*Llp0NKRQruyekQKqxwPF7w.png 552w, https://miro.medium.com/max/1280/1\*Llp0NKRQruyekQKqxwPF7w.png 640w, https://miro.medium.com/max/1456/1\*Llp0NKRQruyekQKqxwPF7w.png 728w, https://miro.medium.com/max/1632/1\*Llp0NKRQruyekQKqxwPF7w.png 816w, https://miro.medium.com/max/1808/1\*Llp0NKRQruyekQKqxwPF7w.png 904w, https://miro.medium.com/max/1984/1\*Llp0NKRQruyekQKqxwPF7w.png 992w, https://miro.medium.com/max/2160/1\*Llp0NKRQruyekQKqxwPF7w.png 1080w, https://miro.medium.com/max/2700/1\*Llp0NKRQruyekQKqxwPF7w.png 1350w, https://miro.medium.com/max/3200/1\*Llp0NKRQruyekQKqxwPF7w.png 1600w" sizes="1600px"/>

In this article I’ll share a few things I learned in JavaScript that I wished I had learned sooner. I’m not saying you should or shouldn’t use these techniques. Just that they exist, and understanding them will hopefully help you along.

The Ternary Operator
====================

This is a great code saver when you want to write an `if..else` statement in just one line.

The Long Method:

```
const x = 20;
let answer;if (x > 10) {
    answer = "greater than 10";
} else {
    answer =  "less than 10";
}
```

The Shortcut:

```
const answer = x > 10 ? "greater than 10" : "less than 10";//OR you can also nest if statement like thisconst answer = x > 10 ? "greater than 10" : x < 5 ? "less than 5" 
: "between 5 and 10";
```

Short-circuit Evaluation Shorthand
==================================

When assigning a variable value to another variable, you may want to ensure that the source variable is not null, undefined, or empty. You can either write a long `if` statement with multiple conditionals, or use a short-circuit evaluation.

The Long Method:

```
if (variable1 !== null || variable1 !== undefined || variable1 !== '') {
     let variable2 = variable1;
}
```

The Shortcut:

```
const variable2 = variable1  || 'new';
```

Declaring Variables Shorthand
=============================

It’s good practice to declare your variable assignments at the beginning of your functions. This shorthand method can save you lots of time and space when declaring multiple variables at the same time.

The Long Method:

```
let x;
let y;
let z = 3;
```

The Shortcut:

```
let x, y, z=3;
```

JavaScript For Loop Shorthand
=============================

This little tip is really useful if you want plain JavaScript and don’t want to rely on external libraries.

The Long Method:

```
const fruits = \['mango', 'peach', 'banana'\];
for (let i = 0; i < fruits.length; i++)
```

The Shortcut:

```
for (let fruit of fruits)
```

If you just wanted to access the index, do:

```
for (let index in fruits)
```

This also works if you want to access keys in a literal object:

```
const obj = {continent: 'Africa', country: 'Kenya', city: 'Nairobi'}
for (let key in obj)
  console.log(key) // output: continent, country, city
```

Short-circuit Evaluation
========================

Instead of writing six lines of code to assign a default value if the intended parameter is null or undefined, we can simply use a short-circuit logical operator and accomplish the same thing with just one line of code.

The Long Method:

```
let dbHost;
if (process.env.DB\_HOST) {
  dbHost = process.env.DB\_HOST;
} else {
  dbHost = 'localhost';
}
```

The Shortcut:

```
const dbHost = process.env.DB\_HOST || 'localhost';
```

Object Property Shorthand
=========================

Defining object literals in JavaScript makes life much easier. ES6 provides an even easier way of assigning properties to objects. If the variable name is the same as the object key, you can take advantage of the shorthand notation.

The Long Method:

```
const x = 1920, y = 1080;
const obj = { x:x, y:y };
```

The Shortcut:

```
const obj = { x, y };
```

Arrow Functions Shorthand
=========================

Classical functions are easy to read and write in their plain form, but they do tend to become a bit verbose and confusing once you start nesting them in other function calls.

The Long Method:

```
function sayHello(name) {
  console.log('Hello', name);
}setTimeout(function() {
  console.log('Loaded')
}, 2000);list.forEach(function(item) {
  console.log(item);
});
```

The Shortcut:

```
sayHello = name => console.log('Hello', name);setTimeout(() => console.log('Loaded'), 2000);list.forEach(item => console.log(item));
```

It’s important to note that the value of `this` inside an arrow function is determined differently than for longhand functions, so the two examples are not strictly equivalent.

Implicit Return Shorthand
=========================

Return is a keyword we use often to return the final result of a function. An arrow function with a single statement will implicitly return the result its evaluation (the function must omit the braces (`{}`) in order to omit the return keyword).

To return a multi-line statement , it’s necessary to use `()` instead of `{}` to wrap your function body. This ensures the code is evaluated as a single statement.       

The Long Method:

```
function calcCircumference(diameter) {
  return Math.PI \* diameter
}
```

The Shortcut:

```
calcCircumference = diameter => (
  Math.PI \* diameter;
)
```

Template Literals
=================

All you need to do is use is the backtick, and `${}` to enclose your variables.

The Long Method:

```
const welcome = 'You have logged in as ' + first + ' ' + last + '.'const db = 'http://' + host + ':' + port + '/' + database;
```

The Shortcut:

```
const welcome = \`You have logged in as ${first} ${last}\`;const db = \`http://${host}:${port}/${database}\`;
```

Destructuring Assignment Shorthand
==================================

If you are working with any popular web framework(ReactJs , Angular etc), there are high chances you will be using arrays or data in the form of object literals to pass information between components and APIs. Once the data object reaches a component, you’ll need to unpack it.

The Long Method:

```
const observable = require('mobx/observable');
const action = require('mobx/action');
const runInAction = require('mobx/runInAction');const store = this.props.store;
const form = this.props.form;
const loading = this.props.loading;
const errors = this.props.errors;
const entity = this.props.entity;
```

The Shortcut:

```
import { observable, action, runInAction } from 'mobx';const { store, form, loading, errors, entity } = this.props;
```

You can even assign your own variable names:

```
const { store, form, loading, errors, entity:contact } = this.props;
```

Spread Operator Shorthand
=========================

The **spread operator**, introduced in ES6, has several use cases that make JavaScript code more efficient and fun to use. It can be used to replace certain array functions. The spread operator is simply a series of three dots.

The Long Method:

```
// joining arrays
const odd = \[1, 3, 5\];
const nums = \[2 ,4 , 6\].concat(odd);// cloning arrays
const arr = \[1, 2, 3, 4\];
const arr2 = arr.slice()
```

The Shortcut:

```
// joining arrays
const odd = \[1, 3, 5 \];
const nums = \[2 ,4 , 6, ...odd\];
console.log(nums); // \[ 2, 4, 6, 1, 3, 5 \]// cloning arrays  
const arr = \[1, 2, 3, 4\];
const arr2 = \[...arr\];
```

Unlike the `concat()` function, you can use the spread operator to insert an array anywhere inside another array.

```
const odd = \[1, 3, 5 \];
const nums = \[2, ...odd, 4 , 6\];
```

You can also combine the spread operator with ES6 destructuring notation:

```
const { a, b, ...z } = { a: 1, b: 2, c: 3, d: 4 };
console.log(a) // 1
console.log(b) // 2
console.log(z) // { c: 3, d: 4 }
```

Array.find Shorthand
====================

If you have ever been tasked with writing a find function in plain JavaScript, you would probably have used a `for` loop. In ES6, a new array function named `find()` was 
introduced.

The Long Method:

```
const pets = \[
  { type: 'Dog', name: 'Max'},
  { type: 'Cat', name: 'Karl'},
  { type: 'Dog', name: 'Tommy'},
\]function findDog(name) {
  for(let i = 0; i<pets.length; ++i) {
    if(pets\[i\].type === 'Dog' && pets\[i\].name === name) {
      return pets\[i\];
    }
  }
}
```

The Shortcut:

```
pet = pets.find(pet => pet.type ==='Dog' && pet.name === 'Tommy');
console.log(pet); // { type: 'Dog', name: 'Tommy' }
```

Double Bitwise NOT Shorthand
============================

Bitwise operators are one of those features you learn about in beginner JavaScript tutorials and you never get to implement them anywhere. Besides, who wants to work with ones and zeroes if you are not dealing with binary?

There is, however, a very practical use case for the Double Bitwise NOT operator. You can use it as a replacement for `Math.floor()`. The advantage of the Double Bitwise 
NOT operator is that it performs the same operation much faster.

The Long Method:

```
Math.floor(4.9) === 4  //true
```

The Shortcut:

```
~~4.9 === 4  //true
```

Bitwise IndexOf Shorthand
=========================

When performing a lookup using an array, the `indexOf()` function is used to retrieve the position of the item you are looking for. If the item is not found, the value `-1` is returned. In JavaScript, `0` is considered ‘falsy’, while numbers greater or lesser than `0` are considered ‘truthy’. As a result, one has to write the correct code like this.

The Long Method:

```
if(arr.indexOf(item) > -1) { // Confirm item IS found}if(arr.indexOf(item) === -1) { // Confirm item IS NOT found}
```

The Shortcut:

```
if(~arr.indexOf(item)) { // Confirm item IS found}if(!~arr.indexOf(item)) { // Confirm item IS NOT found}
```

The `bitwise(~)` operator will return a truthy value for anything but `-1`. Negating it is as simple as doing `!~`. Alternatively, we can also use the `includes()` function:

```
if(arr.includes(item)) { // Returns true if the item exists, false if it doesn't}
```

Suggest One?
============

I really do love these and would love to find more, so please leave a comment if you know of one!
