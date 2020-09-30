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

