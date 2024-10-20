# javascript-interview-questions
javascript-interview-questions

### Table of Contents
<!-- TOC_START -->
| No. | Questions |
| --- | --------- |
| 1 | [What are the scope in JavaScript](#what-are-the-possible-ways-to-create-objects-in-javascript) |
| 2 | [How many types of the scope in JavaScript](#How-many-types-of-the-scope-in-JavaScript) |
| 3 | [What is global scope in JavaScript](#What-is-global-scope-in-JavaScript) |
| 4 | [What is function scope in JavaScript](#What-is-function-scope-in-JavaScript) |
| 5 | [What is block scope in JavaScript](#What-is-block-scope-in-JavaScript) |
| 6 | [What is scope chain in JavaScript](#What-is-scope-chain-in-JavaScript) |


<!-- TOC_END -->


<!-- QUESTIONS_START -->
1. ## What are the scope in JavaScript

  Scope is a specific region in the code where a variable is defined, accessible, and recognized. Outside this region, the variable cannot be accessed or recognized.

2. ## How many types of the scope in JavaScript

  JavaScript has three types of scope:

    1. Global Scope:
    2. Function Scope:
    3. Block Scope:

3. ## What is global scope in JavaScript
  <b>Definition: </b>Variables declared outside of any function or block have global scope.
  <b>Access: </b> Global variables can be accessed from anywhere in the code, including inside functions and blocks.
  
  <b>Example: </b>
  ```javascript
    var globalVar = "I am global scope";  // global scope
    function showGlobal() {
      console.log(globalVar);  // can access globalVar
    }

    showGlobal();  // Output: I am global scope
  ```

4. ## What is function scope in JavaScript
  <b>Definition: </b>Variables declared inside a function (using var) are function-scoped. They are only accessible within that function.
  <b>Access: </b> Cannot be accessed outside the function they are declared in.
  
  <b>Example: </b>
  ```javascript
    function functionScope() {
    var localVar = "I am local";  // function scope
    console.log(localVar);  // accessible inside function
  }

    functionScope();
    console.log(localVar);  // Error: localVar is not defined
  ```

5. ## What is block scope in JavaScript
  <b>Definition: </b>Variables declared with let or const inside a block (denoted by {}) are block-scoped.
  <b>Access: </b> Only accessible within that block (e.g., inside loops, if statements).
  
  <b>Example: </b>
  ```javascript
    if (true) {
      let blockScoped = "I am block-scoped";
      const anotherBlockScoped = "I am also block-scoped";
      console.log(blockScoped);  // accessible inside block
    }

    console.log(blockScoped);  // Error: blockScoped is not defined
  ```

6. ## What is scope chain in JavaScript
  When you try to access a variable, JavaScript will look for it first in the current scope, then move up to the next outer scope, and so on, until it finds the variable or reaches the global scope. This is called lexical scoping.
  
  <b>Example: </b>
  ```javascript
    let globalVar = "Global";
    function outer() {
      let outerVar = "Outer";
      
      function inner() {
        let innerVar = "Inner";
        console.log(innerVar);  // Inner
        console.log(outerVar);  // Outer
        console.log(globalVar);  // Global
      }
      inner();
    }
    outer();
  ```
    inner() can access innerVar, outerVar, and globalVar due to the scope chain.
    outer() cannot access innerVar but can access outerVar and globalVar.

   **[⬆ Back to Top](#table-of-contents)**