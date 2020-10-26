---
title: JavaScript Questions
layout: layouts/page.njk
permalink: /questions/javascript-questions/index.html
---

* Explain event delegation.
  * Event Delegation allows you to avoid adding event listeners to specific nodes; instead, the event listener is added to one parent. 
   ```
   document.getElementById("parent-list").addEventListener("click", function(e) {
	    if(e.target && e.target.nodeName == "LI") {
		    console.log("List item was clicked!");
	    }
  });
   ```
  * The benefits of event delagation are useful in apps that have elements that are constantly being dynamically created because they can be move to the parent element that is delegated to the same event.

  * another benefit is that the memory footprint used by event listeners goes down since the number of event bindings go down. With event delegation, you're free to destroy child elements without risk of forgetting to "unbind" their event listeners. 

* Explain how `this` works in JavaScript.
  * `This` is the object executing the function.
    * in a global context, `this` refers to the global oject, usually the window.
    * in an object method, `this` refers to the oject in which it is called. 
  * Can you give an example of one of the ways that working with `this` has changed in ES6?
    * the ability to use bind(`this`) at the end of a function to allow `this` to work in anonymous functions.
    * `this` inside fat arrow functions points to whatever the value of `this` inside the upper function is. Hence, the value of `this` is lexically scoped

* Explain how prototypal inheritance works.
  * Prototypal inheritance allows an object to inherit properties from another object.

* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  * undefined is a variable that has been declared but no value exists and is a type of itself 'undefined'
  * null is a value of a variable and is a type of object. 
  * undelcared variables is a variable that has not been declared or initialized with a const/let/var keyword.

  * You can check this with by using `typeof`
    ``` 
    console.log(typeof variable)
    ```

* What is a closure, and how/why would you use one?
  * Closures are important becuase they control what is and isn't in scope in a particular function, along with which variables are shared between sibling functions in the same containing scope. 
  * Closures give you access to an outer function's scope from an inner function. 
  In javascript, closures are created every time a function is created. 
  * Closures are often used to give objects data privacy. Data privacy is an essential property that helps us program to an interface, not an implementation. 
  * To use, define a function inside another function, and return it or passt it to another function. 
  * More on closures: [link](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36)

* What language constructions do you use for iterating over object properties and array items?
  * for loop, for each, map, reduce

* Can you describe the main difference between the `Array.forEach()` loop and `Array.map()` methods and why you would pick one versus the other?
  * forEach() executes a provided function once for each array element.
  * map() creates a new array with the results of calling a provided function on every element in the calling array. Map() utilizes return values and actually returns a new Array of the same size. Map() allocates and stores the return values whereas forEach() throws away return values and always returns undefined.

  * forEach() affects and changes our original Array, whereas map() returns an entirely new Array - thus leaving the original array unchanged. 
  * forEach() would be better when we are not planning on changing the array and just want to do something with it. 
  * map() would be better when we are changing or altering the data. It is faster than forEach and returns a new Array.

* What's a typical use case for anonymous functions?
  * an anonymous function is a function without a name. An anonymous function is often not accessible after its initial creation. 
  * Anonymous functions can be used to store a bit of functionality in a variable and pass that piece of functionality around. It is usually used as arguments of another function. 

* What's the difference between host objects and native objects?
  * Host Object: object supplied by the host environment to complete the execution environment of ECMA script
  * Native Object: are standard built-in objects provided by JavaScript. Native objects is sometimes referred to as "Global Objects" since they are objects Javascript has provided natively available to use. 

* Explain the difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
  * function Person() {} declares a function statement but does not execute it. 
  * var person = Person() A variable "var person" has been defined an containes a value reference to a Person function. Any JS Expressions always return a value.
  * var person = new Person() is a class constructor.

* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
  * function foo() is an actual named function whereas var foo = function is a regular variable declaration with an anonymous function attached to it. 

* Can you explain what `Function.call` and `Function.apply` do? What's the notable difference between the two?
  * call() passes all arguments after the first one on to the invoked function.
  ```
  let customer1 = { name: 'Leo', email: 'leo@gmail.com' };
  let customer2 = { name: 'Nat', email: 'nat@hotmail.com' };

  function greeting(text) {
    console.log(`${text} ${this.name}`);
  }

  greeting.call(customer1, 'Hello'); // Hello Leo
  greeting.call(customer2, 'Hello'); // Hello Nat
  ```
  * apply() takes an array as its second argument and passes the members of that array as arguments.
  ```
  let customer1 = { name: 'Leo', email: 'leo@gmail.com' };
  let customer2 = { name: 'Nat', email: 'nat@hotmail.com' };
  function greeting(text, text2) {
    console.log(`${text} ${this.name}, ${text2}`);
  }
  greeting.apply(customer1, ['Hello', 'How are you?']); // output Hello Leo, How are you?
  greeting.apply(customer2, ['Hello', 'How are you?']); // output Hello Nat, How are you?
  ```

* Explain `Function.prototype.bind`.
  
* What's the difference between feature detection, feature inference, and using the UA string?
* Explain "hoisting".
* Describe event bubbling.
* Describe event capturing.
* What's the difference between an "attribute" and a "property"?
* What are the pros and cons of extending built-in JavaScript objects?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Why is it called a Ternary operator, what does the word "Ternary" indicate?
* What is strict mode? What are some of the advantages/disadvantages of using it?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?
* What are the differences between variables created using `let`, `var` or `const`?
* What are the differences between ES6 class and ES5 function constructors?
* Can you offer a use case for the new arrow `=>` function syntax? How does this new syntax differ from other functions?
* What advantage is there for using the arrow syntax for a method in a constructor?
* What is the definition of a higher-order function?
* Can you give an example for destructuring an object or an array?
* Can you give an example of generating a string with ES6 Template Literals?
* Can you give an example of a curry function and why this syntax offers an advantage?
* What are the benefits of using `spread syntax` and how is it different from `rest syntax`?
* How can you share code between files?
* Why you might want to create static class members?
* What is the difference between `while` and `do-while` loops in JavaScript?
* What is a promise? Where and how would you use promise?

## Coding questions
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* What will be returned by each of these?
```javascript
console.log("hello" || "world")
console.log("foo" && "bar")
```
* Write an immediately invoked function expression (IIFE)
