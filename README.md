# js-concepts

## Closure:

Javascript variable can belong global and local scope.  
Global variables can be made local(private) with closures.

In the last example, a is a global variable.

In a web page, global variables belong to the window object.

Global variables can be used (and changed) by all scripts in the page (and in the window).

In the first example, a is a local variable.

A local variable can only be used inside the function where it is defined. It is hidden from other functions and other scripting code.

Global and local variables with the same name are different variables. Modifying one, does not modify the other.

Closure example:

```
var add = (function() {
  var counter = 0;
  return function() { counter + 1; return counter }
})()
self invocking function
```

## Hoisting

Hoisting in mechanisum where variables and function declarations are moved to the top of their scope before code execution.

### undefined vs ReferenceError

In JavaScript, an undeclared variable is assigned the value undefined at execution and is also of type undefined.  

```
console.log(typeof variable); // Output: undefined
```

variable is undefines as its not declared and assigned.

```
console.log(variable); // Output: ReferenceError: variable is not defined
```
When we are trying to access previously undeclared variabled, we can ReferenceError.

All variable and function declarations are hoisted to the top of their scope. Variable declarations are processed before any code is executed.

However, in contrast, undeclared variables do not exist until code assigning them is executed.
Therefore, assigning a value to an undeclared variable implicitly creates it as a global variable when the assignment is executed. This means that, all undeclared variables are global variables.

#### var
The scope of a variable declared with the keyword var is its __current execution context__. This is either the enclosing function or for variables declared outside any function, global.  

### Strict Mode
By enabling strict mode, we opt into a restricted variant of JavaScript that will not tolerate the usage of variables before they are declared.

```
'use strict';
```

## ES6

#### let

Before we start, to be noted is the fact that variables declared with the keyword let are block scoped and not function scoped.

JavaScript hoists variables declared with es6 let and const. The difference in this case is how **it initialises them**.
Variables declared with let and const remain uninitialised at the beginning of execution whilst variables declared with var are __initialised with a value of undefined__.

## Hoisting functions

JavaScript functions can be loosely classified as the following:

1.Function declarations
1.Function expressions

### Function declarations
Are hoisted completely to the top. Now, we can understand why JavaScript enable us to invoke a function seemingly before declaring it.

### Function expressions
Function expressions, however are not hoisted.

```
expression(); //Output: "TypeError: expression is not a function

var expression = function() {
  console.log('Will this work?');
};
```
Combination of a function declaration and expression.

```
expression(); // Ouput: TypeError: expression is not a function

var expression = function hoisting() {
  console.log('Will this work?');
};
```
See above, the variable declaration var expression is hoisted but it’s assignment to a function is not. Therefore, the intepreter throws a TypeError since it sees expression as a variable and not a function.

### Order of precedence

1.Variable assignment takes precedence over function declaration
1.Function declarations take precedence over variable declarations

```
var double = 22;

double(num) {
  return (num * 2)
}

console.log(typeof double); // Output: number
```

#### Function declarations over variable declarations

```
var double;

function double(num) {
  return (num*2);
}

console.log(typeof double); // Output: function

```

### Hoisting classes

Same as function

### The modern mode, "use strict"
For a long time, JavaScript evolved without compatibility issues. New features were added to the language while old functionality didn’t change.

That had the benefit of never breaking existing code. But the downside was that any mistake or an imperfect decision made by JavaScript’s creators got stuck in the language forever.

#### “use strict”
The directive like "use strict" or 'use strict' is used to run the JS code in modern way. Will give the warning / errors while using old ways.

```
"use strict";

// this code works the modern way
```

#### Ensure that “use strict” is at the top

```
alert("some code");
// "use strict" below is ignored--it must be at the top

"use strict";

// strict mode is not activated
```
how to actually ```use strict``` in the console?

```
'use strict'; <Shift+Enter for a newline>
//  ...your code
<Enter to run>
```

__##'use strict' is unnecessary when using ES6 modules ('import' syntax). Its strict out of the box##__




