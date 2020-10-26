---
title: Coding Questions
layout: layouts/page.njk
permalink: /questions/coding-questions/index.html
---

Question: What is the value of `foo`?
```javascript
var foo = 10 + '20';
```
 - foo = 1020 because its a string concat operation

Question: What will be the output of the code below?
```javascript
console.log(0.1 + 0.2 == 0.3);
```
 - False because floating point numbers are rounded.
 - The expected result is 0.3000000000000004 == 0.3

Question: How would you make this work?
```javascript
add(2, 5); // 7
add(2)(5); // 7
```
Answer: 
```javascript
  function add(x, y) {
    if(arguments.length == 2) {
      return function(y) { 
        return x + y
      };
    };
    return x + y
  }
```

Question: What value is returned from the following statement?
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
 - "goh angasal a m'i"

Question: What is the value of `window.foo`?
```javascript
( window.foo || ( window.foo = "bar" ) );
```
 - window.foo = bar because the first window.foo is undefined so it will move to the next window.foo.  '||' means or. 

Question: What is the outcome of the two alerts below?
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```
- The first alert will return "Hello World" and the second one will return undefined since bar is not defined globally.

Question: What is the value of `foo.length`?
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
- The value will be 2.

Question: What is the value of `foo.x`?
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```
- undefined

Question: What does the following code print?
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
Promise.resolve().then(function() {
  console.log('three');
})
console.log('four');
```

Question: What is the difference between these four promises?
```javascript
doSomething().then(function () {
  return doSomethingElse();
});

doSomething().then(function () {
  doSomethingElse();
});

doSomething().then(doSomethingElse());

doSomething().then(doSomethingElse);
```

Question: What will the code below output to the console and why?
```javascript
(function(){
  var a = b = 3;
})();

console.log("a defined? " + (typeof a !== 'undefined'));
console.log("b defined? " + (typeof b !== 'undefined'));
```

Question: Consider the two functions below. Will they both return the same thing? Why or why not?
```javascript
function foo1()
{
  return {
      bar: "hello"
  };
}

function foo2()
{
  return
  {
      bar: "hello"
  };
}
```
