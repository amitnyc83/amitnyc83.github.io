---
layout: post
title:      "What is  Scope & Hoisting"
date:       2019-04-08 09:10:17 -0400
permalink:  what_is_scope_and_hoisting
---


In JavaScript there are two types of scope: (before ES6)

1. Local scope 
2. Global scope 

Introduced in ES6 is **Block scope** where keywords **let** and **const** were introduced. What happens in the block stays in the block if you declare variables with **let** and **const**. Something to remember is that any variable created without the **const**, **let** or **var** keyword are always globally-scoped, regardless of where they sit in your code. Not a good idea if that variable holds a secret password. Making a variable available in places that shouldn't have access to it can lead to bad things and make debugging process more complex. The more pieces of code that can access a given variable, the more places you have to check for bugs. 

The simplified meaning of Scope is **where something is available**.  


Any variable declared outside of a function belongs to the global scope and is accessible from anywhere in your code. Variables defined inside a function are in the local scope and can only be accessed from within the function. Each function when invoked creates a new scope.


<h2>Global Scope </h2>

A variable declared outside of a function, become Global. Variables in the Global scope can be accessed and altered in any other scope as they live in the top-level scope.

>Quick Tip: Global variables should be used sparingly if at all

It is also important to be aware that if you do not declare a variable using one of the keywords **var**, **let** or **const** in your codebase then the varibale is given a global scope. 

<h2>Local Scope</h2>

Variables defined inside a function are in the local scope.




JavaScript has three different keywords to declare a variable; **var**, **let** & **const**. It is best pratice to use **const** as much as possible, and **let**  in the case of loops and reassignment. These two keywords provide **Block scope** variables (and constants) in JavaScript. Before ES2015, JavaScript only had two type of scope **Global scope** and **Function scope**.


![](https://cdn-images-1.medium.com/max/1600/1*pRBQHfaeJcOmoEK_WG2fLw.png)


<h2>Block Statements</h2>

Block statements like **if** and **switch** conditions or **for** and **while** loops, unlike functions, do not create new scope. Variables defined inside of a block statement will remain in  the scope they were already in.

```
if (true) {
    // this 'if' conditional block doesn't create a new scope
    var name = 'Hammad'; // name is still in the global scope
}

console.log(name); // logs 'Hammad'
```

If you use the **let** and **const** keywords inside a block statement, they will support local scope and you won't be able to access them outside of its scope. 

```
if (true) {
    // this 'if' conditional block doesn't create a scope

    // name is in the global scope because of the 'var' keyword
    var name = 'Hammad';
    // likes is in the local scope because of the 'let' keyword
    let likes = 'Coding';
    // skills is in the local scope because of the 'const' keyword
    const skills = 'JavaScript and PHP';
}

console.log(name); // logs 'Hammad'
console.log(likes); // Uncaught ReferenceError: likes is not defined
console.log(skills); // Uncaught ReferenceError: skills is not defined
```



> Global scope lives as long as your application lives. Local Scope lives as long as your functions are called and executed.
> 



<h2>Hoisting</h2>


First rule of Hoisting in JavaScript is that only declarations are hoisted, not initializations(expressions). To avoid bugs and confusion, always declare all variables at the beginning of every scope. Since this is how JavaScript interprets the code, it is always a good rule to follow. **ES6 Arrow functions are not hoisted so they have to be defined before they are used.**

Here is a simple example of a **function declaration** and a **function expression**. 

```
// Function declaration
function add(num1, num2) {
	return num1 + num2;
}

// Function expression
var add = function (num1, num2) {
	return num1 + num2;
};
```

A Javascript **function declaration** must begin with the** function** keyword. A function can also be defined using an expression. When a function is stored in a variable, it becomes a **function expression**.

**Function declarations** load before any code is excuted while **function expressions** load only when the interpreter reaches that line of code. **Function declarations** are hoisted to the top of other code while **function expressions** aren't hoisted.


JavaScript puts **function declarations** into memory before it excutes any code and that allows you to use a function before you declare it in your code. Here's a simple example: 

```
catName("Muffin');
function catName(name) {
console.log("My cat's name is " + name);  // My cat's name is Muffin
}
```

In the example above, function catName is a **function declaration** so when the code runs, the JavaScript compiler hoists the function to the top of the code and saves it in memory. This is how it looks to the compiler when catName("Muffin") is called:

```
//Hoisted
function catName(name) {
console.log("My cat's name is " + name);
}

catName("Muffin")
```



but if the function was saved in a variable like the example below: 

```
myName=("Muffin")

var myName = function catName(name) {
console.log("My cat's name is " + name);
}
```

We will get back a **TypeError: myName is not a function**. This bascially goes back to scoping, where the variable with the var keyword is hoisted and held in memory(but not the function assignment). So in this example, this is how it look to the compiler: 

```
var myName 

myName("Muffin")

myName = function catName(name) {
console.log("My cat's name is " + name);
}
```

The compiler knows there is a variable **myName** but does not know it has been assigned to a function; hence why we get the **myName is not a function TypeError**



In Fig.1, we expect the result of the console.log to be: `ReferenceError: hoist is not defined` but instead the output is `undefined`. 


Fig.1
```
console.log(hoist); // Output: undefined

var hoist = 'The variable has been hoisted.';
```

Why did this happen?

JavaScript hoisted the variable declaration. This is how the code above looked like to the interpreter: 



Fig.2
```
var hoist;
// the variable is hoisted and declared but assigned the value the undefined. By using the keyword undefined, it is saving some space in memory.  

console.log(hoist); // Output: undefined
hoist = 'The variable has been hoisted.';
```











