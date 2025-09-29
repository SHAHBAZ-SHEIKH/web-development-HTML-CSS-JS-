# JavaScript Functions – Detailed Guide

---

## 🔹 What is a Function?

A **function** in JavaScript is like a machine.

* You provide it with **input** (parameters).
* It performs some **task** (function body).
* It may give you **output** (return value).

Think of a **washing machine**:

* Input → dirty clothes
* Machine → function (wash)
* Output → clean clothes

---

## 🔹 Why Use Functions?

* To avoid repeating code (reusability).
* To organize code into smaller, logical parts.
* To make programs easier to read and maintain.
* To perform a specific task whenever needed.

---

## 🔹 Function Syntax

```javascript
function functionName(parameters) {
  // function body
  return result; // optional
}
```

---

## 🖥️ Example 1: Passing Numbers

```javascript
function addNumbers(a, b) {
  return a + b;
}

console.log(addNumbers(10, 20));
```

✅ Output:

```
30
```

👉 Here we passed **numbers** as arguments. The function adds them.

---

## 🖥️ Example 2: Passing Strings

```javascript
function greetUser(name) {
  return "Hello, " + name + "!";
}

console.log(greetUser("Shahbaz"));
console.log(greetUser("Ahmed"));
```

✅ Output:

```
Hello, Shahbaz!
Hello, Ahmed!
```

👉 Here we passed **strings**. The function joins them with another string.

---

## 🖥️ Example 3: Passing Arrays

```javascript
function printFruits(fruits) {
  for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
  }
}

printFruits(["Apple", "Banana", "Mango"]);
```

✅ Output:

```
Apple
Banana
Mango
```

👉 Here we passed an **array**. The function looped through and printed each item.

---

## 🖥️ Example 4: Passing Objects

```javascript
function showStudent(student) {
  console.log("Name:", student.name);
  console.log("Age:", student.age);
}

let student1 = { name: "Sara", age: 22 };
showStudent(student1);
```

✅ Output:

```
Name: Sara
Age: 22
```

👉 Here we passed an **object**. The function accessed its properties.

---

## 🔹 Local vs Global Scope

* **Global Scope**: Variables declared outside any function can be used anywhere.
* **Local Scope**: Variables declared inside a function can only be used inside that function.

```javascript
let globalVar = "Global";

function demoScope() {
  let localVar = "Local";
  console.log(globalVar); // works
  console.log(localVar);  // works
}

demoScope();
// console.log(localVar); ❌ Error (outside function)
```

---

## 🔹 Return Keyword

The `return` keyword sends a value back to where the function was called.

```javascript
function square(num) {
  return num * num;
}

let result = square(5);
console.log("Result:", result);
```

✅ Output:

```
Result: 25
```

👉 The returned value is stored in `result`.

---

## 🔹 Higher-Order Functions & Callbacks

* **Higher-Order Function**: A function that takes another function as input.
* **Callback Function**: The function passed as an argument.

### Example 1: Basic Callback

```javascript
function sayHello(name) {
  return "Hello, " + name;
}

function processUser(name, callback) {
  console.log(callback(name));
}

processUser("Shahbaz", sayHello);
```

✅ Output:

```
Hello, Shahbaz
```

---

### Example 2: Callback with Numbers

```javascript
function double(n) {
  return n * 2;
}

function calculate(num, callback) {
  return callback(num);
}

console.log(calculate(10, double));
```

✅ Output:

```
20
```

---

### Example 3: Callback with Delay

```javascript
function showMessage() {
  console.log("This message is shown after 2 seconds.");
}

setTimeout(showMessage, 2000);
```

👉 Here `setTimeout` is a **higher-order function** and `showMessage` is a **callback**.

---

### Example 4: Custom Callback Example

```javascript
function applyOperation(a, b, operation) {
  return operation(a, b);
}

function add(x, y) {
  return x + y;
}

function multiply(x, y) {
  return x * y;
}

console.log(applyOperation(5, 10, add));      // 15
console.log(applyOperation(5, 10, multiply)); // 50
```

---

## ✅ Summary

* Functions group reusable code.
* Parameters let us pass values into functions.
* We can pass **numbers, strings, arrays, and objects**.
* **Local scope** variables stay inside a function, **global scope** can be used everywhere.
* `return` gives a value back to where the function was called.
* **Higher-order functions** take other functions as input.
* **Callbacks** are used for flexibility and handling asynchronous tasks.

---
