---
title: "JavaScript Basics"
seoTitle: "how I can return different data types and objects from JavaScript"
seoDescription: "Here are examples that demonstrate returning various data types and objects from functions in JavaScript, including numbers, strings, booleans, undefined,"
datePublished: Sat Oct 07 2023 01:18:34 GMT+0000 (Coordinated Universal Time)
cuid: clnfcjupj00010amlhf66g1z2
slug: javascript-basics
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/XmZ4GDAp9G0/upload/1cb93cd898d4c04096dbcaed97bfbae3.jpeg
tags: js, javascript

---

# how I can return different data types and objects from JavaScript functions

Here are examples that demonstrate returning various data types and objects from functions in JavaScript, including numbers, strings, booleans, undefined, null, objects, functions, arrays, promises, and generators:

```jsx
// Returning Numbers
function returnNumber() {
  return 42;
}

// Returning Strings
function returnString() {
  return "Hello, World!";
}

// Returning Booleans
function returnBoolean() {
  return true;
}

// Returning Undefined
function returnUndefined() {
  return undefined;
}

// Returning Null
function returnNull() {
  return null;
}

// Returning Objects (Custom Object)
function returnCustomObject() {
  return { name: "Alice", age: 25 };
}

// Returning Objects (Built-in Objects)
function returnBuiltInObject() {
  return new Date(); // Returns a Date object
}

// Returning Functions
function returnFunction() {
  return function() {
    console.log("I'm a function!");
  };
}

// Returning Arrays
function returnArray() {
  return [1, 2, 3, 4];
}

// Returning Promises
function returnPromise() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Promise resolved!");
    }, 1000);
  });
}

// Returning Generators
function* generatorFunction() {
  yield 1;
  yield 2;
  yield 3;
}

function returnGenerator() {
  return generatorFunction();
}

// Example usage
console.log(returnNumber());           // 42
console.log(returnString());           // "Hello, World!"
console.log(returnBoolean());          // true
console.log(returnUndefined());        // undefined
console.log(returnNull());             // null
console.log(returnCustomObject());     // { name: "Alice", age: 25 }
console.log(returnBuiltInObject());    // Current date and time
const returnedFunction = returnFunction();
returnedFunction();                    // "I'm a function!" (logs to console)
console.log(returnArray());            // [1, 2, 3, 4]
returnPromise().then(result => console.log(result)); // "Promise resolved!" (after 1 second)
const generator = returnGenerator();
console.log(generator.next().value);   // 1
console.log(generator.next().value);   // 2
console.log(generator.next().value);   // 3

```

These examples illustrate how you can return different data types and objects from JavaScript functions.

---

# How to use various types of parameters in JavaScript functions

Here are examples that demonstrate how to use different types of parameters in JavaScript functions:

1. **Primitives as Parameters:**
    
    ```jsx
    function primitiveExample(numberParam, stringParam, booleanParam) {
      console.log(numberParam, stringParam, booleanParam);
    }
    
    primitiveExample(42, "Hello, World!", true);
    
    ```
    
2. **Objects as Parameters:**
    
    ```jsx
    function objectExample(objParam, arrayParam) {
      console.log(objParam, arrayParam);
    }
    
    objectExample({ name: "Alice" }, [1, 2, 3]);
    
    ```
    
3. **Functions as Parameters:**
    
    ```jsx
    function functionExample(callback) {
      callback();
    }
    
    function sayHello() {
      console.log("Hello!");
    }
    
    functionExample(sayHello);
    
    ```
    
4. **Arrays as Parameters:**
    
    ```jsx
    function arrayExample(arrParam) {
      console.log(arrParam);
    }
    
    arrayExample([1, 2, 3, 4]);
    
    ```
    
5. **Object Destructuring as Parameters:**
    
    ```jsx
    function destructuringExample({ name, age }) {
      console.log(name, age);
    }
    
    destructuringExample({ name: "Bob", age: 30 });
    
    ```
    
6. **Rest Parameters:**
    
    ```jsx
    function restParameterExample(...args) {
      console.log(args);
    }
    
    restParameterExample(1, "a", true, [1, 2, 3]);
    
    ```
    
7. **Default Parameter Values:**
    
    ```jsx
    function defaultParameterValueExample(param = "default") {
      console.log(param);
    }
    
    defaultParameterValueExample(); // Uses the default value
    defaultParameterValueExample("custom value");
    
    ```
    
8. **Callback Functions:**
    
    ```jsx
    function asyncExample(callback) {
      setTimeout(callback, 1000);
    }
    
    function sayAsyncHello() {
      console.log("Async Hello!");
    }
    
    asyncExample(sayAsyncHello);
    
    ```
    
9. **Promises as Parameters:**
    
    ```jsx
    function promiseExample(promiseParam) {
      promiseParam.then(result => console.log(result));
    }
    
    const myPromise = new Promise((resolve) => {
      setTimeout(() => resolve("Promise resolved!"), 1000);
    });
    
    promiseExample(myPromise);
    
    ```
    
10. **Generator Functions as Parameters:**
    
    ```jsx
    function* generatorFunction() {
      yield 1;
      yield 2;
      yield 3;
    }
    
    function generatorExample(generatorFunc) {
      const generator = generatorFunc();
      console.log(generator.next().value);
      console.log(generator.next().value);
      console.log(generator.next().value);
    }
    
    generatorExample(generatorFunction);
    
    ```
    

These examples illustrate how to use various types of parameters in JavaScript functions to work with different data and functionalities.
